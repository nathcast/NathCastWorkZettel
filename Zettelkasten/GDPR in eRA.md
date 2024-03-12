---
aliases: []
---
202401301519
Status: #idea
Tags: #GDPR

# GDPR in eRA

https://github.com/Rothamsted-Ecoinformatics/eRA/issues/88 

see [[GDPR course]]
- made a page with the content of the PP from Rothamsted, 
- reading the page: listing the promises of that document 
	- When we hold or use your personal information as a data controller (see below for a description of what this is) we will provide you with a privacy notice which sets out in detail what information we hold about you (such as your contact details, address, etc.), how your personal information may be used and the reasons for these uses, together with details of your rights.
	- Where we collect personal information from you directly, we will provide this privacy notice at the time
- https://www.dbxuk.com/blog-2023/cookies-vs-sessions  However, it would be possible (but not recommended) to store personal information within a session cookie. This would not be compliant if it could be used to identify an individual. Sessions are OK, but I need to check that I am not recording anything that can identify a person
- TODO: 
- [ ] Correct the Privacy page in eRA and pass on
- [ ] Check sessions variables : Do they store private information? 
	- I am killing history everyday
	- user info is killed after 7 days

- [ ] make a toast to say that we collect limited information for funding purposes and continuing on this site is considered consent
- [ ] make a specific privacy notice for eRA that is sent when User Request 
	- [ ] how long we keep the personal data, 
	- [ ] their right to be forgotten - note that being forgotten will forego their use of the database: can we do that? 
- [ ] Need a chat about the IP address: Do we need them for User Request? 
- [ ] For the Downloads, It is nice to be able to identify download per unique person. https://law.stackexchange.com/questions/61076/storing-ips-and-gdpr-compliance that article explains that IP is personal data and as such they need to consent to have it collected. 
- [ ] Need to make google analytics GA4 GDPR compliant or stop using it. https://www.cookieyes.com/blog/google-analytics-gdpr/ 
- [ ] RE gA4: I have now installed GA4 on eRADET _ I realised that it was not collecting data. the tag was not in the code. I have corrected that. 

When ask for data this is what we say we record

Dear Nathalie

This is the information that has been recorded.

- **Name :** Nathalie Castells
- **Email :** [nathalie.castells@rothamsted.ac.uk](mailto:nathalie.castells@rothamsted.ac.uk)
- **How did you hear about e-RA :** COL - - Rothamsted
- **Sector :** Academic (Research Institute or University)
- **Institution :** Rothamsted Research (RRES)
- **Country :** GB
- **Student :** Not recorded as Student
- **Funding source :** BBSRC
- **ISPG :** NBRI-LTE
- **Are you happy to receive occasional emails?** yes
- **Data request reason :** GDPR work Investigating the email send to check what we say - GDPR work
- **Datasets requested (shortnames) :** Broadbalk , BKYIELD , ParkGrass
- **More Specifications :**

A member of our team will contact you shortly. Please reply to this email for correspondence.


---
## References
