# Rationale

## Why Fork kiex?

I thought it was the _better_ option. The journey to that point is convoluted.

I switched to the [Fish shell] a couple of years ago and I created
[halostatue/fish-kiex] to automatically load kiex rather than having to remember
to add it to my Fish configuration. I was recently (April 2021) working through
some improvements to it to add command-line completion and some other quality of
life improvements. In looking at that, I started looking deeper into the
implementation of kiex to see what I could use to make those happen.

This led to the start of some consideration on what would be changed if I ran
[shfmt] (a lot) and what would be required to change if I ran [shellcheck] (a
lot more). So I started working on what would become a PR or a series of PRs on
[kiex]…and it kept growing. And growing.

Breaking the changes down would have resulted in _many_ PRs or a single
all-in-one PR replacing 75% or more of the original implementation…and it
wouldn't have helped with any of the original problem I had…making it easier to
use kiex to improve `halostatue/fish-kiex`.

So I started reworking the code. I applied my idiomatic style of bash scripting.
I applied shfmt and shellcheck ruthlessly. I changed dependencies. I dropped all
support for Elixir versions less than 1.0. I dropped commands that I've never
used and changed how a number of the commands work. I changed the help messages
and added a _lot_ more help messages. I made it so that kx has knowledge of the
underlying Erlang/OTP version that was used to install each Elixir‡. I added
support for other repositories and for release tarballs. I added caching.

> ‡ I have run into at least two instances where I tried to run an Elixir built
> with Erlang 22 on Erlang 21.

I've kept the ease of kiex. I've kept the principle of being self-contained.

kx (1,593 lines) is larger than kiex (1,124 lines) and has _different_
functionality. `git diff --stat` tells me that there's 1,383 insertions and 914
deletions. I can't consider myself a good citizen by dropping a diff like that
on a project that last saw a merged patch 13 months ago. So I've forked kiex as
kx.

I'm perfectly willing to contribute kx back to kiex; without kiex, kx would not
exist. I don't know that it's necessary for there to be two "main" tools that do
almost the same as each other. I do think that the improvements that I've made
along the way are worthwhile and I'll keep maintaining kx as long as I keep
using it.

[fish shell]: https://fishshell.com 'friendly interactive shell'
[halostatue/fish-kiex]: https://github.com/halostatue/fish-kiex
[shfmt]: https://github.com/mvdan/sh/tree/master/cmd/shfmt
[shellcheck]: https://github.com/koalaman/shellcheck
[kiex]: https://github.com/taylor/kiex
