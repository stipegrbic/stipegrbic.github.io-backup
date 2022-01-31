---
title: Working with manipulation events on Windows Phone
date: 2014-10-22 20:10:37
categories: [software development, windows phone]
tags: [software development, windows phone]
---
Recently I worked on a Windows Phone app that had to allow users to move objects on the screen. More precisely, users would need to drag images on either left or right side. So, I just went by putting Image into a Border with CompositeTransform and then listened to Manipulation events. The thing I noticed is that it just isn't really smooth, had a lag and I didn't want users to have that experience. 
<!--more-->

Then I tried another method, using the Touch.FrameReported event as I read it is a lower level API and should work smoother. The results were better, but still not perfect, and I knew there had to be a better way to do it as I saw other apps which had it done right. After looking into a source code of a few samples I found, I came across the [WPToolkit](https://phone.codeplex.com/SourceControl/latest) source code and samples. Then looking into a GestureSample I found a comment inside .xaml file: 

> Unlike in the WP7 toolkit sample, these event handlers need to be on the containing grid, rather than on the element itself, because calculations for these events are done within the coordinate space of the element, rather than screen coordinate space, which will create incorrect values compared to the user's expectations when the element has been scaled or rotated. 

So there it is, because of a change between WP7 and WP8 and moving from GestureListener in WP7 Toolkit to built-in gesture events in WP8, this had to be implemented a little bit different. After applying changes to my code the results were just perfect. Perfectly smooth dragging of images, just as you would expect on Windows Phone.

I'm not sure if this change is documented anywhere in the official documentation, but sometimes it's not bad to look directly into source code and see how it works.