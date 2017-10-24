title: My first Node.js experience
date: 2015-10-26 20:20:25
tags: 
- node.js
- backend
---
Recently I got a requirement to create a proof of concept web application. Something not too complicated, two types of users can register, login and after that enter and view some data with file upload/download functionality. There was also a requirement for an admin page which can view and approve registered users. I had my hands free to choose the technology and tools to build it. Oh, and did I mention the deadline was in four days?
<!--more-->

### Possible solutions

Since I had experience in Java web development and .NET client development and I like to say I'm technology agnostic, I was open for anything that would best suit the need. After some examination, I ended up with three options: Java, ASP.NET and Node.js. I always wanted to try Node, but didn't think this was the right moment when I had less than four days to complete the project. And while I personally like the C# language the most, I didn't work with ASP.NET. But the reason to dismiss it wasn't that, but the fact I wasn't able to create a free trial account on Azure, even if I gave my credit card number. Platforms like Heroku usually don't support ASP.NET and I wasn't ready to pay for hosting of an app that was only an MVP.

For all these reasons I decided I'd try Play framework using Java. Their documentation looked nice and it seemed I could do the job fast and easy using the language I know well. So I created a new project and followed the guidelines to get it configured and start working. But soon I ran into typical Java problems, I was stuck in project setup, configuration problems, guidelines didn't work for me, something somewhere wasn't installed properly. After fixing one problem, another would come up and I soon realized I could loose a lot of time just to get the project started. That's when I decided I would give up on Java and try this hot new thing – Node.js.

### Node.js

I did know the theory behind Node.js, I also had some experience with JavaScript, but I was ready to learn a lot of new things. I started by following Heroku guidelines and had the project set up in a few minutes. I was really amazed how little code was needed to get the application running. I decided to concentrate on front end and didn't bother with data persistence at first. I liked the Jade template engine and was able to do stuff quickly even if I haven't seen it before. After I had the routing and screens set up, I turned to find a solution for data persistence. I knew there was a MongoDB option which works good with Node.js applications, but I thought a good old SQL would fit the need the best. Another reason was that I had enough new technologies for these few days. So I chose the PostgreSQL database and Sequelize ORM. I was able to get it working very fast, but I wish Sequelize had a better documentation. The Heroku part was easy enough, creating a database and connecting to it was all done in a few minutes.

So there it was, a production ready application built in four days in technologies I didn't work with before. I don't have to say I felt proud and also happy that Node.js exists and only look forward to building more applications like this. Well, with more reasonable deadline if possible.