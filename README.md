# Pyking releases

Releases of Pyking, a compiler and interpreter with no dependencies.

## macOS

macOS 11 or later, Apple Silicon and Intel, with [Homebrew](https://brew.sh):

```sh
brew update
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

## Nix

Linux and macOS, with flakes enabled. Run it once, or install it:

```sh
nix run github:pyking-lang/pyking-releases -- hello.pyk
nix profile install github:pyking-lang/pyking-releases
```

## Docker

x86_64 and arm64. The current directory is the container's `/work`:

```sh
docker run --rm -it -v "$PWD:/work" ghcr.io/pyking-lang/pyking hello.pyk
docker run --rm -it -v "$PWD:/work" ghcr.io/pyking-lang/pyking repl
docker run --rm -p 8000:8000 ghcr.io/pyking-lang/pyking playground --port 8000
```

`ghcr.io/pyking-lang/pyking:full` also holds Python, node, gcc, a JDK and OCaml, so `pyk compile --run` runs every target.
