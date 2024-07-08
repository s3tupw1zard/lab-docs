Go to brew.sh and copy the homebrew install command. It will look like the following:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

When the script finished, installing, you will see something like this:

```bash
==> Homebrew has enabled anonymous aggregate formulae and cask analytics.
Read the analytics documentation (and how to opt-out) here:
  https://docs.brew.sh/Analytics
No analytics data has been sent yet (nor will any be during this install run).

==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations

==> Next steps:
- Run these two commands in your terminal to add Homebrew to your PATH:
    (echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/s3tupw1zard/.bashrc
    eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
- Install Homebrew's dependencies if you have sudo access:
    sudo apt-get install build-essential
  For more information, see:
    https://docs.brew.sh/Homebrew-on-Linux
- We recommend that you install GCC:
    brew install gcc
- Run brew help to get started
- Further documentation:
    https://docs.brew.sh

s3tupw1zard@Manuels-Laptop:~$
```

## Adding Homebrew to PATH

Next we need to add Homebrew to our path. For this, we execute the following:

For Bash:

```bash
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/$USER/.bashrc
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

For ZSH:

```zsh
(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/s3tupw1zard/.zshrc
    eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

After this, we can verify that the brew command is available:

```bash
whereis brew
```

The output will look like this:

```bash
s3tupw1zard@Manuels-Laptop:~$ whereis brew
brew: /home/linuxbrew/.linuxbrew/bin/brew
```

After this we can begin installing packages using homebrew:

```bash
brew install <package1> <package2>
```
