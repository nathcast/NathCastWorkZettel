202312051457
Status: #documentation

https://medium.com/@shifrb/what-is-rest-a-simple-explanation-for-beginners-part-2-rest-constraints-129a4b69a582


Hi,  I am Nathalie, and our group is developing a few RESTful APIs. I am working on the one for eRA.

API stands for **Application Programming Interface** and establishes a **connection** between programs so they can transfer data.

The API exposes only part of the data to the client which could be the frontend of API, (a web interface for example) or an external program, like Postman, R or Python programs.  A correctly structured **request**is sent to the API. If the request meets the desired requirements, a response which contains the data gets sent back to where the request was made. This response usually comes in the form of JSON, CSV or XML data which can the be manipulated by the user using thirds party apps like XL, PowerBI, or routines they have written in their preferred language like Python or R.

In some cases, you'll need some sort of **authorization** or authentication to gain access to the data.

A **documentation** will tell you what data is available and how to structure your request to get a valid response.

To be RESTful, and API must complies with some or all of 6 guiding constraints.

Let’s see if we have understood all that using a **real-life example:**

Imagine visiting a new restaurant. The waiter gives you a menu so you can pick what you'd like to eat. After making your choice, the waiter then goes to the kitchen and gets your food.

In this case, the waiter is the API who is connecting you to the food. The menu is the API's documentation. The request is made when you pick what you'd like to eat, and the response is the food being served.

---

  

So what is happening with the **LTEs and the e-RA database**?

e-RA provides a permanent storage of Data for the Long-Term experiments, and weather data. After having revamped the web site in 2021, and the metadata curation tool last year, we are now tackling the database itself and the Data extraction tool.

First, Richard has almost finished redeveloping the Database in POSTGRES. The new structure will enrich the information on the **experiments design** data description, metadata to include as much  as needed to describe them fully. For example:  the plots will receive Unique IDs, resolving to International Generic Sample Numbers. information on protocols, which all will receive DOIs, detailed analytical information, and all connected to standardise ontologies.  It will be the same for the collection of measurements.

POSTGRES is also a lot better at handling **spacial information. T**here are multiple data types that deal with geographical data such as points, lines, polygon, etc.

We had a **Brainstorm meeting** three week ago, with potential users and providers, to talk about the changes and start the conversation about what kind of dishes they want served! It was very successful: there was a great exchange of ideas, and enthusiasm for the project.

Next, onto the design of the WAITER, the API

I will be using **LARAVEL** to design the API.  I used it last year to deliver a tool for the curation of the metadata: it is a PHP Model View Controller framework which offers a safe and coherent structure to design web interfaces, programmatic APIs and documentations. Whether the user is coming from a web page, or a third party app, the routing within Laravel will direct their requests to the correct controllers. A lot of them are modules like Jetstream for authentication, or filament for panels, forms and tables, or scribe to build the documentation. The controllers will interact with the Models (Eloquent ORM) to query the databases appropriately with GET, POST, PUT, or DELETE requests. The controllers receive the responses, and deliver them to the view or the original app.

We are  aiming to make the responses FAIR, Findable, Accessible, Interoperable and Reusable,  and also incorporate all the metadata necessary. There are already great examples of these practices around, like HESTIA.

We already have proof of concept, and our authentication ready. I am assembling the different tools I will be using. Please let me know if you would like to be the firsts to try our wonderful dishes!