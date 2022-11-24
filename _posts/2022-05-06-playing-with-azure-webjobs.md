---
title: Playing with Azure WebJobs
date: 2022-05-06 10:45:30
categories: [software development, web]
tags: [azure, asp.net, backend]
---
In case you were following my posts, you are aware about my project [Days From Today](https://stipe.xyz/posts/my-first-asp-net-core-mvc-app/). It's a port of my Windows app which is much more functional, but it's still only a Windows app and I wanted my web version to be as functional as a Windows app. This time I tried to add email reminders about events.
<!--more-->

So, the Windows app has a functionality that it can notify you about your events with a scheduled notification. This is great but as I noticed, I'm sitting by my PC 24/7 and this means I might miss some notifications. To avoid missing some important event notification, I had an idea to have my web version of the app send an email reminder for an event. I coded the CRUD operations to subscribe for event reminder emails, integrated an email sending service and it all worked nice and I was happy :)

Then, I needed my web app to do this on a schedule. Each day check if there's any event with a reminder and send an email if needed. I learned about Azure WebJobs and Function Apps. Created such a WebJob, it worked and I was still happy. Then I noticed WebJob triggers don't work in a free-tier app. Ok, I was ready to cancel everything, as I don't have intention to pay anything for this hobby project. Then I found this [blog post](https://medium.com/@patrick_abel/a-poor-mans-approach-for-scheduling-azure-web-jobs-f46e0f4fcdb3) and found out there's a workaround to this limitation. So I created a Function App which would run on a schedule and trigger my WebJob which would send emails. It worked and I was happy :)

Then, I noticed Function App requires Azure Storage account. I checked its pricing immediatelly and noticed there's no free storage. As little as it could be, anything higher than 0 is too expensive for this app. This was a moment I realized it's not worth it. I was anyway hesitant to add many services to Azure and then live in fear of unexpected costs. So the app is back to it's initial functionality, calculating days from today. 

At the end, I'm not happy I had to shut it down, but I'm not sad either. I learned quite a lot during these two days of hobby development. It's sad that Azure has such limitations, I'm sure they could have such functionality which doesn't cost anything if only they provided it. Probably they don't think about simple use cases like this as it's not something production apps need. Anyway, email reminders will have to wait for better times when Azure would provide free scheduled background tasks.