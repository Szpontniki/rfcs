---
feature: linting
start-date: 2026-10-21
author: Khenzii <khenzii@khenzii.dev>
co-authors: N/A
related-prs: https://github.com/szpontniki/rfcs/pull/7
---

## Summary
[summary]: #summary

Linting of all our projects with linters from many different ecosystems.

## Detailed Overview
[detailed-overview]: #detailed-overview

I plan to make each repository maintain it's own linting configuration and tooling dependencies. My reasoning for this is that our repos are using vastly different ecosystems and so enforcing common rules, or even trying to share them in part, across all of them would be pointless and add lots of complexity. We should also update the current CIs to run lint checks alongside build checks once the linter configurations are ready.

## Motivation
[motivation]: #motivation

We all have different styling preferences but it absolutely will get confusing if we use too many of them together. Enforcing a single one per project with linters would be a favorable idea.

## Alternatives
[alternatives]: #alternatives

N/A

## Drawbacks
[drawbacks]: #drawbacks

N/A

## Unresolved Questions
[unresolved-questions]: #unresolved-questions

Do we want to lint not strictly code-oriented repos like api-schema? I suppose that it could make sense in some cases. Although I'm not sure whether there are linters made explicitly for YAML, perhaps some formatters. I'll look into this. There's always a chance that there's some OpenAPI speciffic tech given how popular it is.

## Prior Art
[prior-art]: #prior-art

N/A

## Future Possibilities
[future-possibilities]: #future-possibilities

N/A
