+++
title = "This Week in Ruma"
date = 2016-05-22
extra.author = "Jimmy Cuadra"
+++

## From the editor

Lots of progress this week!
As expected, I finished the `/login` endpoint, so I can now move on to the real stuff: rooms and the event stream.
This week also saw two nice milestones:
Ruma's first pull request was merged, and I successfully registered an account with a locally running Ruma server via a locally running [Vector](https://vector.im/) client.
(The latter also uncovered an undocumented API that Vector was attempting to use which I've brought up with the Matrix team.)

Before taking the plunge into rooms and events, I'm taking some time to think and plan about how to structure the data, and have been talking with the Matrix team about how Synapse handles things, lessons learned, and the trade offs of different approaches.
A few months ago, Erik Johnston of the core team wrote up some [notes on data storage in Matrix](https://gist.github.com/erikjohnston/ae60767679278c0c4519) which has been very useful in this planning stage.
It's a great read if you're interested in some of the tricky issues in Matrix development.

There was also a little discussion on how difficult it is to represent certain JSON structures in the API as Rust types.
There are several data structures in the API that are effectively enums, but can't be automatically deserialized by Serde because of two things:
[how Serde currently handles enums](https://github.com/serde-rs/serde/issues/251) and the fact that variants can only be determined by examining the values of some of their fields.
The latter currently requires manual implementation of deserialization, which gets cumbersome very quickly.
The way I'm probably going to address this is to deserialize these types of data structures to an intermediate type so simple deserialization from JSON can be separated from higher level detection and validation logic.
To that end, I built the [validations](https://github.com/jimmycuadra/validations) library, which provides both an interface for validating a type, and types for representing validation errors.

## Notable changes to `ruma`

* Finished a simple working version of the `/login` API endpoint.
* Added [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) support to all endpoints.
* Reexported the Iron handlers for API endpoints from their parent module to make imports a little less verbose.
* Renamed the `FinalConfig` type to `Config`, and the previously named `Config` to the now private `RawConfig` type.
* Revised the README with full documentation of the configuration file's format along with some other improvements.

## New contributors

* [Johannes Oertel](https://github.com/jooert)
