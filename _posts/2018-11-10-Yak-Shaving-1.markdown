---
layout: post
title: 'Yak Shaving 1'
tag: TechnicalDebt Managing
---

One of my team came to me the other day and said that the amount of "issues" that we're having to deal with on a daily basis was starting to mount and we were spending as much (if not more) time trying to get our own environments working as we were furthering the product.

It's quite amazing how much time these things can take up. An Assembly Binding Redirect can easily take 20 minutes of your time, not to mention the associated context switch when you have to stop working on what you were planning on debugging and fix the issue before you can carry on. Do Not Pass Go, Do Not Collect £200. There's a list of things that have been getting to us recently, and it's all part of growing up and becoming a larger team.

One issue which has bitten us recently which I always thought was a bit of an "overhead" in larger companies and had mostly gone away is "development dependencies". Now this isn't a case of libraries in your project (as that has mostly been solved by NuGet) but what tools and frameworks you need installed on your development machine. The specific case we encountered is the ".NET 4.5.2 Targeting Pack". This is a required component for doing any CRM SDK work, and needs to be deployed on each developer machine to open up the projects. Communicating this out to developers in an efficient way is quite tricky. We use a management system that allows us to remotely deploy software, but it doesn't appear to work as well as you'd hope and diagnosing issues with it can frequently take longer than manually installing the apps themselves.

Basically, the environment for developing software is constantly evolving, and the tooling at the moment doesn't seem to be well equipped to handle frequent small changes.