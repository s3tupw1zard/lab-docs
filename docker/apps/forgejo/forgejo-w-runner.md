To generate the needed configs for the runner, you need to execute the following while replacing redacted with your token and git.example.com with your Forgejo instance url:

```docker-run
docker run -v /var/run/docker.sock:/var/run/docker.sock  -v $PWD:/data -u 0:0 --rm code.forgejo.org/forgejo/runner:3.3.0 forgejo-runner register --no-interactive --token <redacted> --name forgejo-runner01 --instance https://git.example.com
```

You then need to put the .runner and config.yml files in place:

```bash
cp ./config.yml /your/forgejo/working/path/runner/config.yaml
cp .runner /your/forgejo/working/path/runner/data/.runner
```

This is the docker-compose.yml file:

```yaml
networks:
  forgejo:
    external: false

name: forgejo
services:
  server:
    image: codeberg.org/forgejo/forgejo:7
    container_name: forgejo
    environment:
      - USER_UID=1000
      - USER_GID=1000
    restart: always
    networks:
      - forgejo
    volumes:
      - ./forgejo:/data
      - /etc/timezone:/etc/timezone:ro
      - /etc/localtime:/etc/localtime:ro
    ports:
      - '127.0.0.1:3000:3000'
      - '222:22'

  docker-in-docker:
    image: docker:dind
    container_name: 'docker_dind'
    privileged: true
    command: ['dockerd', '-H', 'tcp://0.0.0.0:2375', '--tls=false']
    restart: 'unless-stopped'

  runner:
    restart: unless-stopped
    links:
      - docker-in-docker
    depends_on:
      docker-in-docker:
        condition: service_started
    container_name: 'runner'
    image: code.forgejo.org/forgejo/runner:3.5.0
    user: 1000:1000
    command: forgejo-runner daemon
    environment:
      DOCKER_HOST: tcp://docker-in-docker:2375
      CONFIG_FILE: /config.yaml
      GITEA_INSTANCE_URL: https://git.example.com
      GITEA_RUNNER_REGISTRATION_TOKEN: "<redacted>"
      GITEA_RUNNER_NAME: forgejo-runner-1
      GITEA_RUNNER_LABELS: "ubuntu-latest,ubuntu-22.04,ubuntu-20.04,ubuntu-18.04"
    volumes:
      - ./runner/config.yaml:/config.yaml
      - ./runner/data:/data:rw
      - ./runner/cache/:/cache
      - /var/run/docker.sock:/var/run/docker.sock
    ports:
      - "[::]:42263:42263"
```