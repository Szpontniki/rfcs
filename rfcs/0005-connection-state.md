---
feature: connection_state
start-date: 2026-10-21
author: Khenzii <khenzii@khenzii.dev>
co-authors: N/A
related-prs: https://github.com/szpontniki/rfcs/pull/9
---

## Summary
[summary]: #summary

Create a centralised helper on the clients (currently just web) that will manage different possible ways of connecting to firmware API.

## Detailed Overview
[detailed-overview]: #detailed-overview

Our firmware API currently can be interacted with in two ways:

- HTTP (the mock version of it is implementing it),
- Bluetooth Low Energy (this is what the microcontroller does)

In the future, this might be actually extended to:

- Bluetooth Classic,
- WebSockets

Eventually, I expect firmware API to support all those types of connection. We need to support both BLE and Bluetooth Classic, as BLE can be used from browsers experimentally and Bluetooth Classic will offer superior throughput on the android client which will be able to utilise it. I also want to support communication via WebSockets, as we may want to display movies on the display later on and then HTTP will obviously struggle to broadcast that many frames a second.

Those many ways of API interaction obviously come with their own issues. The primary one being that ideally, the client using the API shouldn't have to care which communication channel it's using. It should be given the choice to use many different technologies that may suit it to connect, but in the end still be able to say "color pixel (1, 1) to #000". To accomplish something like this we'd have to simplify the API as far as we can. This would basically result in the API being describable as a collection of instructions being identifiable by name and taking required input via JSON. For example: we may have a route called `/display/color-pixels` on the HTTP API, expecting a body of pixels like this: `{ x: int, y: int, color: [int, int, int] }[]`. To make a Bluetooth API compatible with this one we should make the Bluetooth request string contain: `<path>;<body>`, so in this case: `/display/color-pixels;{ x: int, y: int, color: [int, int, int] }[]`. This way, the client could simply write a helper util that would, depending on some condition, either pass the data to the firmware via HTTP or via Bluetooth. WebSockets will also be suitable for such a mechanism.

This change will currently require modifications to firmware and web code, and in the future it will impact android.

## Motivation
[motivation]: #motivation

I think that designing the firmware API in such an accessible manner will significantly simplify the process of developing new clients and will allow us to maintain a greater range of connecting protocols with a lower effort.

## Alternatives
[alternatives]: #alternatives

I can't put my mind on any viable alternatives. This kind of logic can't be outsourced to auxiliary-api as in the end the client itself needs to be supporting many different ways of communication with the firmware. All the while writing the clients separately and then choosing which one to use everytime would be a ridiculous task.

## Drawbacks
[drawbacks]: #drawbacks

We won't be able to use some protocol speciffic features, such as HTTP's headers and so on, but that's acceptable. For our current needs we don't require them anyways.

## Unresolved Questions
[unresolved-questions]: #unresolved-questions

I wonder if Orval-generated web code exposes useful types like `ValidPaths` that could be used for writing such a client-side connection manager. I'll check that later.

## Prior Art
[prior-art]: #prior-art

N/A

## Future Possibilities
[future-possibilities]: #future-possibilities

With this design choice we'll be freer to add more communication protocols support in the future.
