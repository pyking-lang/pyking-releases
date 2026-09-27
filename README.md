# Pyking releases

Releases of Pyking, a compiler and interpreter with no dependencies.

## macOS

macOS 11 or later, Apple Silicon and Intel, with [Homebrew](https://brew.sh):

```sh
brew install pyking-lang/tap/pyking
```

## Linux and WSL

Any distribution, x86_64 or aarch64. Installs into `~/.local`, with no sudo:

```sh
curl -fsSL https://github.com/pyking-lang/pyking-releases/releases/latest/download/install.sh | sh
```

`sh -s -- --system` installs for every user instead, `--version X` a given release, and `--uninstall` removes it. On Debian, Ubuntu and WSL Ubuntu, the `.deb` of a release works too:

```sh
curl -fLO https://github.com/pyking-lang/pyking-releases/releases/latest/download/pyking_amd64.deb
sudo apt install ./pyking_amd64.deb
```

`pyk notebook` and `pyk playground` also need Python 3.10 or later.
