---
feature: containerization
start-date: 2026-10-14
author: Khenzii <khenzii@khenzii.dev>
co-authors: N/A
related-prs: https://github.com/szpontniki/rfcs/pull/5
---

## Summary
[summary]: #summary

Containerization of our apps with Docker.

## Detailed Overview
[detailed-overview]: #detailed-overview

We'll be using Docker as it's the de facto go to tool for this task. We need to containerize:

- web,
- auxiliary-api,
- docs

I'll also look into writing a Dockerfile for firmware, as we could theoretically containerize the mock version of the program. This could prove useful in the future.

Another repository that will be affected by this repo is system, because even though it won't be directly built via a Dockerfile, I want it to support building the apps together upon release. This way we could have images like `szpontniki/web:v3.1.2` and `szpontniki/web:v2.1.0-system` where the second one would be compatible with all the other apps having the `v2.1.0-system` tag.

Other repos (api-schema and rfcs) obviously don't require any changes as part of this RFC.

## Motivation
[motivation]: #motivation

I've been looking to finally host the project, but in order to do so effectively we need to containerize our apps first.

## Alternatives
[alternatives]: #alternatives

I don't think that there are any alternatives. Distributing the binaries in most other ways would be troublesome.

## Drawbacks
[drawbacks]: #drawbacks

N/A

## Unresolved Questions
[unresolved-questions]: #unresolved-questions

Currently web isn't passing the build test. I'll temporarily disable the generated errors if possible (from what I remember they're quality of code enforcements) and I'll open an issue for [@Azteczek](https://github.com/azteczek/) to take care of.

## Prior Art
[prior-art]: #prior-art

N/A

## Future Possibilities
[future-possibilities]: #future-possibilities

N/A
