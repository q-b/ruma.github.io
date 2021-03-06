+++
title = "This Week in Ruma"
date = 2019-07-14
extra.author = "Jimmy Cuadra"
+++

## From the editor

In the [last update](/news/this-week-in-ruma-2019-07-07/), I mentioned that the ongoing ruma-events revamp was impeded by an issue with types from *ring* which don't implement `Clone` and `PartialEq`.
It turns out that there is [a reasonable explanation for this](https://github.com/briansmith/ring/pull/727), and so it was decided to work around it.
I restructured the ruma-signatures types in question so that they don't contain *ring* types, but simply construct them and use them as-needed in the relevant methods.

While I was working on ruma-signatures, I decided to fill in the missing functionality—signing and verifying events.
In the process of doing that, I ended up with a significantly revised API for the crate, which has now been released as [version 0.5.0](https://github.com/ruma/ruma-signatures/releases/tag/0.5.0).
In a somewhat amusing development, the new ruma-signatures API doesn't include the `Signatures` and `SignatureSet` types that were causing the issue in ruma-events in the first place.
As a result, ruma-events is not only unblocked, but doesn't have depend on ruma-signatures at all.

I made a little bit more progress on ruma-events.
There is only one module remaining to be updated to the new API, so we're on the home stretch for a new ruma-events release.
