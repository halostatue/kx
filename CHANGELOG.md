# kx Changelog

## 1.0.0 / 2021-04-30

- Forked from [taylor/kiex]. See the [rationale](RATIONALE.md).
- Formatted with `shfmt` and checked for issues with `shellcheck`.
- Removed the _generic_ startup script in favour of being explicit about loading
  the fish, bash, or csh scripts directly.
- Only Elixir 1.0 or later can be installed with kx.
- The Elixir version is associated associated with the exact Erlang/OTP release
  used at build time.

[taylor/kiex]: https://github.com/taylor/kiex
