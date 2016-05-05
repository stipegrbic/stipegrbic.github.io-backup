title: Xamarin.Forms hands on
date: 2016-05-05 21:59:03
tags:
- xamarin
- windows phone
- android
---
For some time I wanted to try Xamarin for multi platform mobile app development. Recently I got very basic app idea suggested by a friend and it looked like a perfect excuse to finally try Xamarin. Of course that Microsoft recent acquisition of Xamarin and giving the technology to developers for free gave me more reasons to do it.
<!--more-->

### Xamarin + Visual Studio

First things first, I installed Xamarin for Visual Studio and created a new project. In the solution there were Android, iOS, Windows 8 Store and Windows Phone 8.1 apps. I can't say I was surprised that there was no Windows 10 UWP app, even though I read there is support for Xamarin, maybe it's too early to abandon Windows (Phone) 8. I didn't read much of a documentation, but rather learned from code. There was one share component in which you can put all the shared stuff, from DB, networks calls to UI written in XAML. Since my app was so basic and I really wanted to make use of write once run everywhere slogan, I wrote a share page in XAML. There were some usual Android struggles, from installing the SDK, setting up the emulators, to `java.lang.OutOfMemoryError: Java heap space` error but eventually I got it working. When I realized I was writing C#/XAML code to run on Android it felt like magic, I couldn't believe this all works. But soon after I decided the app is ready for testing on a device, I just plugged it in and deployed from Visual Studio, it felt so natural. Just to mention I didn't try iOS because I don't have an access to a Mac. 

### OneSignal 

My app needed the push notifications service. I already imagined writing a Node.js service for this, but before I started that I investigated about existing services which I could use. OneSignal seemed like a good option, it provided the needed functionality, had good documentation, SDKs for many platforms and was free. I started to work with it, and didn't regret, I got push notifications working rather quick.

### Conclusion

Of course, main disadvantage of Xamarin.Forms is the number of UI controls you have at your disposal. This means Xamarin.Forms can't really be used for any advanced application with much UI customizations. And that's OK, for that purpose there's pure Xamarin where you can write UI natively on each platform. But for what it meant to be, a faster way to build simple apps for multiple platforms or a prototyping tool Xamarin.Forms works really well.

My most negative surprise was that Windows Phone was least supported by Xamarin.Forms. I mean, it's C#/XAML after all and one would expect it works the best for Windows, but when you think about it you can understand that there's no reason for Xamarin team to make extra effort to support Windows Phone developers who already can develop using C#/XAML. Their main target is iOS and Android and I think they've done a great job implementing all that stuff, from Mono, Google Play Services, I-don't-know-what for iOS, to UI layer and supporting XAML on all three platforms. 