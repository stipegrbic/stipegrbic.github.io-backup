---
title: Blocked? Prepare to unblock
date: 2020-07-05 20:15:04
categories: [software development, opinions]
tags: [software development, opinions]
---
Many times during my career I’ve been blocked from completing my work. Be it feature implementation, bug fix or some kind of software migration I couldn’t finish until someone else does their job first. What to do during this time? 
<!--more-->
I learned that you can’t just say “I’m blocked and can’t do anything until I get unblocked” because there’s so much you can do to prepare for when you get unblocked. Let’s say you are implementing a new feature and need to get the data from server. This new feature is also new for server and it doesn't have the API you need right now. Instead of waiting or annoy server developers with constant pinging you could prepare for the moment API gets implemented. The goal is to have the least possible amount of work remaining to complete your feature. In this example you could use the time to create tests for your feature before implementation (remember the TDD?). While writing tests you’ll probably need to make some mock data. With mock data you can already continue implementing the feature and get it close to completion. With this approach not only you’ll be faster to complete the feature once you get unblocked, but your implementation will already have covering tests.  