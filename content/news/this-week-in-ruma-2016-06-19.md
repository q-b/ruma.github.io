+++
title = "This Week in Ruma"
date = 2016-06-19
extra.author = "Jimmy Cuadra"
+++

The effort last week to make it easy to identify ways to contribute to Ruma has already paid off with two new API endpoints being implemented by the community this week!
Leah and I finished a draft of the "introduction to Matrix" document that will appear on the forthcoming Ruma documentation website, and we are very pleased with it.
Hopefully everyone who reads it will find it useful in understanding Matrix (and those who already understand Matrix well will get some new ideas about how to explain it to the uninitiated.)
The documentation section for the website now exists on a Git branch, but the content isn't filled in quite yet.
The Matrix guide is probably another week or two away, as we still need to proofread the draft of the overview and create the other documents (a feature overview and a long-form explanation of what problems Matrix is intended to solve.)

## Notable changes to `ruma`

* Added `GET /directory/room/:room_alias` endpoint. (Contributed by Johannes Oertel.)
* Added `DELETE /directory/room/:room_alias` endpoint. (Contributed by Lee Hinman.)
* Updated the development setup to run entirely in Docker containers.
* Started running Ruma's test suite on Travis CI.

## New contributors

* [Tor Hveem](https://github.com/torhve)
* [Lee Hinman](https://github.com/dakrone)
