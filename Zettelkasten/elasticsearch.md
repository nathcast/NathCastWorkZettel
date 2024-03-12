202311211318
Status: #notes
Tags: #elasticsearch #digital 

# elasticsearch

Hi Stephen,

I’m glad to hear you’ve found it useful – getting across the message out that there are better alternatives to multiple Excel files is still difficult!

Elasticsearch is on the todo list with us and IT, but we’re limited by the amount of staff time free to play around with these resources. There are also other alternatives from standard SQL databases to cloud data integration platforms like Snowflake we could potentially look at. Plus there is also cost to factor in and cloud services especially can ramp up very quickly. Elasticsearch is just one tool among many for wrangling data, and if my team are costed into projects we can help with this.

Two other things that we are looking at are iRODS (federated data management software – currently used at EI and looking to set-up an instance here to improve data sharing, especially for very large datasets, within DSW) and CKAN (open source data repository+ - allows datasets publishing _and_ direct data access via APIs). I believe both these platforms can integrate with Elasticsearch.

Cheers

Richard

**From:** Stephen Pearce <[stephen.pearce@rothamsted.ac.uk](mailto:stephen.pearce@rothamsted.ac.uk)>  
**Sent:** 17 October 2023 08:00  
**To:** Richard Ostler <[richard.ostler@rothamsted.ac.uk](mailto:richard.ostler@rothamsted.ac.uk)>  
**Cc:** Nathalie Castells <[nathalie.castells@rothamsted.ac.uk](mailto:nathalie.castells@rothamsted.ac.uk)>  
**Subject:** Elasticsearch for biological datasets

Hi Richard (cc Nathalie),

I'm forwarding below a message I sent to Francois Belleau, who presented a seminar at Rothamsted a couple of weeks ago on his recent paper about business intelligence tools for biological data (PDF attached). 

During his visit Francois showed me how to set up an ElasticSearch instance and we integrated some of my datasets on wheat gene information which worked well for custom searches. Hosting the Elastic Search instance comes with a monthly subscription fee, but for now I'm just using the free trial period. 

I'm not sure how broadly something like this might be useful at Rothamsted, but perhaps is worth considering for large projects or groups of researchers. 

Thanks,  
Stephen

**From:** Stephen Pearce <[stephen.pearce@rothamsted.ac.uk](mailto:stephen.pearce@rothamsted.ac.uk)>

**Sent:** 12 October 2023 15:51

**To:** [francois.belleau@gmail.com](mailto:francois.belleau@gmail.com)

**Cc:** Nathalie Castells <[nathalie.castells@rothamsted.ac.uk](mailto:nathalie.castells@rothamsted.ac.uk)>  
**Subject:** Elasticsearch applications

Hi Francois (cc Nathalie),

This is Stephen from Rothamsted following up on our meeting during your visit a couple of weeks ago. 

The ElasticSearch trial we set up together for my wheat dataset expired, but I've started a new 14-day trial under a new account and have been playing around to replicate some of the searches and data visualizations you showed us. 

As a member of the data group, Nathalie will be more informed about broader applications of these tools across Rothamsted. For my own uses I'd be interested in developing an internal visualization tool to rapidly view and query the different information classes about wheat genes and separately, to see whether this could be a solution to update my moribund and sad-looking [public expression database](https://eur01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwheat.pw.usda.gov%2FWheatExp%2F&data=05%7C01%7Cnathalie.castells%40rothamsted.ac.uk%7C8fc1d9b34c0d4c6dd95a08dbcee58373%7Cb688362589414342b0e37b8cc8392f64%7C0%7C0%7C638331257362709692%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=szsYkMvuR8LYWf%2B4UZUBwyivRI3pWozCg70nTNJKmZ0%3D&reserved=0 "https://wheat.pw.usda.gov/WheatExp/").

During your visit and outside of ElasticSearch you worked with a notebook to demonstrate downloads of kibio databases and something using eland, which I lost track of. We discussed the script-based development of databases and I was curious what stage this would apply to? Would we use this to download and integrate independent databases, or use tools to transfer our own existing datasets into formats appropriate for elasticsearch?

Best wishes,  
Stephen


---
## References
