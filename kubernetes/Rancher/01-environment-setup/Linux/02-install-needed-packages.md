First we install `kubectl` and `k9s` using brew:

```bash
brew install kubectl k9s
```

The output will look like this:

```bash
s3tupw1zard@Manuels-Laptop:~$ brew install kubectl k9s
==> Auto-updating Homebrew...
Adjust how often this is run with HOMEBREW_AUTO_UPDATE_SECS or disable with
HOMEBREW_NO_AUTO_UPDATE. Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Downloading https://ghcr.io/v2/homebrew/core/kubernetes-cli/manifests/1.30.2
################################################################################################################# 100.0%
==> Fetching dependencies for kubernetes-cli: gmp, isl, mpfr, libmpc, lz4, xz, zlib, zstd, binutils and gcc
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/manifests/6.3.0
################################################################################################################# 100.0%
==> Fetching gmp
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/blobs/sha256:3dca3544faca889c7389a5fdbd2b5b00582c34a4e14607033573ad
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/isl/manifests/0.26
################################################################################################################# 100.0%
==> Fetching isl
==> Downloading https://ghcr.io/v2/homebrew/core/isl/blobs/sha256:db14ba1e4ea23ab41e06930dcf25ae9023c5e395c88602da2a9b6a
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/mpfr/manifests/4.2.1
################################################################################################################# 100.0%
==> Fetching mpfr
==> Downloading https://ghcr.io/v2/homebrew/core/mpfr/blobs/sha256:18857bac44d9f49faeb1d147146ba7fb420d5bf85076f69c68a86
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/libmpc/manifests/1.3.1
################################################################################################################# 100.0%
==> Fetching libmpc
==> Downloading https://ghcr.io/v2/homebrew/core/libmpc/blobs/sha256:f6542ae5bcf643ca0c980c7000cde1585922e76be080b3cc342
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/manifests/1.9.4
################################################################################################################# 100.0%
==> Fetching lz4
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/blobs/sha256:1757fefc3840e11c4822e4c2a95aa62aca44a4eaccce6f5c414ea5
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/xz/manifests/5.4.6
################################################################################################################# 100.0%
==> Fetching xz
==> Downloading https://ghcr.io/v2/homebrew/core/xz/blobs/sha256:0736983b952c5273bb5a345008bac7311c2f4b60758d69cc05495d5
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/zlib/manifests/1.3.1
################################################################################################################# 100.0%
==> Fetching zlib
==> Downloading https://ghcr.io/v2/homebrew/core/zlib/blobs/sha256:38f2469db2ce63b70855a98e5ee27b5b5a92874e52542cbdc0b23
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/manifests/1.5.6
################################################################################################################# 100.0%
==> Fetching zstd
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/blobs/sha256:0e6ddbd4c969bb84261f12b759fb78a828d6f734c9e515793c6ac
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/binutils/manifests/2.42
################################################################################################################# 100.0%
==> Fetching binutils
==> Downloading https://ghcr.io/v2/homebrew/core/binutils/blobs/sha256:1b498d741c952477f46dc6a2f46f91ace4e65579c56c41918
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/gcc/manifests/14.1.0_1
################################################################################################################# 100.0%
==> Fetching gcc
==> Downloading https://ghcr.io/v2/homebrew/core/gcc/blobs/sha256:6356fd3788f92d60a10ed20cd6b1ec4f4d53235ece41bb7d867870
################################################################################################################# 100.0%
==> Installing kubernetes-cli dependency: gcc
==> Downloading https://ghcr.io/v2/homebrew/core/gcc/manifests/14.1.0_1
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/9de763cb06656c454ed0cd4073737d75caec823de6fce1db96eba5cf44714053--gcc-14.1.0_1.bottle_manifest.json
==> Installing dependencies for gcc: gmp, isl, mpfr, libmpc, lz4, xz, zlib, zstd and binutils
==> Installing gcc dependency: gmp
==> Downloading https://ghcr.io/v2/homebrew/core/gmp/manifests/6.3.0
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/70a72a71216843d66a953c06ff6337445ce9bc94fae9f0e301e2f59005274a8e--gmp-6.3.0.bottle_manifest.json
==> Pouring gmp--6.3.0.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/gmp/6.3.0: 24 files, 3.9MB
==> Installing gcc dependency: isl
==> Downloading https://ghcr.io/v2/homebrew/core/isl/manifests/0.26
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/ec0bbec77171645273dd59a9ccfdf290deccd999b3ca2082e0478d282b777ec0--isl-0.26.bottle_manifest.json
==> Pouring isl--0.26.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/isl/0.26: 75 files, 9.8MB
==> Installing gcc dependency: mpfr
==> Downloading https://ghcr.io/v2/homebrew/core/mpfr/manifests/4.2.1
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/a2a3424f4974f6febfa0334a93f35f508eaef3f4ad04320f73d9498302295635--mpfr-4.2.1.bottle_manifest.json
==> Pouring mpfr--4.2.1.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/mpfr/4.2.1: 32 files, 3.9MB
==> Installing gcc dependency: libmpc
==> Downloading https://ghcr.io/v2/homebrew/core/libmpc/manifests/1.3.1
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/fdfa98e0f8bb3ce075cb32776ac2345aa2f89252706c162aecfc841085fa76be--libmpc-1.3.1.bottle_manifest.json
==> Pouring libmpc--1.3.1.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/libmpc/1.3.1: 14 files, 643.0KB
==> Installing gcc dependency: lz4
==> Downloading https://ghcr.io/v2/homebrew/core/lz4/manifests/1.9.4
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/379e59b981667f9585b33a2ff318769d8edca3ce6fd2e9a67ed291ae3e0cc872--lz4-1.9.4.bottle_manifest.json
==> Pouring lz4--1.9.4.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/lz4/1.9.4: 23 files, 697.9KB
==> Installing gcc dependency: xz
==> Downloading https://ghcr.io/v2/homebrew/core/xz/manifests/5.4.6
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/b2cc4077807c100af6e0253f51d186f187ff55165638cbe3a4aa16d1c4762660--xz-5.4.6.bottle_manifest.json
==> Pouring xz--5.4.6.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/xz/5.4.6: 165 files, 2.7MB
==> Installing gcc dependency: zlib
==> Downloading https://ghcr.io/v2/homebrew/core/zlib/manifests/1.3.1
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/f68d0caf232d52f2aa586abefbbfd7e958e384d84f3967008fa83de94b5f10ae--zlib-1.3.1.bottle_manifest.json
==> Pouring zlib--1.3.1.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/zlib/1.3.1: 14 files, 476KB
==> Installing gcc dependency: zstd
==> Downloading https://ghcr.io/v2/homebrew/core/zstd/manifests/1.5.6
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/29403e0df5404d8aeca0e750ac135ec9ef44fc5eeb6df69170ed602acabf0ffb--zstd-1.5.6.bottle_manifest.json
==> Pouring zstd--1.5.6.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/zstd/1.5.6: 32 files, 2.9MB
==> Installing gcc dependency: binutils
==> Downloading https://ghcr.io/v2/homebrew/core/binutils/manifests/2.42
Already downloaded: /home/s3tupw1zard/.cache/Homebrew/downloads/21c83d367c6459449acbeea36db5c99baba65353c7f09b8cfe34a98977783291--binutils-2.42.bottle_manifest.json
==> Pouring binutils--2.42.x86_64_linux.bottle.tar.gz
🍺  /home/linuxbrew/.linuxbrew/Cellar/binutils/2.42: 4,797 files, 490.5MB
==> Installing gcc
==> Pouring gcc--14.1.0_1.x86_64_linux.bottle.tar.gz
Warning: The post-install step did not complete successfully
You can try again using:
  brew postinstall gcc
==> Summary
🍺  /home/linuxbrew/.linuxbrew/Cellar/gcc/14.1.0_1: 1,731 files, 500.4MB
==> Fetching kubernetes-cli
==> Downloading https://ghcr.io/v2/homebrew/core/kubernetes-cli/blobs/sha256:e14a3ad9d310d78bd27840026ce7a0256bdcd3dff6c
################################################################################################################# 100.0%
==> Downloading https://ghcr.io/v2/homebrew/core/k9s/manifests/0.32.5
################################################################################################################# 100.0%
==> Fetching k9s
==> Downloading https://ghcr.io/v2/homebrew/core/k9s/blobs/sha256:7976a912773c66e26bac3c89e5886dc369f2d23f34efc916f76ec2
################################################################################################################# 100.0%
==> Pouring kubernetes-cli--1.30.2.x86_64_linux.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /home/linuxbrew/.linuxbrew/etc/bash_completion.d
==> Summary
🍺  /home/linuxbrew/.linuxbrew/Cellar/kubernetes-cli/1.30.2: 236 files, 50MB
==> Running `brew cleanup kubernetes-cli`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Pouring k9s--0.32.5.x86_64_linux.bottle.tar.gz
==> Caveats
Bash completion has been installed to:
  /home/linuxbrew/.linuxbrew/etc/bash_completion.d
==> Summary
🍺  /home/linuxbrew/.linuxbrew/Cellar/k9s/0.32.5: 10 files, 119.8MB
==> Running `brew cleanup k9s`...
==> Caveats
==> kubernetes-cli
Bash completion has been installed to:
  /home/linuxbrew/.linuxbrew/etc/bash_completion.d
==> k9s
Bash completion has been installed to:
  /home/linuxbrew/.linuxbrew/etc/bash_completion.d
s3tupw1zard@Manuels-Laptop:~$
```

Then we install `tmux` and `vim` using apt:

```bash
sudo apt install tmux vim
```

Since it's already installed on my machine, the output will look like this:

```bash
s3tupw1zard@Manuels-Laptop:~$ sudo apt install tmux vim
[sudo] password for s3tupw1zard:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
tmux is already the newest version (3.4-1build1).
tmux set to manually installed.
vim is already the newest version (2:9.1.0016-1ubuntu7).
vim set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
s3tupw1zard@Manuels-Laptop:~$
```

