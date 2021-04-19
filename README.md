# kiex - Elixir version manager

Kiex allows you to easily build and switch between different [Elixir] versions.
It supports setting the default (global) Elixir version as well as per
shell/project versions. Everything is self-contained under `~/.kiex`.

Usage is based _lightly_ on [RVM], [kerl], and [rbenv].

## Install

Run the following to get up and running:

```bash
curl -sSL https://raw.githubusercontent.com/halostatue/kiex/master/kiex | bash -s
```

which will install in `$HOME/.kiex`.

### Prerequisites

- bash 3.x+
- curl
- erlang
- git
- make
- openssl

## Usage

List installed versions

- `kiex list`: List known releases
- `kiex list known` (or `kiex list releases`): List current branches
- `kiex list branches`: Install a known release or branch.
- `kiex install VERSION [ASNAME]`: Install specific Elixir version. If `ASNAME`
  is specified, the version is given this name.
- `kiex uninstall VERSION`: Uninstall specific Elixir version
- `kiex use VERSION [--default]`: Sets the Elixir version for current shell. If
  `--default` is specified, sets this version as the default.
- `kiex shell VERSION`: Starts sub-shell with given Elixir version. Exiting
  shell goes to default.
- `kiex alias VERSION ALIAS`: Create an alias for the specified Elixir version.
- `kiex unalias ALIAS`: Removes the alias.
- `kiex default VERSION`: Set default Elixir version
- `kiex implode`: This removes all versions of Elixir installed by kiex as well
  as all kiex components.
- `kiex selfupdate`: pull down latest updates for kiex.

### Options

- `KIEX_HOME`: Set this to a different directory to use instead of `~/.kiex`.
- `KIEX_OAUTH_TOKEN`: A GitHub token to be used for GitHub API requests.

## Sourcing Elixir into your path

After installing your preferred version of Elixir and setting it as your default
you can use kiex scripts to put your default Elixir bin into your path. One way
to do this is to add the following line into your rc file:

```bash
# Bash or zsh
[[ -s "$HOME/.kiex/scripts/kiex" ]] && source "$HOME/.kiex/scripts/kiex"
```

```tcsh
if (-e $HOME/.kiex/scripts/kiex.csh) source $HOME/.kiex/scripts/kiex.csh
```

```fish
test -s $HOME/.kiex/scripts/kiex; and source $HOME/.kiex/scripts/kiex

# or install halostatue/fish-kiex
fisher install halostatue/fish-kiex
```

## Design philosophy

- KISS
- Sane defaults
- Self-contained
- Single-purpose

## Comparison Q&A

### `exenv`

How is it like exenv (rbenv)?

- Super light and simple
- Focus on installing & managing one piece of software: Elixir

How is it not like exenv?

- Does not use shims
- Includes Elixir build component

### `kerl`

How is it like Kerl?

- Minimal command set
- Retrieves, builds, installs and manages different releases

How is it not like Kerl?

- Not as flexible on install path
- Dynamically gets release list instead of caching
- Build and install actions are not separated

### `RVM`

How is it like RVM?

- Sane defaults
- Uses Unix PATH to manage binary to use

How is it not like RVM?

- No function over-loading
- Does not manage/install extra software and prereqs

## Platforms/Shells tested

Operating Systems:

- Arch
- CentOS
- Debian
- FreeBSD
- OS X/Darwin
- Ubuntu

Shells:

- bash
- csh
- tcsh
- zsh
- fish

Erlang installs:

- erlang-solutions
- erlang.org
- kerl
- Debian apt, FreeBSD pkg, OS X brew

## Alternatives

- [exenv] + [elixir-build]
- [edwb]
- [asdf] extendable version manager for multiple languages (eg. Ruby, Erlang, Elixir)

### Related Tools

- [kerl] - Easy building and installing of Erlang/OTP instances
- [kex] - Build any tagged release of Erlang/OTP or Elixir from git
- [heroku-buildpack-elixir] - Elixir buildpack for Heroku
- [heroku-buildpack-erlang] - Erlang/OTP buildpack for Heroku
- [erln8] - Erlang/OTP version manager (builds from git source)
- [robisonsantos/evm] - Erlang Version Manager (from erlang.org tarballs)

## Limitations

- kiex does not build Erlang; it uses the currently active version.
- Same build directory used for every build (saving space vs keeping build env
  around)
- No uninstall option for installed Elixir versions
- No per-directory/project config file. This can be hacked with [direnv] or
  other, similar tools.

## TODO

- Merge install script into kiex script as an install function
- Cleanup build output (extra git info etc)
- Maybe print source line with use command
- Add active command (or similar) to show current Elixir
  - Already in list command - this would be the single version
  - Maybe show source line?
- Add sourceline or similar command to show source line to use?
- Maybe add dynamo install and setup for MIX_PATH
  - how to tie to Elixir used? gemset like?
  - use dynamo tags?
- Look at elixir-build for ideas, collaboration

### License

[LICENSE](LICENSE.md)

[elixir]: http://elixir-lang.org/
[rvm]: http://rvm.io
[kerl]: https://github.com/spawngrid/kerl
[rbenv]: https://github.com/sstephenson/rbenv
[exenv]: https://github.com/mururu/exenv
[elixir-build]: https://github.com/mururu/elixir-build
[edwb]: https://github.com/clutchanalytics/edwb
[asdf]: https://github.com/asdf-vm/asdf
[kex]: https://github.com/d0rc/kex
[heroku-buildpack-elixir]: https://github.com/HashNuke/heroku-buildpack-elixir
[heroku-buildpack-erlang]: https://github.com/heroku/heroku-buildpack-erlang
[erln8]: https://github.com/metadave/erln8
[robisonsantos/evm]: https://github.com/robisonsantos/evm
[direnv]: https://direnv.net
