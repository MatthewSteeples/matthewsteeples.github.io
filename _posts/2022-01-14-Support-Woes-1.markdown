---
layout: post
title: 'Support Woes 1'
tag: Support Azure CDN
---

A journey through Microsoft's support channels today. I think I'm yet to have a positive experience with a Microsoft support representative, mainly because it seems like none of them have been told what the products do. Today's communication is a perfect example of this.

We make use of [Azure CDN](https://azure.microsoft.com/en-gb/services/cdn/) to cache static assets close to our users. Arguably, that's the main purpose of a CDN. Recently, it stopped working and started displaying an error message with a few identifiers on it (which look like they should be useful for diagnostic purposes), so I raised a case with support.

After telling me that it was all fine and there were no problems (it would appear that this issue isn't affecting _all_ CDN servers, but happens to affect one near me at least), I sent them a [HAR Trace](https://docs.microsoft.com/en-us/azure/azure-web-pubsub/howto-troubleshoot-network-trace) which was nice and simple to do. They then came back to me (after doing some digging) and said that it was a problem retrieving the content from the source, and purging the cache should fix it.

That didn't work, so the next step was to disable caching entirely (by configuring a rule in the CDN portal). That stopped the error message from appearing and rendered the content. I informed them of this and asked them what the next steps were. The response made me laugh (and not in a good way):

> It is good to know that Issue is resolved now. For the next action plan, You can keep the configuration as it is configured now.
> Please let me know if you have any further queries.

Yes, the error message no longer appears, but I may as well not be using the CDN anymore because it's not caching anything! This went backwards and forwards for a couple of weeks before we gave up using the CDN altogether. It's just not worth the hassle.