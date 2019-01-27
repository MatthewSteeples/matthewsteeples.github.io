---
layout: post
title: 'App Services'
tag: AdventuresInAzure AppServices Azure
---

On the surface and at their simplest level, [App Services](https://azure.microsoft.com/en-us/services/app-service/) are a nice straightforward successor to Cloud Services. They give you slightly less control of the environment in exchange for even less management overhead. To describe them as simply as possible, they're basically hosted instances of IIS. Scaling up and down happens in seconds as opposed to minutes, and the "application" is managed separately from the "infrastructure" allowing you to have a crazy number (150) of applications running on the same servers. Obviously if you are hosting that many, you may want to pick the larger instance sizes!

Deploying applications has a lot more options as well; accepting packages, building automatically from source or various file synchronisation systems. 

There are quite a few additional administrative options that allow some clever use cases. One of these is Deployment Slots. This allows you to have a different version of your application, and seamlessly swap users between the two without any downtime. This can either be done all at once or as a gradual process (known as testing in production).

In true Microsoft style, these services integrate with others. You can deploy SSL certificates and store secrets in Azure Key Vault, you can use the CDN to move static assets closer to your users, and you can log the details of the errors, performance and general health of your application through Application Insights. 
