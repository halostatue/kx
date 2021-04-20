# kx Changelog

## 2.0 / 2021-04-18

- Forked from [taylor/kiex] for a cleanup.
- Applied cleanups based on `shellcheck`.
- Formatted with `shfmt`.
- Removed the _generic_ startup script.
- Support for Elixir versions older than 1.0 is hard deprecated; those releases
  are explicitly filtered.
- No support will be given for Elixir versions older than 1.7.
- The Elixir version installed is tagged with the Erlang/OTP release used at
  build time.
- The Elixir version selected is tagged with the Erlang/OTP release used at
  at `use` time.

### Notes on Issues in [taylor/kiex]

- [#28]: This issue has been open since 2016. It is not clear whether this can
  be reproduced.
- [#36]: This will be easier to implement after this update since there will be
  clear versions.
- [#44]: This is not applicable to kiex and should be closed. It will not be
  implemented as there is no concept like `gemsets` for `kiex`, and it’s not
  appropriate because Elixir doesn’t have globally install packages like Ruby.
- [#50]: This issue has been resolved.
- [#51]: I do not understand the purpose of this issue, however one of the
  features being implemented as part of this fork is providing an alternate name
  for an install.
- [#53]: This will be added as part of this fork, imported from [#54].
- [#60]: This is outside of the scope of kiex. The recommendation here would be
  to set the kiex version in environment variables with Ansible.
- [#61]: This option (searching `mix.exs`) is suboptimal, as the version of
  Elixir in the `mix.exs` file is generally bounded.
- [#73]: Open since 2017 without action.
- [#85]: GitHub API issues will be handled better.
- [#90]: If this can be done without using `tac`, it will be implemented.

### Build Issues

- [#21], [#43], [#59], [#66], [#69], [#86], [#88]
- [#79] - This appears to have been resolved at some point.
- [#81] - This appears to be a `git clone` error where the Elixir build scripts
  gets written with DOS line endings.
- [#91] - This can be closed.

[taylor/kiex]: https://github.com/taylor/kiex
[#21]: https://github.com/taylor/kiex/issues/21
[#28]: https://github.com/taylor/kiex/issues/28
[#36]: https://github.com/taylor/kiex/issues/36
[#43]: https://github.com/taylor/kiex/issues/43
[#44]: https://github.com/taylor/kiex/issues/44
[#50]: https://github.com/taylor/kiex/issues/50
[#51]: https://github.com/taylor/kiex/issues/51
[#53]: https://github.com/taylor/kiex/issues/53
[#54]: https://github.com/taylor/kiex/pull/54
[#59]: https://github.com/taylor/kiex/issues/59
[#66]: https://github.com/taylor/kiex/issues/66
[#79]: https://github.com/taylor/kiex/issues/79
[#81]: https://github.com/taylor/kiex/issues/81
[#86]: https://github.com/taylor/kiex/issues/86
[#88]: https://github.com/taylor/kiex/issues/88
[#91]: https://github.com/taylor/kiex/issues/91
