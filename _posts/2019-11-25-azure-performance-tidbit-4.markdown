---
layout: post
title: 'Azure Performance Tidbit #4'
tag: Scriptlist AzureTables
---

One of the benefits of running in the cloud is that someone else manages (and upgrades) the hardware for you. When I last blogged about this in 2015 it took 4 hours to import the 10 million rows. With no significant changes to my code (there's only been the odd feature here and there, no more optimisations have been done) a single server now imports this data in 2 hours and 8 minutes. That's an average rate of nearly 3000 records inserted per second. The cost hasn't changed either!
