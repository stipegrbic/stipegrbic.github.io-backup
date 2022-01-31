---
title: Be careful with cache
date: 2017-11-29 14:49:03
categories: [software development, opinions]
tags: [software development, opinions]
---
There's a well known saying that goes like this: There are only two hard things in Computer Science: cache invalidation and naming things *. This is a post about the first one.

Today I experienced a cache invalidation issue where I was presented with cached data instead of a fresh data which was different. This prevented me from fixing an issue which only my colleague discovered and for a minute we were confused with what was happening.

This just remembered me to be careful next time when I'm thinking about caching things. It's extremely important that you know when to invalidate cache. If you don't determine that moment correctly you are about to put a nasty bug in your product and frustrate your users.

\* [https://martinfowler.com/bliki/TwoHardThings.html](https://martinfowler.com/bliki/TwoHardThings.html)
