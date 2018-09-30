---
layout: post
title: 'Azure Performance Tidbit #2'
tag: 
---

Continuing on with the aforementioned side project, I tried some scaling up. I'd made a mistake in the design of the table so it was easier to bin it all and re-import it. I decided to see if running the imports in parallel would speed things up, and I was not disappointed!

Running a single instance resulted in importing 10 million rows in approximately 4 hours (roughly 700 records per second). I spun up a couple more servers and let the import carry on going and the import time remained at 4 hours! I know obviously that won't scale linearly and infinitely but for my needs it meant that I'd just slashed the amount of time I had to wait by two thirds and I was getting an **average** throughput of 2100 rows per second! Due to the nature of "Pay as you go" in the cloud, I'd also done this without really increasing my costs! Running 3 servers for 4 hours costs the same as running 1 server for 12 hours.

I'd made this change to improve the query performance, as defining your keys is something you need to do in the beginning and can massively affect the speed at which you retrieve data out of it. The queries that I'm running on this data usually involve about 410 requests and return 33,000 records. With my old design this took about 30 minutes, which works out at 19 rows per second. Not bad (considering the size of the dataset) but at the same time not great. After the re-design the data comes out in 78 seconds! That's an average of 425 rows per second.