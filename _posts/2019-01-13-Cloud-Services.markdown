---
layout: post
title: 'Cloud Services'
tag: AdventuresInAzure CloudServices Azure
---

Azure was brand new when we started our project, and it made sense to take advantage of it for a greenfield development. [Cloud Services](https://azure.microsoft.com/en-us/services/cloud-services/) were the only way of hosting applications, and they fit our requirements perfectly. They're not popular anymore, and although they're still offered they have been pretty much phased out with more up to date offerings.

The basic overview of them was that you had a VM preconfigured with Windows and IIS, and you packaged your application up for it to be deployed through the Azure Portal. You could scale up and down with about 25 minutes notice (the time it took to allocate a new VM and deploy your package to it). If you were coming from the traditional ASP.NET application background then there were very few changes that you needed to make for compatibility.

Background tasks were handled by Worker Roles, which were basically VMs that just ran an executable. We didn't really make use of these, and instead ran code in a separate thread on our Web roles to keep costs down. 

The system itself required next to no maintenance. Everything was preinstalled and Windows Updates were applied automatically each month. High availability meant having 2 instances running, so the main shocker for most people was moving away from Session State. Deploying a new version of your application could use separate deployment slots so you could "stage" them and make sure they worked fine, or you could roll out your changes to half of the cluster and then swap over. 

It was definitely a good start into the world of Platform as a service, but the functionality it offered has (for us at least) been replaced by 3 other complementing services. 

Details of them are to follow...! 