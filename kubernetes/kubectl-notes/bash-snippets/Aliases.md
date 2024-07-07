Here are some aliases and functions I'm using.

## Install ZSH

For this we need to install zsh:

```bash
sudo apt instal zsh
```

The output will be like this:

```bash
s3tupw1zard@Manuels-Laptop:~$ sudo apt install zsh
[sudo] password for s3tupw1zard:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  zsh-common
Suggested packages:
  zsh-doc
The following NEW packages will be installed:
  zsh zsh-common
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
Need to get 4985 kB of archives.
After this operation, 19.1 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu noble/main amd64 zsh-common all 5.9-6ubuntu2 [4173 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 zsh amd64 5.9-6ubuntu2 [812 kB]
Fetched 4985 kB in 1s (5549 kB/s)
Selecting previously unselected package zsh-common.
(Reading database ... 40663 files and directories currently installed.)
Preparing to unpack .../zsh-common_5.9-6ubuntu2_all.deb ...
Unpacking zsh-common (5.9-6ubuntu2) ...
Selecting previously unselected package zsh.
Preparing to unpack .../zsh_5.9-6ubuntu2_amd64.deb ...
Unpacking zsh (5.9-6ubuntu2) ...
Setting up zsh-common (5.9-6ubuntu2) ...
Setting up zsh (5.9-6ubuntu2) ...
Processing triggers for debianutils (5.17build1) ...
Processing triggers for man-db (2.12.0-4build2) ...
s3tupw1zard@Manuels-Laptop:~$
```

## Install oh-my-zsh

Then we install oh-my-zsh:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

If curl isn't installed we can install it using:

```bash
sudo apt install curl
```

### Switch from Bash to ZSH


During the installation, the script will ask you if you want to change your default shell to zsh:

```bash
Do you want to change your default shell to zsh? [Y/n]
```

Here we type `Y` and proceed by pressing Enter.

## Install kube-aliases

First clone [this](git clone https://github.com/Dbz/kube-aliases) repo into your home folder:

```
git clone https://github.com/Dbz/kube-aliases.git ~/.oh-my-zsh/custom/plugins/kube-aliases
echo "plugins+=(kube-aliases)" >> ~/.zshrc
```


Save it into your home folder:

```bash
nano $HOME/.kube-aliases
```

Add this to your .bashrc:

```bash
echo "source $HOME/.kube-aliases" >> $HOME/.bashrc
```

Source your .bashrc file:

```bash
source $HOME/.bashrc
```

To see a full list of aliases, use:

```bash
khelp usage
```


I got this from Github: [Dbz/kube-aliases](https://github.com/Dbz/kube-aliases)
