# Node mandatory 2
Auth application for the mandatory 2 assignment in my Node.js course. I themed it around a login system for my Football Summarizer application i made with Mathias B. M. some time ago. More information can be found on the about page.

### To Run this application you need to do a few quick steps
##### You will have to do these things in the 2 seperate directories:

#### \server directory

1 - *Run `npm install`*

2 - *Create a .env file and set SESSION_SECRET*

3 - *In the server directory run `node database/createDatabase.js` to create a table and seed it.*

*You can use the two seeded users if you wish.*

| Username      | Password   |
| ------------- |:----------:|
| anders        | password123|
| admin         | admin      |


*Or create your own and check the console for the ethereal mail*

4 - *Run `node app.js` to start the backend.*

#### \client directory

1 - *Run `npm install`*

2 - *And run `npm run dev` to start the frontend.*