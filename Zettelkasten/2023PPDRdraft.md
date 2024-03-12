202311231157
Status: #draft
Tags: #document

# 2023PPDRdraft




## 1: eRAcuration back-office intranet site: 
Objective: Complete initial deployment of the new eRACuration site to the intranet, then develop improved reporting dataset downloads and requests, and integrate python tools for dataset publishing.
Tasks:
1.	RO to handover database migration code from moving data from the old version to the new data model.
2.	Develop login function to limit access to e-RA team using LARAVEL framework + MS Exchange.
3.	Liaise with ITS to deploy LARAVEL application to intranet.
4.	Move existing dataset & request reporting from e-RA site to e-RA curation site.
5.	Refactor dataset & request reporting by converting lists to downloadable tables using LARAVEL+livewire.
6.	Explore LARAVEL tools for calling existing python modules to allow integration of existing python code for e-RA dataset packaging, DOI minting and publishing. The fall-back option if this is not possible is to build CLI wrappers around the python code.
7.	Test with e-RA team and deploy


### My comments
1. Richard and I migrated the data to the actual eRAGilbert (python tools failed on my machine)
2. I researched login using EXCHANGE - and it is not trivial in PHP so we made the decision to focus on tools and techniques that can be used for e-RAdata. The implementation of login could be done later and the same as for e-RAdata
3. With help from Constantin, I deployed eracuration on the INTRANET.  We have 2 interfaces on the intranet at [[eracuration]] for actual work and eracuration-dev for the testing for the dev branches. (with a orange header background). Neat GIT workflow. 
4. eracuration also gives reports of the requests and downloads 
5. MG and SP now use the python tools for updating of DATA, and pushing the pages across. This is a massive improvement to their work on the datasets. I have used a python library to create the exe files, but some have not worked and I have not had the time to investigate that.
6. extra: I have built the image tool: add image model, and associated tool to import the media in the database: this saves tremendous amount of time. 
7. I have improved the New from Old tool, so that it does not create duplicate. 

### TODO for 1: 
1. Write a protocol.io for deployment of LARAVEL applications on the servers, including GIT commands and so on. I have kept all history form all those I have done. 
2. When login function is done for e-RAdata, try implement it in eRAcuration: note that e-RAdata will be LARAVEL11 but eracuration is LARAVEL9.  
3. It would be nice if the whole set of python apps for the website updates where working
4. To mend the export tool, I might have to implement the tables in FILAMENT (same as the new e-RAdata), and in the same breath, implement the login feature. 

## 2: eRAdata  - Requirements gathering phase
Objective: the e-RA website currently provides download access to the LTE database via eRAdata, this is a legacy system which needs rebuilding to implement FAIR principles and capture a broader set of LTE data. I will work with RO, with RO developing the new data model and I will develop the frontend, and new data loading tools developed jointly. This phase will identify requirements for the new e-RAdata frontend
Tasks: 
1. Review existing data query systems to identify good practices
2. Meet with stakeholders to understand how they would use eRAdata
3. Identify requirements for supporting FAIR dataset downloading, liaising with RIS and NWFP teams.
4. Develop non-functional mock-up to demonstrate planned look and feel, and functionality

### My comments
Note that until September, I was under the impression that i was building a web site and when on a quest in that direction. 
-  I am using LUNACY to gather information and draw the mock ups. I have collected in it the screenshots and information from existing data query systems. 
- I organised a [[Brainstorm]] that was well attended and gathered ideas as well as shared our own ideas. I wrote a report on that.
- I know where to find the information, and this part is a bit further down the line. 
- As I am researching the tools that will constitute the site, I am building test web sites to test the features. I am also noting how I make them. This is overlapping with the next objective
### to do for 2: 
- 

## 3: eRAdata – development phase
Objective: following from the requirements phase, aim to do develop an MVP version of eRADet using the new data model and with a LARAVEL frontend.
Tasks, in priority order
1. Build login system
2. Build simple query frontend allowing users to query the database
3. Build LARAVEL code to query the new data model and basic preview data
4. Implement FAIR data downloads of queried datasets
5. Build more sophisticated query tools (Stretch – more likely for next version in 2024)
6. Build data preview and visualisation tools (Stretch) 

[[connectionPGRES]]
### My comment
 1. I have a login system, an API token management system, a potential admin system for the curator to manage members. In FILAMENT2: I also built a simple table based on a Broadbalk dataset with a simple filter interface and an export function. FILAMENT has moved to version 3, and LARAVEL will move to version 11 in January: 
 2. So this side of January, I am finding out about the tools and how to set them up, knowing that once I have all my pieces, I can start putting them together. Getting more familiarized with LARAVEL helped me develop a strategy that might work better in the long run, and produce a site that will be consistent. I would like to avoid having to refactor too quickly.  
 
### to do for 3: 

## 4: e-RA Team support
1. Support Margaret and Sarah to package and publish datasets until new tools are released (see objective 1) (weekly)
2. Support extracting data from End note for e-RA bibliography, and build simple tool for Margaret and Sarah
3. Train & support Margaret and Sarah to use SQL and DBeaver


### My comments
 1. I continue to support the management of datasets -  packaging them, and minting the DOIs.
 2. I do the update using dbeaver. I have not managed to find an easy way to automated that. At some point, I tried to build the library as a json file and built a quick search tool, but the search was not adequate so I gave up that project
 3. We have not had a chance to look at dbeaver much. But it would be really helpful and then, they will be able to add people, organisations and experiments until I can add these in eracuration (easy to do in FILAMENT)
### To do for 4

## 5. Maintain existing e-RA and eRADoc websites,
incremental/minor improvements as necessary, bug fixes/corrections, code version updates for PHP (liaising with ITS)
### My comments
 1. This year, the update of the intranet server took PHP from 5.x to 8.1 - there was a lot of changes to do to the intranet sites including eRAdoc. The import function used a library that was not supported in PHP8, so I found a new one and updated the code with the new library, and also corrected most of the issues. The people in IT also helped moving some of the code over. 
 2. A few minor changes to the e-RA web site: like simplification of the login/registration so that we still keep tab. 
 3. Some changes that look trivial actually take a lot of time - like grant numbers (multiple places, databases and pages)
### to do for 5: 
Same as 2023
 1. I need to review the Privacy Notice on the web site, check my usage of cookies and program the cookie Toast so that we know that users are aware we are collecting something. This is a priority as we are collecting some metrics. 
 3. 

## 6: eRAdoc
Supervise Emily and the two visiting worker for the management of eRAdoc

### My comments
Emily has not continued. But I have enrolled Pamela who has made tremendous progress with John Jenkins project and has also imported some yield books. I have not seen Peter and Kirsten in a while, but they assure me that they are making progress on the transcription. We have renewed their " contract " so that they can continue working on that. They work from home. I will be taking Peter and Kirsten under my admin supervision (from Sarah ) as of January. 
 
### to do for 6: 
No change



## 7: OUTREACH and Meetings
- Q1 Give a talk on Laravel to the Data Science research group.
- April: Vision for eRAdata with LTE group and other key RRES stakeholders
- Identify conference to present e-RA (poster or presentation)
- Attend LTE biannual Meeting
- June: participation in LTE Broadbalk conference - Poster on eRA and demo on stand (21, 22)
- Participate in Web Dev forum (inside information from Costi) - collaborate with other web devs in the local area

### My comments
 1. I ran the Brainstorm in November. It was well attended and started an important discussion. 
 2. WebDev Forum not started by Constantin 
 3. attended the 2 LTE meeting and did my bits
 4. Participates in the Broadbalk anniversary conference
 5. on Viva  Engage (exYammer): posted a few times in the software dev and web dev groups which should be merged - I got some suggestions from there. 
 6. talk on Laravel superseeded
 7. in my own time, I went to a Hackathon which I found really useful
 
### to do for 5
 2. I would like to attend a LARAVEL or developer conference, or a hackathon - KINGDOM - BUILD is happening again in October - I will go to that anyway. {Could I get sponsoring for that? £reg is 32 , train, and take as work day instead of leave (24hours)}


## 8: Participate in ELN evaluations - 
Work alongside other RDS team members as part of the ELN evaluation to provide feedback on usefulness ELNs for RSE projects.

### My comments
During the ELN trials, I did try to use them as I would use them when they are adopted and had a few chats with Loretto and reported on my finding. 
### to do for 7: 
This is not going forward

## Personal development
I would like to stick with SQL, LARAVEL and front end development, with some more complex queries, continue learning the TALL stack to a level where I am fairly confident. I also have basic development skill in Python. There is a neat development path for LARAVEL that I could follow, with or without help from online tutor. I suggest that 10% if my time is devoted to PD and read literature, so about 2 hours a week. Not interested in server management.

### my comments
During the year, I had a few interactions with other developers, when getting IT stuff sorted, during the debugging and so on. I learnt a lot more during these discussions. I also went to a Hackathon, on a week end, and being surrounded by coders, networking, working on a different project, working outside comfort zone, pair programming. I learnt a lot that week-end and also I know that some people learnt from me which boosted my confidence. 

## Training 1: 
 1. Follow curriculum from LARAVEL daily
 2. Possible subscription to the actual courses (129 / per year) - includes livewire tools

## Training 2: 
 1. Data management and database language : Please forward papers you find interesting, or nice queries you have built so that I get an idea of what I need to aim for, thanks. 

## Career aspirations
As I am still recovering from the divorce and anticipating moving house this year, I have no intention to have a massive career move.  
I am aware that I am the main developer for e-RA. What would make that position the title of senior developer and how do I work towards achieving that status personally. 

## Physical wellbeing: 
I still find it difficult to sit for long period of times so I am reluctant to go full time in a desk job!  I use a timer to remind me to take breaks - but as I stay hyper-focused, I am not taking the breaks I need. I am aware of that. 
## Emotional wellbeing
The worst part of the divorce is over. This year, my external stress will be decluttering, decorating and moving house - one of the big stressors in life. I will be doing that alone (no other adults I can rely on) so I intend to use the recently inaugurated help provided my ROTH. 


## What I learnt this year: 
GIT commands in CLI to speed things up, using branches in GIT

Curation steps improved this year
Curations steps that I still do but have tools that should work for M and S
1. update experiments - the BExpt tool did not compile well - infrequent
2. update Keywords - infrequent
3. update files metadata - infrequent
4. load up images to the database

Other curation steps that I do: 
1. update bibliography from EN 
	1. export as a TXT
	2. check in excel for errors
	3. save as CSV, use notepad++ to convert to UTF8 
	4. in dbeaver: make new table, import csv in new table, rename old table for back up, rename new table.
2. mint DOIs for Datasets: this is straigthtforward, and I could see if I can make a exe out of that. 
3. package datasets: it is often straightforward, but when there are errors, it is a detective work to find mistakes


## Things unplanned: 
- Longer to test ELN than anticipated: because of my addiction to newness, tools and so on! yum
- Attempted migrate eracuration to LARAVEL10: used the tool LARAVELshifts: that was really good, but some of the tools could not move to LARAVEL 10 - datatables. So investigation no to use these in new development, and only use deployment tools that have a great support - so using filaments (so far) to build new interface. This one will have to stay in LARAVEL 9 until I can replace the tables with filament tables (which might not be too difficult - )
- ![[Pasted image 20231123130852.png]]

- The upgrade to Poppy came with a lot more debugging including some refactoring of the eradoc import function

[[ppdroutput]]

---
## References

[[PPDR FJP.pdf]]
