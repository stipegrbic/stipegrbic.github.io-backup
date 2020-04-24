title: Data affects algorithm performance
date: 2019-09-25 13:37:59
tags:
- software development
---
The title is so obvious that you're probably wondering why I had to write a blog post about it. I'm also surprised how obvious truths must be repeated in order to comply with them. I'll explain what inspired me.
<!--more-->

### Optimize

Recently I got a task to optimize a piece of software I worked on. This was a part of code I inherited and wasn't so familiar with. In short, it had to process a list of data input, compute something and save the information to the database. So simple, right? Of course, it had some complicated computation in each iteration, but to my surprise that wasn't the bottleneck. The bottlneck was in the storing and retrieving data from database. It was done in each iteration because the previous one affected computation of the next one. So a developer before me decided to use the database as a single point of truth and on each iteration he saved the computed data, and retreived it again in the next iteration. For a short while I was angry with this unknown suspect and couldn't understand why would he do it like that. Then I realized, he couldn't see the actual slowness of the application because his database was probably almost empty. The actual customer has a lot of data in it, so in each iteration there's a lot of data to send and retrieve from database. That's when I got a bit of understanding for the guy, but also reminded myself, next time when I'm trying to write optimal code, have in mind the actual data might affect its performance.
