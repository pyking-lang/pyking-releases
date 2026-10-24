# Pyking releases

Releases of Pyking, a compiler and interpreter with no dependencies.

## macOS

macOS 11 or later, Apple Silicon and Intel, with [Homebrew](https://brew.sh):

```sh
brew update
brew install pyking-lang/tap/pyking
```

Installed with the formula of 0.1.4 or earlier? Replace it with the cask: `brew uninstall pyking && brew install pyking-lang/tap/pyking`.

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

## Nix

Linux and macOS, with flakes enabled, built from the source in [pyking-lang/pyking](https://github.com/pyking-lang/pyking) (`tools/packaging/nix/`). Run it once, or install it:

```sh
nix run 'github:pyking-lang/pyking/release-0.1.5?dir=tools/packaging/nix' -- hello.pyk
nix profile install 'github:pyking-lang/pyking/release-0.1.5?dir=tools/packaging/nix'
```

## Docker

x86_64 and arm64. The current directory is the container's `/work`; the command is `pyk repl` unless the run names another:

```sh
docker run --rm -it -v "$PWD:/work" ghcr.io/pyking-lang/pyking pyk hello.pyk
docker run --rm -it -v "$PWD:/work" ghcr.io/pyking-lang/pyking
docker run --rm -p 8000:8000 ghcr.io/pyking-lang/pyking pyk playground --port 8000
docker run --rm -it -v "$PWD:/work" ghcr.io/pyking-lang/pyking bash
```

`ghcr.io/pyking-lang/pyking:full` also holds Python, node, gcc, a JDK and OCaml, so `pyk compile --run` runs every target.
