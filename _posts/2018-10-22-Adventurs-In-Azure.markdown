---
layout: post
title: 'Adventures in Azure'
tag: AdventursInAzure
---

The day job involves a lot of cloud computing (our server bill is our second biggest cost after people) and we like to stay ahead of the curve where possible. We've been in Azure since the beginning with this project, and it's enabled us to develop and scale quickly, using fewer developers and IT professionals than if we were looking after it all ourselves. It hasn't always seemed as straightforward as we'd have liked it to be, so this blog is going to give a bit of history and documentation into our processes.

Here's a fairly comprehensive list of the Azure services that we make use of at the moment (in no particular order):

* App Services
* WebJobs 
* Sql Azure 
* Blob Storage
* Table Storage 
* Queue Storage
* Service Bus
* Virtual Machines
* VPN (and Gateway)
* DevOps
* Redis
* Batch
* Functions
* Key Vault
* Application Insights
* Azure AD
* CDN
* Bot Service

For the most part, each item in the list above represents something that we didn't have to code and, beyond the initial consultation, we don't have to maintain. Vendor lock in is always a concern and something we take into consideration, but for the most part the services are the correct size that if we want to replace them with something else then we can do.

There are also some pieces that we used to use but don't anymore for various reasons:

* Cloud Services
* Automation

Additionally,there are a few Azure services that we've evaluated and not chosen, and I think the stories behind them are just as valuable:

* DNS
* CosmosDB 
* Containers
* Service Fabric
* Traffic Manager
* Event Grid
* Azure AD B2C

Usual disclaimers apply, your mileage may vary etc