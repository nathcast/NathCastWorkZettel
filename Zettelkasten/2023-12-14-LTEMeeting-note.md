202312131536
Status: #meeting
Tags: #LTE 

# 2023-12-14-LTEMeeting-note

Software engineering for eRA: 
Since may 2023: 
### e-RAhub (website): 
- News page, 
- Update to the grant numbers and so on
- Now working on a way to assist the download of citation information for datasets
- Please visit the Credits Page to ensure that all the staff is listed properly: https://www.era.rothamsted.ac.uk/info/credits

### e-RAcuration - metadata for the curated datasets
- made eracuration live on 12 may
- import tool for images: captioning - made functions to bulk import images into the eracuration database
- 'new from template' function. this allows the curators to create a new metadata document from an old one - also avoids duplicates
- upgrade to laravel 10 - aborted 
- documentation updated - in the app
- published a couple of apps that enable Margaret and Sarah  to publish and update  datasets independently. There are still a few apps that I have trouble packaging for them, but we still have a massive improvement in the workflow.
- I package the frictionless datasets using our in-house python app and I mint the DOI, run the regular updates to the metadata and all associated pages and bibliography 

### e-RAdata - The rebuilding of the data extraction tool - dev prep phase
- Wireframing in Lunacy: a place to have all the ideas and draft the interface and a moodboard
- registration pages are ready, including syndicated registration via GitHub and google. 
- possibility to have an admin panel to manage users and permissions and some curation 
- API management in LARAVEL: checked that is was possible and straightforward
- [[Documentation]] using docblock or PHP8 attributes and scribe 
- we can use filament tables, forms, that come with export and filter tools for the front end and I created a proof of concept in Laravel 10 and Filament 2
- 19 including our team attended a brainstorm. We informed providers and users of the progress and gathered some ideas of the needs and wants. 
- Timetable: continue to gather the tools needed in December and January - until Laravel 11 is stable with the tools I use. From then, working collaboratively to produce API, internal beta version spring: we will need collaboration with data users, especially for the API. 

### e-RAdoc: 
Pamela, Peter and Kirsten are working on eRAdoc. They mainly have helped John Jenkins on an historical document and use eradoc to digitise and publish it. However, Pamela is also helping importing some Long-Term experiment documents - she is a visiting worker who is giving her time to help out. She has imported the missing yield books - scanning and image preps, and is next preparing the Brimstone.

### Upgrade to servers: 
Burdock and Wizard are migrating to Poppy and Basset - and the tools hosted by each of these servers needed updating as the version of PHP jumped from 5.xx to 8.2 - some refactoring needed. 


---
## References
[[BrainStorm]]

