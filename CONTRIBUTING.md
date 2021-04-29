# Contributing

I value any contribution to kx you can provide: a bug report, a feature request,
or code contributions. Code contributions to kx are especially
<del>welcome</del>encouraged. Here are some guidelines for contributing to kx.

## Issues Support Policy

kx _should_ work with any version of Elixir after 1.0, but support in the [issue
tracker] will only be provided for Elixir 1.7 or later. When Elixir 1.13 is
released, the minimum supported Elixir will be 1.8, and the minimum versions
will increment after that, following the Elixir version deprecation strategy.

_Branch_ build issues will receive limited support, as branch builds would
typically be used for experimental changes that are still in development or
under consideration as a pull request.

## Code Contributions

- Match my coding style.
- Use [shfmt] and [shellcheck]. Changes that do not conform to either will be
  required to change until they do.
- Use a thoughtfully-named topic branch that contains your change. Rebase
  your commits into logical chunks as necessary.
- Use [quality commit messages][].
- Do not change the version number; when your patch is accepted and a release
  is made, the version will be updated at that point.
- Submit a GitHub pull request with your changes.
- New or changed behaviours require appropriate documentation.

### Workflow

Here's the most direct way to get your work merged into the project:

- Fork the project.
- Clone down your fork (`git clone git://github.com/<username>/diff-lcs.git`).
- Create a topic branch to contain your change (`git checkout -b awesome_feature`).
- Hack away, add tests. Not necessarily in that order.
- Make sure everything still passes by running `rake`.
- If necessary, rebase your commits into logical chunks, without errors.
- Push the branch up (`git push origin my_awesome_feature`).
- Create a pull request against halostatue/kx and describe what your
  change does and the why you think it should be merged.

## Features Wanted

- A [Homebrew] formula and/or tap as described in [kiex#36]. This is possible
  with kx because releases are tagged, providing release tarballs.

- Completions for bash and zsh. Completions for fish are in progress and will be
  included in a later release.

### Features Not Wanted

There are some features requests that will not be accepted:

- Anything like RVM gemsets, as described in [kiex#44]. Even with the
  `Mix.install` capabilities being introduced in Elixir 1.12, there's no
  meaning to a package set concept in Elixir; it will not be supported by kx.

- Translating kx to anything other than bash. Parts of kx would be much easier
  in a more capable language, but it would make it that much harder tor un.

## Contributors

- Austin Ziegler (@halostatue) forked kx from kiex.
- Taylor Carpenter (@taylor) created kiex.

kx benefits from various [contributors][kiex-contributors] over the years:

- Armando di Canno (@greymouser)
- Evan Barta (@evinb)
- Wenbiao Zheng (@jsvisa)
- Sascha Kattelmann (@GalaxyGorilla)
- Greg Farrell (@gregerg)
- Hiro Asari (@BanzaiMan)
- Andrea Leopardi (@whatyouhide)
- Enrique Barragán (@arcticbarra)
- Kevin van Rooijen (@kwrooijen)
- Eric Liaw (@eliaw)
- Roman Coedo (@rcoedo)
- wendy kurniawan soesanto (@wendy0402)
- Josh Burrows (@qhool)
- Kenji Rititake (@jj1bdx)
- Larry Lv (@larrylv)
- Oleksii Semilietov (@spylik)
- mike (@fntz)
- Marc Ignacio (@padi)
- Kyle Baker (@kylebakerio)
- András Boroska (@aboroska)
- @schnittchen
- Darko Fabijan (@darkofabijan)

[quality commit messages]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[shfmt]: https://github.com/mvdan/sh/tree/master/cmd/shfmt
[shellcheck]: https://github.com/koalaman/shellcheck
[issue tracker]: https://github.com/halostatue/kx/issues
[kiex-contributors]: https://github.com/taylor/kiex/graphs/contributors
[kx-contributors]: https://github.com/halostatue/kx/graphs/contributors
[homebrew]: https://brew.sh
[kiex#36]: https://github.com/taylor/kiex/issues/36
[kiex#44]: https://github.com/taylor/kiex/issues/44
