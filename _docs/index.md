---
layout: docs
title: WireMock
---

WireMock is a flexible library for stubbing and mocking web services.
Unlike general purpose mocking tools it works by creating an actual HTTP
server that your code under test can connect to as it would a real web
service.

It supports HTTP response stubbing, request verification,
proxy/intercept, record/playback of stubs and fault injection, and can
be used from within a unit test or deployed into a test environment.

Although it's written in Java, there's also a JSON API so you can use it
with pretty much any language out there.

New new new! Version 2.0 in beta
================================

WireMock 2.0 is now in development. We're using the major version bump
to make a few breaking changes (but nothing too major, so don't worry!).

Among the changes we're making or considering are:

-   Dropping support for JDK 6 and 7, which allows us to use some newer
    libraries we previously couldn't.
-   Upgrading to Jetty 9.3, which is higher performing, and fixes
    some bugs.
-   Upgrading to JSONPath 2.0.0.
-   Improving the extensions API, probably to support transforming
    `Response` s directly in addition to `ResponseDefinition` s,
    but TBD.
-   Adding some additional type safety to the Java DSL.
-   Putting the standalone JAR under its own Maven artifact so it can
    have it's own POM (avoiding the need to exlclude all large swathes
    of dependencies).

If there's something you'd like to see added, particularly something
involving a breaking change, please post a topic on the [mailing
list](https://groups.google.com/forum/#!forum/wiremock-user).

If you'd like to raise a pull request (having discussed it on the list
first :-) please do so against the 2.0-beta branch, not master.

What's it for?
==============

Some scenarios you might want to consider WireMock for:

-   Testing mobile apps that depend on third-party REST APIs
-   Creating quick prototypes of your APIs
-   Injecting otherwise hard-to-create errors in 3rd party services
-   Any unit testing of code that depends on a web service

Who makes it?
=============

WireMock was created and is maintained by [Tom
Akehurst](http://www.tomakehurst.com/about).

The following people have been kind enough to submit improvements:

-   [Tim Perry](https://github.com/pimterry)
-   [Dominic Tootell](https://github.com/tootedom)
-   [mangotang](https://github.com/mangotang)
-   [Rob Elliot](https://github.com/mahoney)
-   [Neil Green](https://github.com/neilg)
-   [Rowan Hill](https://github.com/rowanhill)
-   [Christian Trimble](https://github.com/ctrimble)
-   [Aman King](https://github.com/amanking)
-   [Oliver Schönherr](https://github.com/oschoen)
-   [Jay Goldberg](https://github.com/carthoris)
-   [Matt Nathan](https://github.com/mattnathan)

Why shouldn't I just use my favourite mocking library?
======================================================

Mocking HTTP client classes in a way that adequately reflects their real
behaviour is pretty hard. Creating real HTTP exchanges alleviates this
by allowing you to use your production HTTP client implementation in
your tests.

Object based mocking isn't really suitable for acceptance/functional
testing scenarios. WireMock can be run as a standalone service or
deployed into a servlet container to enable it to be installed into your
dev/test environments.

I like the idea, but the implementation stinks/you've missed something I need/it's the wrong colour
===================================================================================================

Here are some alternative JVM based libraries with similar goals:

-   [Betamax](http://freeside.co/betamax/)
-   [REST-driver](https://github.com/rest-driver/rest-driver)
-   [MockServer](http://www.mock-server.com/)
-   [Moco](https://github.com/dreamhead/moco)

I couldn't possibly be seen using Java, I've got my image to think about!
=========================================================================

Luckily, [Rowan Hill](https://github.com/rowanhill) has built a [PHP
binding](https://github.com/rowanhill/wiremock-php), so you can bring it
to your next Shoreditch hackathon without fear of ridicule!

Contents
========
