---
feature: android_client
start-date: 2026-10-14
author: Khenzii <khenzii@khenzii.dev>
co-authors: N/A
related-prs: https://github.com/szpontniki/rfcs/pull/3
---

## Summary
[summary]: #summary

Introducing an Android client as part of the project's development.

## Detailed Overview
[detailed-overview]: #detailed-overview

N/A

## Motivation
[motivation]: #motivation

It will be cool to add another app to the `system` repository. We could also use this as an opportunity to test out how our `api-schema` is behaving across different ecosystems and most importantly our `auxiliary-api` will finally have multiple consumers. As of right now, with only `web` using it, one could make a point that it could've been included as part of the `web` code.

## Alternatives
[alternatives]: #alternatives

N/A

## Drawbacks
[drawbacks]: #drawbacks

Deployment of `system` will be harder, as more repos will need to have matching `api-schema` hashes, but that's to be expected and it's the wanted behavior of our architecture.

## Unresolved Questions
[unresolved-questions]: #unresolved-questions

I'm not yet sure as to what technology we should use when developing it. I'll consider Flutter, Kotlin and Java. As of right now I'm the most keen towards the idea of building it in Java.

## Prior Art
[prior-art]: #prior-art

N/A

## Future Possibilities
[future-possibilities]: #future-possibilities

N/A
