# Full Stack JS Project - Rest API Routes
**`fullstack-js-06-rest-api`**


## Context
You are going to build a full stack web application with node.js + React. In order to become familiar with how a node project works, you will be responsible for configuring the  initial major components of the project.  

- express server
- application routes
- views
- api layer
  - data access [this assignment]
  - data models + relations (ORM)
  - **RESTful routes**


## The Assignment
The goal of this assignment is to create the following REST routes for the jobs + company resources in your `apiRouter.js`:

```
GET   -  `/api/jobs`     - Fetches all the jobs
GET   -  `/api/jobs/:id` - Fetches a single job
POST  -  `/api/jobs`     - Creates a job
PUT   -  `/api/jobs/:id` - Edits a job
DELETE - `/api/jobs/:id` - Deletes a job

GET   -  `/api/companies`     - Fetches all the companies
GET   -  `/api/companies/:id` - Fetches a single company
POST  -  `/api/companies`     - Creates a company
PUT   -  `/api/companies/:id` - Edits a company
```

### Requirements
In order to complete this assignment, you will need to:

- [x] **Install body parser**
  - you will be sending json to your server in the *request body* and body parser will allow your express server to read/parse JSON in the request body
  ```sh
  npm install --save body-parser
  ```

- [x] **Configure body parser as application middleware**
  + in `server.js`

  ```js
  const bodyParser = require('body-parser')

  //...
  app.use( bodyParser.urlencoded({ extended: false }) )
  app.use( bodyParser.json() )

  // ^^ ... before your app routers in express
  // app.use('/', pageRouter)
  // app.use('/apiRouter', apiRouter)
  ```

- [x] **Declare routes and create Route Handlers in `apiRouter.js`**
  - you will need to use the following
    - `.get(...)`
    - `.post(...)`
    - `.put(...)`
    - `.delete(...)`

- Inside route handler functions for `.get(...)`, `.post(...)`, `.put(...)`, `.delete(...)` routes, you will need to use [Objection's table queries](http://vincit.github.io/objection.js/#fetch-queries) to fetch/create/edit/delete the records in the database

- [x] **Use Postman Request Client to test requests/routes**
  - https://www.getpostman.com/
  - Note: in the request body in Postman, you will need to send the ContentType header _application/json_
  - [Example of POST request in Postman](demos/postman-POST-example.png) (for creating a record)
  - [Example of PUT request in Postman](demos/postman-PUT-example.png) (for updating a record)

### Expected Results

- When I send a `GET` request to http://localhost:3000/api/jobs, the application should:
  - query the job records table and send them to the client as JSON data

- When I send a `GET` request to  http://localhost:3000/api/jobs/[:\_id]
  - query the job records table and send the single record with 'id: _id_' to the client as JSON data

- When I send a `POST` request to http://localhost:3000/api/jobs and JSON in the body, the application should:
  - create a new record in the database
  - send back the new record as JSON to the client (note: the new record will have an id value)

- When I send a `PUT` request to http://localhost:3000/api/jobs/[:\_id] and JSON in the body, the application should:
  - edit the record in the database
  - send back the edited record as JSON to the client

- When I send a `DELETE` request to http://localhost:3000/api/jobs/[:\_id], the application should:
  - i should send back the following JSON to the client




## Setup Instructions

In Terminal:

```sh
# (1) navigate to your project--devjobs directory
cd ~/Documents/muktek/assignments/project--devjobs

# (2) Commit your changes from the previous demo
git add .
git commit -m 'committing work from part-05-models'

# (3) You will work on the part-06-rest-api branch for this feature
git checkout -b part-06-rest-api

```

### Adventure Mode

Create the DELETE route for companies. To make this work, you will need query and delete the related jobs that have the companyId as a foreign key.

```
DELETE - `/api/companies/:id` - Deletes a company (and it's jobs)
```
