# Express_Heroku_API

The API is built in javascript using Express as the server and connects to a PostgreSQL database using the pg package and configured environment variables on the Heroku hosting platform. 

It connects to a basic Postgres database with just one users table storing name, email, password and "entries" a count of the number of times they have entered face images to the front end.  

The passwords are encrypted with a hash and salt algorithm served up by the bcrypt package. Passwords are retrieved using the same package and the actual user package is never stored to the database. 

The server uses Cors authentication to connect between the back end and the front end as they are served at different domains. (Cors package)

User information is passed to and from the server with json and parsed to the relational database.

It has 5 endpoints:

POST /register is used to register the user to the Postgres database
POST /signin is used to sign in to the database (This should be GET and will update in the next release)
GET /profile:id is used to retrieve a user from the database by id
POST /apiRequest is used to communication with the commercial Clarifai API which is used to detect the faces in the images posted
PUT /image is used to update the users entries count in the database when they detect a new image

The server can be accessed on Heroku at the link below:
https://blooming-chamber-64853.herokuapp.com
