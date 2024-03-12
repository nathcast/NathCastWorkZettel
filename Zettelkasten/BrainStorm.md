202311131350
Status: #talk #meeting
Tags: [[eRAdata]]
previous: [[eRAbones]]
next: [[eRA database structure]]


# eRAdata BrainStorm meeting

- [[#Preliminaries: Ideas of agenda|Preliminaries: Ideas of agenda]]
- [[#checklist|checklist]]
- [[#Agenda for talk - we might not follow it, but there is a plan!|Agenda for talk - we might not follow it, but there is a plan!]]
- [[#Minutes of the meeting|Minutes of the meeting]]
	- [[#Minutes of the meeting#Present|Present]]
	- [[#Minutes of the meeting#**RO presentation:**|**RO presentation:**]]
	- [[#Minutes of the meeting#**Suzanne**: How is the data entered into eRA?|**Suzanne**: How is the data entered into eRA?]]
	- [[#Minutes of the meeting#MH – what is API, how to visualize this?|MH – what is API, how to visualize this?]]
	- [[#Minutes of the meeting#Nath demo Laravel magicadmin:|Nath demo Laravel magicadmin:]]
	- [[#Minutes of the meeting#**Andrew Riche** suggested years as columns not rows.|**Andrew Riche** suggested years as columns not rows.]]
	- [[#Minutes of the meeting#**How would have access to data? Access to all?** - User management|**How would have access to data? Access to all?** - User management]]
	- [[#Minutes of the meeting#**Gonzalo** Priority to understand treatments over time for plots.|**Gonzalo** Priority to understand treatments over time for plots.]]
	- [[#Minutes of the meeting#**Marcelo** – is this a platform to give snapshot of data, or exploratory data analysis/visualisation?|**Marcelo** – is this a platform to give snapshot of data, or exploratory data analysis/visualisation?]]
	- [[#Minutes of the meeting#**Marcelo**: Workflow for data entry what is the structure?|**Marcelo**: Workflow for data entry what is the structure?]]
	- [[#Minutes of the meeting#Web interface or API or calculated data? What would people prefer?|Web interface or API or calculated data? What would people prefer?]]
	- [[#Minutes of the meeting#Format of output?|Format of output?]]
	- [[#Minutes of the meeting#Need to know from modellers what resolution data is required?|Need to know from modellers what resolution data is required?]]
	- [[#Minutes of the meeting#API|API]]
	- [[#Minutes of the meeting#**TS**: Are we expanding database to include hourly met data?|**TS**: Are we expanding database to include hourly met data?]]
- [[#additional notes|additional notes]]
	- [[#additional notes#Email from Kev|Email from Kev]]
	- [[#additional notes#Email from Loretto:|Email from Loretto:]]
	- [[#additional notes#email from Tony|email from Tony]]
	- [[#additional notes#Andrew Riche Notes (transcribed from paper)|Andrew Riche Notes (transcribed from paper)]]
	- [[#additional notes#Jonah Prout Notes (transcribed from Paper)|Jonah Prout Notes (transcribed from Paper)]]
- [[#References|References]]


## Preliminaries: Ideas of agenda

- I give a welcome, and intro, give agenda, a quick tour of the room (name - role - main skills: a few buzz words) - 10 minutes
- **Please give a talk highlighting the new direction of the database and FAIR challenges that we want to access in this iteration of the new database / app: how long  do you want for that?** 
- We then go into discussions about the app: these is an unordered list of points for that that I would like to discuss 
    - API - programmatic access: biggest chunck - but might not be the first we discuss - as some might want to leave at that point 
    - user login - user types - moderation - NC to demo the LARAVEL login and admin panel that are available
    - I have a few quick questions that I will need answered regarding style and branding 
    - Content of the actual site: support for API: documentation, examples, tutorials, case studies, links? quick web search of the database?  - or web query builder  and download  stuff? or integrate the new stuff with the eRA site which will mean rewriting eRA hub in LARAVEL (which might not be too hard anyway)
    - we need to fit a comfort break (move, get drinks) 
- Regarding timetable for development: the new version of LARAVEL will appear in January. so in 2023, I will continue to build my tool box, and idea, Then January to April: build working BETA API prototypes - so aiming to have beta testers in APRIL to come on board to work with me on the beta I would like to have one or two of these programmers on board, unless we advertise that to a work experience student. By APRIL, the LARAVEL community has debugged the present version of LARAVEL and I will know the tools that are still well supported in it. Hopefully, I will not have nasty surprises - I am very careful now. 
- Tomorrow: I will bring my laptop - we can use it to connect to the local machines that have the codes, and please bring your too> 
- Thanks for comments
-
**RICHARD**:  I'll only need 5 mins max for bullet 2. For style and branding, I think we follow the existing e-RA site style as it will be a part of e-RA in the way DET currently is, so I don't think we need to spend too much time on that. Equally I don't think we need to spend time on how this is architectured. What you mean by eRA hub?
Also talk about the winding down - so present a road map - 

**NATH** that could be a good point to discuss  with the team there - see what kind of reaction we get to the demise of eRADET: can they do without DET when the API is ready? or will some need access to DET because they can use API but need more than the prepared datasets - I am thinking about Margaret and Sarah and how they get their data to prepare the curated datasets - we quickly mentioned it on Thursday, we do not have to solve that problem now. I  would suggest that as soon as we have the API working, we do not put new data in the old DATABASE - so for externals: it will be prepared datasets or API. For inside: prep datasets, API and SQL queries until we have a GUI query/filter builder -

## checklist
- [x] list for Brainstorm @due(2023-11-14)
	- [x] where is the coffee stuff
	- [x] buy coffee, Biscuits, milk
	- [x] Prepare proof of concept app: [[eRAbones]]
	- [x] Prep some slides or a  workflow
	- [x] make prep for HYBRID - how does that work? - WHITEBOARD

## Agenda for talk - we might not follow it, but there is a plan!  
1. Welcome, ask around the room: name, main research area, main way you have used data from eRA before if at all, if you have used the eRAData extraction tool, and if you are using other source of data, how do you extract data in general. 
2. Richard is going to give a quick intro about the data itself
3. Quick demo of what i have been able to design out of the box using the LARAVEL framework 
	1. I start in Magic Admin to demo the tables, and filters. - then said that this was the previous version of Filament
	2. start the latest to demo the login with github
4. While Richard is away, we can have a chat about users, admin, moderation, what kind of users
5. Then we can see what sort of content the frontend to the new app can have - should we have a few data tables with filters and downloads? 
6. Then we can have a discussion about the API - and see what data would you need in priority to hooked and which transformations
## Minutes of the meeting
### Present 
- Nathalie Castells (NIC) - chair
- Malcolm Hawkesford (MH)– BK data, still asks MJG if needs data
- Tony Scott (TS)– met data, little extraction of data, supplies data.
- Andy G (AG) – doesn’t use DET much, more involved front end. Great improvement website
- Jonah Prout (JP)– C modelling. Through MJG
- Kevin Coleman (KC) – agrosystem modeller. Use e-RA a lot. Knows how to extract data
- John Addy(JA) – use e-RA a lot
- Andrew Riche (AR)– extract lot met data from e-RA. Would like an easy way of see met data
- Melina (M– hasn’t had reason to extract data yet.
- Margaret Glendining (MJG)
- Suzanne (SC)– met data for a project, and supply raw data to curators.
- Richard Ostler (RO) – head the data team, work closely with M<S<N.
- Gonzalo Irisarri (GI) NW using LT data, would like to use more
- Alberto Stella (AS) Insect survey
- Ian Shield (IS) LTEs in his section, LSRE into e-RA soon, Also FFEC. Has extracted some data, mostly met data. Now more complicated to get out.
- Hadewij Sint (HS) NWFP, aligning data portals.
- Loreto Pino-Chandia (LP) data steward LSRE
- Marcelo Galdos (MG)  soil C e-RA important for work. Have explored with MG discussed ideas with RO. Ltd in soil C.
- Thibaut Putelat (TP) modeller e-RA since joined, mostly using data not currently in e-RA. Also to look at Yield books. Met data.
###  **RO presentation:** 
- We have been redeveloping e-RA website and how publish data. 
	- Prepared datasets. All standalone data sets. 
	- Need to download, join yield and nutrient datasets together. 
	- DET – Can't join datasets together. 
	- Lot of data in e-RA that is not in DET. 
	- Data prepared and curated. 
	- None of data downloaded from DET in context – 
	- no management data, etc. So developing new database that captures all information
- **Priority** expt data not met data, as met data in better state.
- Pulling in additional datasets – LSRE, etc.
- More standardised. Aligned with NWFP were possible. 
- Contextual information – plot history, etc. V comprehensive. 
- Also add Metadata – people involved in analysis, protocols, sample prep, etc. Good provenance of data.
- Spatially enabled – every plot associated with a polygon. Sample points of soil samples.
- **Provisioning data**:
	- Direct sql query of database – internal only, need a good understanding of the data
	- API – programmatic access to data via API, as for NWFP and Insect Survey. 
	- Select variables, plots etc interested in. 
	- Visualization, etc. What should this look like?
- **Website/API/how to access**
- **Format?** How much effect to reprocess the data for own use? (cf met data at present).
- **Training resources**? 
- How much pre-prepared?
- How much access control? Currently need ac and password, access to particular datasets. New model – access to all? We monitor downloads, DOI to cite data?
--- 

### **Suzanne**: How is the data entered into eRA?
Accessed from FarmOS?/ FarmOS – who will this be involved? – 
	- RO like Yield Books, curation stem, check data in FarmOS is correct, then bring into database.

External users? Website and API?

### MH – what is API, how to visualize this? 
Answer: URL that can be  code in R or Python, way to extract.
From the Postman site: 
```
An API, which stands for application programming interface, is a set of protocols that enable different software components to communicate and transfer data. Developers use APIs to bridge the gaps between small, discrete chunks of code in order to create applications that are powerful, resilient, secure, and able to meet user needs. Even though you can't see them, APIs are everywhere—working continuously in the background to power the digital experiences that are essential to our modern lives.
```


[RO left 11am]

### Nath demo Laravel magicadmin: 
I have been LARAVEL, a PHP framework, since 2020, and developed an app for the eRA curators as a learnig tool for myself. It supports many tools with which we could build basic web interfaces and API from the box. I showed one I did that had an admin panel, login system, and table with filters and export facilities. With LARAVEL, we can also develop API. 
**MH** – looks really nice.

### **Andrew Riche** suggested years as columns not rows. 
Is this possible? Pivot function? API to do this? AMMAR suggested that it is possible to have the API pivot the data. 
Someone else also suggested the possibility of reordering the columns in the web app before downloading - Something that is done in EUROSTAT. - link below. 
**Kev** – [[Eurostat]] – https://ec.europa.eu/eurostat/databrowser/explore/all/all_themes?lang=en&display=list&sort=category can move columns and rows around as required. Pivot tables.
### **How would have access to data? Access to all?** - User management
**AR** – would make all accessible to all. 
**MH** – aim to make all data available to all in wheat program. Should make as accessible as possible. [MH and AR left 11.12]
**TS** – UKRI funded needs to be Open Access.
**Insect survey** -data for last couple years not publicly available, strategy and practical – QA etc.  Limitations on current data? Embargo for external, admin see everything.

```
Note from Nath: from the discussion with the group I conclude that we will need at least 4 types of users with usernames: 
1. guest: someone who has just registered - and email verified (email verification is automatic). 
2. user: someone whose registration has been checked by curators - we would like the users to fill in their profiles with something more, like affiliation, why use data or something like that? these will have access to most of the QA data, and non embargoed. 
3. power users: collaborators will have access to all data: 
4. admin: a few are moderators and can modify users or data

Only users 4 can edit data that is not their own. 
```
### **Gonzalo** Priority to understand treatments over time for plots. 
NATH: reply: just as for the prepared datasets, all the information needed to understand the treatments is zipped into the bundle, the same will happen with the new interface. Downloads of data will have a clear option to download treatment information with it. Some will not be optional but included in the table. 
### **Marcelo** – is this a platform to give snapshot of data, or exploratory data analysis/visualisation?
**Nath**: in the beginning, there will be a few filterable tables and export facilities, but more effort should be made to push people to use the API and do their own analysis. We could also bring onboard collaborators who could do some visualisation of data and that can be exhibited on the site as tutorials, case studies for the LTE community, or for Data education
### **Marcelo**: Workflow for data entry what is the structure?
**SC**: Need better work flow, more timely. Not for this meeting. Expectations for when data is available. Also linked to FarmOS. If the steps for curation are clearly explained, that would help with the expectations regarding data availability. 
**AG**: Only automated data from Met station. All others discrete measurements, need to go through QA. Maybe this needs better defining. Always lag – up to 2 years, for crop and soil analyses. Yields within a year.
NC: mentioned that there was a hackaton that tried to simplify the process a few years ago, but that is still very much a work in progress and not the focus of this meeting. either the present web site, or the new eRAdata may have ways to explain this, but will not be in the process of the data entry workflow, but very much an end product. 
**TS** – met data checked each day. NWFP do similar thing. Very hard to automate, needs human eyes to check. Eg changed to rain gauges. How to deal with this?

[Kev left 11.25]
### Web interface or API or calculated data? What would people prefer?
**SC**: APIs can be useful if pulling data down regulary, code to do this every day, eg met data. Not so necessary if only one-off.
**TS** still need an interface for those who can’t program. So need both website and API.
**SC**: often go to DB to look for one thing, but useful to be able to look at others when there, even if can’t extract that data.
**TS** created excel files for met data, to calc derived variables. No longer available, AR misses this. Good to have a quick preview.
Missing facility to directly export data into excel file, from met data. THIS WOULD BE VERY USEFUL to all users.

### Format of output? 
Happy with csv and excel? YES
**Marcelo** – met data would be useful as template for other short period data, eg gaseous fluxes. 
**Ammar**: Storage capacity is a limiting factor. Eg Met data every second. Marcelo would also like this. Important point, increasing capability of e-RA. Storage capability important.

### Need to know from modellers what resolution data is required?
- **SC** – wants monthly data, downloads daily, then has to calc monthly. Would be helpful if could download monthly data.
Modellers – often need monthly met data with some models (RothC, Century) others 30 mins.
- **Had**: **Aggregation issue**. What to do with missing data, especially with rainfall? Can’t just add up the data, if there is data missing. Have to be aware of this. Users to decide themselves how to aggregate. 
- **SC**. Sampling intensity needs recording, with the data. Then user can then decide how to deal with this. TS: Need a note to explain missing data, or substituted data, eg recent example of odd rainfall data. Error code to show data missing, not just zero.
Nath **Q**: Can the database do the aggregation, or should it be done by humans? 
- **Had**: can be done automatically, but also need to include number of missing values, and length of period of missing data. NWFP – can download monthly stats, but have a lot of caveats. 
- **TS**: overall provision should be raw data, could also supply summary data, eg **aggregation tool**. Upload data into an aggregation tool. BUT have to make sure have all the information. Eg monthly temp, with days missing.
Missing data: **SC** advocate for only presenting data that is measured, not interpreting adding in missing data.
- **AG**: Expert judgment for frequency of data – daily/hourly/etc. Present daily, inform hourly etc is available.
- Flags if values go outside expected bounds. However, for rainfall this is difficult. More reliable for yields, temp, etc.

[RO returned 12 noon]
### API 
Nath describes API token obtention from the web site
API tokens: allow to authenticate with a third party. So can access via Github etc. One way of accessing APIs.
**RO**: API comes first, as can then query the website. Both serving same data. 
- What end points would be required? 
- How do you frame the query to get the data out? 
- Per expt, per treatment, per plot??
- What information is coming back, what does that look like? 
How structure is very flexible. Eg if working in R/python can export directly. Also need to provide license info, metadata, etc. How do we encourage end users to look at this? Not just looking at yields. Lots of ways could structure this. Table / hierarchy / plot / year / expt. Which is more useful? Are there other schemes we could use?

Eg from **Hestia**: JSON file soil carbon and Also csv format.
https://www.hestia.earth/schema/Cycle
**RO**: problem with csv, can’t put the same textural information in, eg licences,
JSON can provide this. 
**SC**; how do you actually see this information?
**Marcelo** likes this option to see with JSON.
**Gonzalo**: Takes time to learn how to use API.  May end up having a specialized community that can ask questions of the Rothamsted database. 
**Marcelo**: this is very useful, but doesn’t mean everyone needs to learn to do it – need also simple csv/excel options.
**RO** API may not get as many users, but may be more impactful – Turin digital twin NWFP – API provides automated access to the data, can build other tools on top. Help with developing Masters Students projects with this as a data source, eg machine learning resource.

Nath demos the documentation that comes with the API as it is developed. 
**Nath**. Documentation can also build traffic.
**TS**: Front end – option to build in graphics, overview of data, time series before download the data? YES (Nath).
**Nathalie** still gathering ideas, won’t start until Jan onwards. Beta version in April. Testing by modellers and other users.  Who would like to be part of beta testing?
Keep conversation going please. What do modellers want to see? Who would like to continue to be involved? - no answers to these questions

### **TS**: Are we expanding database to include hourly met data?
**RO**: Not expanding to annual expts, only LTEs. LSRE and Transition Expt, Stephan expts. Take-all expts maybe.
**AG**: expand remit in next round of funding, to include eg LSRE.

Finished 12.35. 

## additional notes 
### Email from Kev 
	One thing I would like from E-RA is easier access to the data from the NWFP.

### Email from Loretto: 
While I was in the meeting, I was taking notes about it, and using my small experience downloading data from big databases, here are some things:

- To download a csv/excel dataset is perfect as a tool. Then users can work with their data as they need. There are so many different users and data use, that cover each of them does not sound as possible. 
- I think that using both an API and an export tool would be the best to download data. Not all people work or are familiarised with Programme languages.
- Creating a set of tools such as codes or packages to work with the data in Python or R would be a good option for the future.
- A searching tool to find specific data (e.g., using keywords).
- An easy way to find the specific metadata for each dataset(s) would be good too.
- To have a set of instructions as a help tool.
- Later, showing a series of use cases of e-RA data in papers or projects on the website would be useful.

### email from Tony 
Currently to answer questions regarding Meteorological questions, especially around records broken, I have had to set up a series of MS Excel workbooks.
Examples are:
1. number of consecutive dry days
2. maximum air temperature and date it occurred
3. number of consecutive days above a threshold temperature for determination of a heatwave. A heat wave is three or more days above a location records daily maximum temperature threshold. For Hertfordshire/Bedfordshire that threshold is >=28°C, based on the 1991 to 2020 daily maximum temperatures for July 15th. [https://www.metoffice.gov.uk/weather/learn-about/weather/types-of-weather/temperature/heatwave](https://eur01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.metoffice.gov.uk%2Fweather%2Flearn-about%2Fweather%2Ftypes-of-weather%2Ftemperature%2Fheatwave&data=05%7C01%7Cnathalie.castells%40rothamsted.ac.uk%7C5368e80017fe45acc47608dbe526c3dc%7Cb688362589414342b0e37b8cc8392f64%7C0%7C0%7C638355726872057953%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=M9kfFU7vJdJIHxVarsKoLVaJEmyjY4K1IziueZ2qplY%3D&reserved=0)).
4. minimum air temperature and date it occurred.
5. Etc…
Will the new front end be able to interrogate the database to produce imbedded monthly/yearly summary tables and create tables of records and even graphics? That will give a general overview of the changes in climate at our sites as they occur without the user having to download data to produce them themselves.

These sort of things would probably encourage more visits to the pages and prompt people that the data is available for use. It could also be beneficial for me in putting together the monthly and annual weather reports.
### Andrew Riche Notes (transcribed from paper)
- structured data
- data which can easily be read into a statistical program
- for example connect missing values
- what was good about the old e-RA was the ability to see all the daa before extraction
- I prefer to download all the data and view / calculate into a stastical software
- I would avoid giving full previews of all data: only give previews for some of the data within a dataset

### Jonah Prout Notes (transcribed from Paper)

- I think that both a web interface to download and access via an API will be useful.
- Would be necessary to link up with IT to understand what users need in order to access using an API - admin rights, certain software, or programming language?
- To be able to download different resolutions: e.g. if collected daily, to be able to download also monthly agreggated and averaged values >>> HAD raised a good point regarding missing values - so an aggregation tool might be an option (HAD suggested that too)
- Tutorial for Rothamsted staff and students on how to access API with common programing languages in the Rothamsted IT infrastructure - A lot of tutorials assume that you have access as if a personal computer, access to C:, drive, non network drive - adding sites to PATH 

- [x] send summary to the participants and RO, ahead of the LTE meeting ? @completed(2024-01-04T18:11:29)
- [ ] makes the plan for eRAdata 




---
## References
[[images for Brainstorm]]

