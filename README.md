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
For this assignment, we will focus on configuring the **REST API Routes**  in our application. A REST API is simply a recommended *api interface* for building routes to access/manipulate *resources*. We have 2 resources in our application right now: jobs and companies.

The beauty of REST architecture is that it simplifies and normalizes the actions for interacting with a resource:
- Get many records
- Get one record
- Create a new record
- Edit a record
- Delete a record

The rest architecture for building an API for our jobs resource would be this:

| Action                  | HTTP Verb - Route     |
| :-------------          | :------------- |
| Get Many Job Records    | `GET` - `/api/jobs`     |
| Get Job Record          | `GET` - `/api/jobs/:id`     |
| Create New Job          | `POST` - `/api/jobs`     |
| Edit Job Record         | `PUT` - `/api/jobs/:id`     |
| Delete One Job          | `DELETE` - `/api/jobs/:id`     |




###  Overview
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

  ...

  // ... before your routes
  app.use(bodyParser.urlencoded({ extended: false }))
  app.use(bodyParser.json())

  ```

- [x] **Declare routes and create Route Handlers on `apiRouter` in `apiRouter.js`**
  - you will need to use the following
    - `.get(...)`
    - `.post(...)`
    - `.put(...)`
    - `.delete(...)`

- Inside route handlers for `.get`, `.post`, `.put`, `.delete` routes, you will need to use [Objection's table queries](http://vincit.github.io/objection.js/#fetch-queries) to update the table in the database

- [x] **Use Postman Request Client to test routes**
  - https://www.getpostman.com/
  - Example of POST request
  - Example of PUT Request



## Setup Instructions

In Terminal:

```sh
# (1) navigate to your project--devjobs directory
cd ~/Documents/muktek/assignments/project--devjobs

# (2) Commit your changes from the previous demo
git add .
git commit -m 'committing work from part-04'

# (3) You will work on the part-05-models-and-relations branch for this feature
git checkout -b part-05-models-and-relations

```

**Installation Checklist**

- [x] **Have mysql-server installed**
  - (`sudo service myqsl start` will confirm)
  - [link to mysql-serve install instructions](mysqlserverconfig.md)

- [x] **You have created a MYSQL user**
  - [link to instructions](_mysqluserconfig.md)

- [x] **Have knex installed globally**
  - `npm install -g knex`

### Conceptual Understanding
- Why do we creett
