---
layout: post
title: Online Service Apologies
tag: 
---

Both at work and not at work, I believe in having as much as possible in the cloud. Recently that's been a little problematic as SharePoint Online has been experiencing some outages. That in itself I don't have a problem with. Just as software has bugs, services will occasionally go offline, and these services have spent less time offline than if I was maintaining them myself. What Microsoft endeavour to do well with these services is keep a service dashboard up to date with any incidents that are ongoing, and publish post-incident reports (PIRs) afterwards to explain what went wrong, why it happened, and how they're going to stop it from happening again.

While this may seem like a really good idea, the execution leaves a bit to be desired. They get the first two pretty spot-on as far as I'm concerned, and then the third one is always a bit wishy-washy. Here's some examples:

Finding(s): A portion of server capacity that hosts the Domain Name System (DNS) service was unresponsive.  
Action(s): Further investigate the affected capacity to determine why the servers became unresponsive and help prevent a re-occurrence of the scenario.

Finding(s): An update to the environment unexpectedly introduced a configuration issue on a portion of capacity that delivers content to customers.  
Action(s): Resolve the issue of missing certificates; review the infrastructure update process to prevent re-occurrences of this scenario.

Finding(s): A limited portion of capacity that stores SharePoint Online site content was in a degraded state.  
Action(s): Further investigate the affected capacity to identify the cause and help prevent a re-occurrence of the scenario.

Finding(s): An update to the environment unexpectedly disabled a property that displays the picture for the user account profile.  
Action(s): Review the infrastructure update process to determine how the issue was introduced and prevent re-occurrences of this scenario.

The findings are a summary of what is usually quite a detailed and insightful diagnosis, and the actions can all be summed up as "stop it happening again" with the occasional "we still need to work out why this is happening".

In summary, I think there's scope for them to do better when reporting these issues. The quality of the service is good overall, and obviously any downtime is frustrating but it would be less frustrating if we got confirmation that these issues are being learnt from.