I changed the following so that wings is running on IPv6:

```yaml
...
api:
  host: '0.0.0.0'
  port: 8080
...
system:
...
  sftp:
    bind_address: '0.0.0.0'
    bind_port: 2022
    read_only: false
...
```

The portions should look like this if running on IPv6-only:

```yaml
...
api:
  host: '::'
  port: 8080
...
system:
...
  sftp:
    bind_address: '::'
    bind_port: 2022
    read_only: false
...
```

You could also replace `::` with your own public IPv6 address.