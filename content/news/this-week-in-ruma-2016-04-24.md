+++
title = "This Week in Ruma"
date = 2016-04-24
extra.author = "Jimmy Cuadra"
+++

## From the editor

I said last week that there wouldn't be an update this week because I'm on vacation, but as it turns out a bit of progress was made before I left and I have a few minutes to make the update while my partner writes postcards to send back home.

## Notable changes to `ruma`

* Add initial stub implementation of user-interactive authentication.

  Matrix's interactive auth system is in a bit of a transition, so there has been lots of investigation and discussion with the core team to learn how it works.
  I was able to make some good progress on how it will be represented as Rust code, but there are many more changes to come.
  I hope to have "dummy" authentication working soon.

## Matrix at large

Many of my questions about the specification have been answered, thanks to Richard van der Hoff of the Matrix core team.
A few issues are ongoing, but all of this discussion will be very helpful in improving the specification and clarifying some flows so that Ruma can implement them.

Specifically:

* [SPEC-385](https://matrix.org/jira/browse/SPEC-385): PUT requests should use the JSON body for all request parameters

  Came to agreement that, at least for the `/register` API endpoint, request parameters related to the registration should not be split arbitrarily across the query string and the body of the request.

* [SPEC-343](https://matrix.org/jira/browse/SPEC-343): Explain the purpose of refresh tokens

  Clarified why Matrix authentication involves both "access tokens" and "refresh tokens," where implementations are free to make their own choices, and the trade offs involved.

* [SPEC-313](https://matrix.org/jira/browse/SPEC-313): Provide a high level overview of the different event syncing API endpoints

  Ongoing discussion of which APIs are used by the client to get events, and how best to update the spec to make recent API deprecations more clear.

* [SPEC-310](https://matrix.org/jira/browse/SPEC-310): Consider renaming "state key" to "subtype" and making it optional

  Ongoing discussion of the semantics of Matrix's "state events," as well as discussion about how to balance the quality of the spec with the need to make progress on implementations.

* [SPEC-308](https://matrix.org/jira/browse/SPEC-308): Authentication API is unclear/misleading

  Ongoing discussion about how the user-interactive authentication system relates to specific API endpoints that use it, like `/register` and `/login`.
