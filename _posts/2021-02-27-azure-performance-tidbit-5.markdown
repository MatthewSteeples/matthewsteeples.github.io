---
layout: post
title: 'Azure Performance Tidbit #5'
tag: Scriptlist AzureTables
---

Following on from [#4]({% post_url 2019-11-25-azure-performance-tidbit-4 %}), the speed has dropped yet again. The dataset size is the same as it was 12 months ago, but the database it's importing into now has a billion rows in it. It now imports 10 million new rows in 1 hour 14 minutes, giving an average speed of 2200 records/second

