---
feature: rfc_process
start-date: 2026-10-14
author: Khenzii <khenzii@khenzii.dev>
co-authors: N/A
related-prs: "[#1](pr1)"
---

[pr1]: https://github.com/szpontniki/rfcs/pull/1

## Summary
[summary]: #summary

This RFC introduces the process of adding future RFCs. They're meant to be a place for storing future ideas and eventually discussion regarding them.

## Detailed Overview
[detailed-overview]: #detailed-overview

N/A

## Motivation
[motivation]: #motivation

While this organization is technically nowhere near large enough to require an RFC forum, I do think that it will still grow quite useful. We're working in a polyrepo environment, and so storing organization wide feature ideas is a noticeable problem. Creating unlinked, separate GitHub issues across all the repos is a hustle which could be streamlined by a process like this. This repository will contain strictly defined descriptions of breaking changes, and thus hopefully allowing us to track the process of theirs development more easily.

## Alternatives
[alternatives]: #alternatives

We could potentially use some third party service for writing down ideas, or we could perhaps even keep them on Discord; but I think that having them all on GitHub, and showing up in the [Issues Tracker](https://github.com/orgs/szpontniki/projects/3), will be a more elegant solution.

## Drawbacks
[drawbacks]: #drawbacks

There is a possibility that we'll run into a feeling of increased bureaucracy, but I think that we'll avoid this by keeping this repository rather relaxed. I don't intend to turn this into another [nixos/rfcs](https://github.com/nixos/rfcs) or [rust-lang/rfcs](https://github.com/rust-lang/rfcs). While those repositories were obviously a huge help when it came to designing this one, we surely don't need to be as strict as they are due to the fact that we're not managing a community of any noticeable size.

## Unresolved Questions
[unresolved-questions]: #unresolved-questions

N/A

## Prior art
[prior-art]: #prior-art

As mentioned, many other open source projects also follow the RFC process. That said though we won't enforce it strictly, as it will be more of a whiteboard for storing breaking changes.

This could be loosely linked to repos such as:

- [reactjs/rfcs](https://github.com/reactjs/rfcs),
- [electron/rfcs](https://github.com/electron/rfcs),
- etc.

## Future possibilities
[future-possibilities]: #future-possibilities

Later on I'll have to update this repo's `README.md` to include a quick guide on creating new RFCs. I'll also create GitHub issue labels such as `meta` or `rfc`.
