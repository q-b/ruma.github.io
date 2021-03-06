+++
title = "Ruma is dead, long live Ruma!"
date = 2020-04-10
extra.author = "Jonas Platte"
+++

Today, I have a bit of a sad announcement to make:

## Ruma, the homeserver, won't be developed anymore

To those who have actively been following the project, this probably won't be a
big surprise, given the homeserver's readme file was already update do note the
missing maintenance and people interested in contributing to the homeserver have
now gathered around a new homeserver project by the name of [Conduit][].

The main reason for ending homeserver development is that nobody who has
previously worked on its codebase is currently able to guide and review work on
it. The codebase has also bit-rotted a lot, with the web framework it uses being
almost un-maintained and a number of its other dependencies having seen major
new releases since the most recent commit; it also doesn't build on
ruma-client-api, for the simple reason that ruma-client-api simply didn't exist
yet when most of the homeserver work happened.

However, the end of the homeserver does not at all mean the end of Ruma, the
overall project.

## The future of Ruma, the project

We will be continuing work on our library crates, making sure they are usable
for all kinds of applications, including homeservers. The new homeserver project
mentioned at the beginning is based on them and some other folks are currently
working on [a highlevel client library][matrix-rust-sdk], also using many of
Ruma's library crates.

I am planning to replace the current website with a new one, mostly for
technical reasons, but the new one will also reflect our changed focus. This
work hasn't started yet, but in the interim I will likely update parts of the
current site. Other than that, nothing will really be different compared to last
year.

[matrix-rust-sdk]: https://github.com/matrix-org/matrix-rust-sdk

## If you are still interested in a Rust homeserver

… then check out [Conduit][]. It is a Matrix homeserver, written in Rust using
Ruma's library crates. It is focused on experimenting with new ideas to achieve
better performance, for example by using [sled][] as its database. The goal is
to make it as easy as possible to set up your own homeserver.

[Conduit]: https://conduit.rs/
[sled]: https://sled.rs/
