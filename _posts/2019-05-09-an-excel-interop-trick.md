---
title: An Excel interop trick
date: 2019-05-09 12:10:04
categories: [software development, windows]
tags: [software development, windows]
---
Yesterday I had a nice little evening spent with a silent failure of my program. The program needed to create an Excel document, save it and export as a PDF. It should also run periodically and automatically, so as a scheduled task right? Yes, and it works fine for me on my Windows 10 PC, but on clients Windows Server 2012? Not really.
<!--more-->
### What's wrong?
First thing I saw is that Excel file was created, but PDF wasn't. The Excel file was still in use by an Excel program in background. My scheduled task was still shown as running, and log files didn't have any new lines after creating Excel file. It meant export to PDF method failed, but why?

I browsed the web and found a lot of complaints and users telling that you can't automate Excel with a scheduled task without a user logged in. It made sense, but my task could open Excel, generate a file and save it. It's just that when it tried to export it to a PDF it halted. And only when ran unattended, meaning when no user is logged in.

### The printer
I can't remember all the things I tried to workaround this problem, but after a few hours I got to this [StackOverflow question](https://stackoverflow.com/questions/10272415/excel-exportasfixedformat-pdf). There was that one answer that pointed that Excel is not able to print to PDF and I should set Microsoft XPS document writer as a default printer. So I tried that and it worked! These kind of problems make you feel alive and put you out of your comfort zone writing those lines of code :)


