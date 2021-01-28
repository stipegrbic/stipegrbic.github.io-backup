title: My first iOS development experience
date: 2021-01-28 10:34:43
tags:
- iOS
- xamarin
- software development
---
Due to some circumstances, I came in a possession of a Mac mini. This meant only one thing - I had to create an iOS app. My way of thinking was, let's go completely native - Swift can't be that hard to learn. Create WatchOS app - I miss a lot of functionality on the Apple Watch. After some attempts and giving up I turned to the good old C# and Xamarin.Forms.
<!--more-->

### iOS native development

Yes, my idea was to create a basic app and was thinking just create a native app from the XCode template, and it shouldn't be too hard to learn Swift and SwiftUI in the process. The thing is, it's neither so easy and with my spare time very limited these days, I couldn't afford to go this way. In addition, my Mac mini is quite slow, and made the developemt (attempt) painfully slow.

### Xamarin.Forms

Ok, so I concluded it's better to go the faster way. Using my primary programming language and my primary development PC should speed things up. For a basic app I wanted to created Xamarin.Forms was a good fit, I didn't miss any functionality from native development. To be fair, the app I want to create was a port of one of my Windows Phone apps and I could reuse most of the bussiness logic code - speed++.

Using Xamarin.Forms for iOS on a Windows machine works. That's all :) it works, job can be done but there are a lot of obstacles a native development doesn't have. Connection to a Mac agent is unstable, often needs a machine restart and just like that you spend 10 minutes and work flow. Deploying to a simulator or a device works good enough, it is a bit slow, but doesn't get you nervous.

### Outcome

I created a complete app, but didn't submit it to the store due to it not being production ready, and my wish not to deal with everything that production involves - users, expectations, fixes and maintenance. The app required to have a push notification server, so I reused and expanded my [existing server](http://stipe.xyz/back-to-heroku) used for push notification with APNS support. Of course, since I didn't work on the server for a few years, Heroku wanted me to [migrate to the new stack](https://devcenter.heroku.com/articles/upgrading-to-the-latest-stack) before I could make new deployments.

Since I'm an iPhone, Apple Watch and iPad user, and I feel the need to be able to make an app for my own needs, now that I can do it the feeling is great. The unexpected work on the server also refreshed my Node.js knowledge and I felt satisfaction upon successful migration of the server.