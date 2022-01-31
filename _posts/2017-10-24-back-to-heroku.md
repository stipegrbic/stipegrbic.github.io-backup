---
title: Back to Heroku
date: 2017-10-24 13:21:52
categories: [software development, node.js]
tags: [software development, node.js, backend]
---
A year and a half ago I moved my backend service from Heroku to Openshift. The reasons were that it didn't put services to sleep state in free tier. At that time it just looked it offers more for the same price. A month ago Openshift upgraded their service from version 2 to 3, or something like that. They wanted me to do the migration of my service. This is what happened next :) ...
<!--more-->
### Migrate!
I had little to no will to do any work for this service again. Especially the maintenance work which adds no features and was basically doing someone else's work. As it wasn't that important and hadn't that many users I was considering leaving the service to die. After a few days and email notifications from Openshift that I need to migrate, I decided to give it a try. 

Their tutorial was very short and at first I liked that, but only when I started working realized it's just a bad tutorial, short and inaccurate. So I digged deeper trying to understand what needs to be done. As the last step I needed to create a new database, which wouldn't be a problem if I didn't need to learn all their nomenclature and architecture. I remembered the same service I had been running on Heroku before might still be alive.

### To Heroku
Indeed, as I logged in to Heroku I saw my service was switched to maintenance mode. A simple button click put it to being active. An issue I had before with service being put to idle state after some time of inactivity I solved by using cron jobs as Heroku imagined it. After that I updated my client applications pointing to the new (old) endpoint and voila!

The reason for this post is to remember myself that I like Heroku better. To say that I want the software to live longer without needing for "migrations". This is something I don't like from the backend service providers, even though I'm using a free plan, would you please leave my service working as it was. And that was my main reason to do actual work, I felt sad seeing it die.

