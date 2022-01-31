---
title: My first ASP.NET Core MVC app
date: 2020-07-08 22:23:50
categories: [software development, web]
tags: [software development, web]
---
As you might have noticed I created a Windows application to calculate time span between two dates [Event Timing](http://stipe.xyz/my-work/). Since I'm not always sitting by my Windows PC, I got the need to have this little calculator app available on the web. This evening the web app went from idea to production. 
<!--more-->
The most important motivation for this application was to quickly calculate how old is my baby in days. For this my Event Timing app worked great, with notifications, live tiles and all that, but with one major limitation that it was only available on Windows. Now since I'm spending more time with the baby, I'm not that much by the PC anymore. My phone is always near and I concluded if my application was available as a web app I could easily check the baby's age in days wherever I am. This and my long time desire to try make an ASP.NET web application made me spend a few hours this evening to create this application.

Known limitations:
- It doesn't support different time zones. It always calculates based on UTC time.
- Date format is not based on user's region. Date format in the input field is formatted by users browser. The date in calculated page is formated in dd/MM/yyyy format as I think most of the people use that format.

\[UPDATE\]
The application is no longer available as I didn't want to start an Azure subscription. I'm sorry to end it like this, but the application was never meant to be maintained, or improved. It served its purpose of getting me learn a bit about the technology.

\[UPDATE 2\]
Application is live again. I decided to start an Azure subscription and avoid unnecessary costs. The app is available [here](https://daysfromtoday.azurewebsites.net)