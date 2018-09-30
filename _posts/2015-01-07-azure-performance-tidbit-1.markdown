---
layout: post
title: 'Azure Performance Tidbit #1'
tag: 
---

I've got a side project that is using Azure Tables as it's primary datastore. I've been importing records into it from CSV files for a month or so now and was curious to see how many records were in there. There isn't a built in Count() function in Azure (yet) so I wrote a small WebJob that would count the number of partitions and the number of records in my tables. It took about 10 minutes to write (including the use of projections to reduce the amount of data that it needed to parse) and then I set it off going... and waited...

19.5 hours later and it's finished. Sounds like a long time, but bear in mind that it had to read all of the records from the table and send them over to the Webjob in order to count them. There were 446,254,376 records spread over 30,643 partitions, which equates roughly to 6,300 records per second!

As a rough estimate, running that count will have cost me £0.01 (that's not a typo) as Azure charges £0.0022 per 100,000 data transactions. The Data storage itself is a bit harder to work out, but I'd estimate that at about £10.20 per month (approx 175gb at £0.0581/gb). A lot cheaper than if I was running that myself!