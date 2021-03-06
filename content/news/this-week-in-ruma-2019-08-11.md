+++
title = "This Week in Ruma"
date = 2019-08-11
extra.author = "Jimmy Cuadra"
+++

## From the editor

I did another live stream of Ruma development on [my Twitch channel](https://www.twitch.tv/jimmycuadra) this past week.
If you missed it, you can watch [the recording on YouTube](https://www.youtube.com/watch?v=vfMvGWCBkVI).
In the stream, I worked on another revision to the [ruma-events](https://github.com/ruma/ruma-events) API in which a special result type was introduced to handle deserialization/validation errors.
[Jonas](https://github.com/jplatte) quickly discovered, upon trying to update [ruma-client-api](https://github.com/ruma/ruma-client-api) to ruma-events 0.10, that the new deserialization API didn't quite work and that further changes were needed.
I updated all the manually events to the *new* new API, but the events generated by [ruma-events-macros](https://github.com/ruma/ruma-events-macros) still need to be updated.
I will do that on the next stream in the coming week.

A couple weeks ago I recorded an interview with the [Rustacean Station](https://rustacean-station.org/) podcast, and today the episode was released.
You can find it here: [Ruma and the Matrix Communication Protocol: An Interview with Jimmy Cuadra](https://rustacean-station.org/episode/001-ruma/).
A huge thanks to Ben Striegel and Jon Gjengset for starting the podcast, and to Ben and Abdou Seck for taking the time to record this episode with me.
It was a good time, and I hope it gets some new people interested in Matrix and/or Ruma.
