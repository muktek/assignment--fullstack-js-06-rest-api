# Full Stack JS Project - Data Access
**`fullstack-js-05-models-relations`**


## Context
You are going to build a full stack web application with node.js + React. In order to become familiar with how a node project works, you will be responsible for configuring the  initial major components of the project.  

- express server
- application routes
- views
- api layer
  - data access [this assignment]
  - **data models + relations (ORM)**
  - RESTful routes


## The Assignment
For this assignment, we will focus on configuring the **models** and **relations** in our application through an ORM (object relational mapper).

Instead of doing SQL queries, we typically interact with an ORM module that provides us with a 'model' of each table. A model is simply an object-oriented representation of a database table. The ORM module we are using is called  [objection.js](http://vincit.github.io/objection.js/#models), and as you complete this assignment, you will see that it provides utility methods for fetching, inserting, and deleting data as well as providing helper methods for combining queries on our database tables.

###  Overview
The goal of this assignment is to query the data in the job and company tables using Models and return data as json when a on the `api/jobs`/`api/companies` routes. The query for the company should return related jobs.

Summary of primary tasks:

- Configure the data access library (knex) with the ORM (objection).
- Declare Job and Company models.
- Query the database using `Job` and `Company` models
- Return jobs/company records as json in the `api/jobs` and `api/companies` routes
- Create a database migration to put a foreign key on the job table (for the company id).
- Declare the relationships between the `Company` and `Job` models

Here is a link to the sample data that you will use to seed:
  - [jobs data](https://github.com/muktek/assignment--fullstack-js-04-data-access/blob/master/seeddata/jobsData.js)
  - [companies data](https://github.com/muktek/assignment--fullstack-js-04-data-access/blob/master/seeddata/companiesData.js)


### Requirements
In order to complete this assignment, you will need to:

- [x] **Install dependencies**
  - objection
  ```
  npm install --save objection
  ```

- [x] **Create relevant files/folders**
  + add a `models/` directory to `src/`
  + add a `Job.js` file to `src/models/`
  + add a `Company.js` file to `src/models/`

- [x] **Configure objection with knex**
  + in `server.js`

  ```js
  const { Model } = require('objection');

  //...connect to knex db... //

  Model.knex(«..app-db-instance..»)
  ```


- [x] **Declare Models + export**
  - Create a Job [model class](http://vincit.github.io/objection.js/#models) in `Job.js`
  - Create a Company [model class](http://vincit.github.io/objection.js/#models) in `Company.js`


- [x] **Use Model query builder in `apiRouter.js`**
  - in route-handler functions for `/api/jobs` and `/api/companies`, import models and [query for data](http://vincit.github.io/objection.js/#query-examples).

- [x] **Generate a database migration and put the foreign key on jobs table**
  + A company has many jobs, and we need to tell our database about that relationship.
  + [Instructions](https://stackoverflow.com/questions/28350849/knex-migration-creating-foreign-key) for how to put a foreign key on a table in knex

- [x] **Declare the relationships between the `Job` and `Company` models**
  - [Demo of declaring relations in objection](http://vincit.github.io/objection.js/#relations)
  - Note: instead of a static property object to configure the relations
     `static relationMappings = {...}`

     you will need to declare a static method to return the object:

     `static get relationshipMappings(){
       return {...}
      }`



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
