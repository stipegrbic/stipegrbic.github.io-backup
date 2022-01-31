---
title: Sending push notifications with Google App Engine
date: 2014-05-01 20:17:48
categories: [software development, windows phone]
tags: [software development, windows phone, google app engine, backend]
---
When I built a Windows Phone application for local weather forecast it was naturally to implement push notifications – because you know how hard it is for users to manually check if new weather information is available. So, the question was how to do it – simple, fast and for free?
<!--more-->

### Solution

There's a service from Google called App Engine which enables you to make web applications in Java or Python and host them on their servers for free. There are a lot of constraints which they had to make in order to make it free to use for everyone, but for application of this purpose there weren't too many obstacles to make it work.

### Problems

I won't write about building a web application here, but rather about a problems I came across. So, once I've made it and put it to service it was working OK before first problem came up – a request to send notifications was taking too much time. Google App Engine runs applications in a sandbox environment which means you don't have much freedom there. The constraint that was a problem was that each request has only 60 seconds to finish before it's terminated. As I knew that sending a notification usually doesn't take too long, only a fraction of a second I was thinking that even with thousands of users it shouldn't be a problem. But, as I looked at the logs I saw that sometimes it takes a few seconds and then it fails. That's when URL is not available and notification is not possible to send. There's nothing you can do about it because Microsoft is responsible for delivering notifications to users. But here are a few things you can do about this problem:

- When a notification URL of a user changes, delete old URL. Not only because it will clear unnecessary data, but it will also make sending notifications faster because your server won't be trying to send a notification to an old URL.

- Use asynchronous requests. All requests to external resources go through URL Fetch service, but it allows you to fetch URLs asynchronously. You should use that feature not to block your thread when calling thousands of notification URLs. One thing to remember is that a request has only 60 seconds to finish and no thread cannot outlive a request that started it.

- Don't delete URLs that failed once. I thought that URL that failed is safe to delete because it's not working and it's probably some old URL. That was wrong as it lead to deletion of a lot of URLs that were active and users couldn't receive notifications until their URL changed.

In general Google App Engine works great for this purpose. It's simple to use, reliable and free, but it has quite a lot of limitations which could make a problem for some other application. This is understandable because even Google doesn't have unlimited resources and when you use something for free, you don't really have the right to complain about it :)