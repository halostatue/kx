# kx - Elixir Version Manager

kx allows you to easily build and switch between different [Elixir] versions. It
supports setting the default (global) Elixir version as well as per-shell or
per-project versions. Everything is self-contained under one directory, by
default `$XDG_DATA_HOME/kx` (usually `$HOME/.local/share/kx`).

kx is forked from [kiex] and has a few key differences:

- kx focuses on modern Elixirs (support is provided for Elixir 1.7.0 or later,
  but kx should build any version after Elixir 1.0.0).

- kx Elixir builds are tied to the version of Erlang/OTP used to build Elixir,
  and uses that to prevent the use of Elixir builds incompatible with the
  current version of Erlang/OTP installed.

- kx installs Elixir releases from `elixir-lang/elixir` tarballs. It only uses
  `git` to install branches. Branches can be installed from _any_ repo.

While kx will be familiar to users of kiex, it is different, intentionally so.

## Install

```bash
# Install to $XDG_DATA_HOME/kx ($HOME/.local/share/kx)
curl -sSL https://raw.githubusercontent.com/halostatue/kx/main/install |
  bash -s
```

If a different directory is preferred it can be installed by specifying
`$KX_HOME` prior to running `bash`.

```bash
# Install to $HOME/kx
curl -sSL https://raw.githubusercontent.com/halostatue/kx/main/install |
  KX_HOME=$HOME/kx bash -s
```

### Prerequisites

- `bash` 3.x+
- `curl`
- `erlang`
- `git`
- `make` (or `gmake` on FreeBSD)
- `openssl` # Required to build
- `jq`

## Usage

- `kx list [installed]`: Shows kx-managed Elixir versions
- `kx list releases`: Shows available Elixir releases
- `kx list branches`: Shows available Elixir branches
- `kx install VERSION [AS]`: Installs the given release version
- `kx reinstall VERSION`: Reinstalls the given release version
- `kx uninstall VERSION`: Uninstalls the given release version
- `kx use VERSION`: Uses the given version for this shell
- `kx shell VERSION`: Uses the given version for this shell
- `kx source VERSION`: Prints the script to load for this version
- `kx default VERSION|--clear`: Manages the default Elixir version
- `kx doctor`: Checks whether kx can be used
- `kx self update`: Downloads and Updates kx
- `kx self destruct`: Removes kx and all installed Elixirs

### Options

- `KX_HOME`: Set this to a different directory to use instead of
  `$XDG_DATA_HOME/kx`.
- `KX_OAUTH_TOKEN`: A GitHub token to be used for GitHub API requests.

## Limitations

- kx does not build Erlang; it uses the currently active version.
- The same build directory used for every git build (saving space vs keeping
  build around). At the moment, the build directory for each version's tarball
  is kept. (This may change.)

### Licence

[LICENCE](LICENCE.md)

[kiex]: https://github.com/taylor/kiex
[elixir]: https://elixir-lang.org/
