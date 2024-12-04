# Response
> The Current content is an **example template**; please edit it to fit your style and content.
## A. Required Information
### A.1. Import Data Commands

Completed the following commands for running dummy data into the database.

```bash
$ rake import_data:pharmacies["../data/pharmacies.json"]
$ rake import_data:users["../data/users.json"]
```

### A.2. Requirement Completion Rate
- [x] List all pharmacies open at a specific time and on a day of the week if requested.
  - Implemented at `/api/v1/pharmacies/opening_hours` API.
- [x] List all masks sold by a given pharmacy, sorted by mask name or price.
  - Implemented at `/api/v1/pharmacies/{pharmacy_id}/masks` API.
- [x] List all pharmacies with more or less than x mask products within a price range.
  - Implemented at `/api/v1/pharmacies` API.
- [x] The top x users by total transaction amount of masks within a date range.
  - Implemented at `/api/v1/purchases/report` API.
- [x] The total number of masks and dollar value of transactions within a date range.
  - Implemented at `/api/v1/purchases` API.
- [x] Search for pharmacies or masks by name, ranked by relevance to the search term.
  - Implemented at `/api/v1/search` API.
- [x] Process a user purchases a mask from a pharmacy, and handle all relevant data changes in an atomic transaction.
  - Implemented at `/api/v1/purchases` API.

### A.3. API Document

We use swagger as the API documentation. Once you run the Rails application, visit http://localhost:3000/api-docs/index.html to check out all API endpoints.

## B. Bonus Information

>  If you completed the bonus requirements, please fill in your task below.
### B.1. Test Coverage Report

I wrote down the 26 automated tests, including unit tests and request tests.

You can run the test script by using the command below:

```bash
bundle exec rspec spec
```

### B.2. Dockerized
Please check my Dockerfile / docker-compose.yml at [here](#dockerized).

On the local machine, please follow the commands below to build it.

```bash
$ docker build --build-arg ENV=development -p 80:3000 -t my-project:1.0.0 .
$ docker-compose up -d

# go inside the container, run the migrate data command.
$ docker exec -it my-project bash
$ rake import_data:pharmacies[PATH_TO_FILE]
$ rake import_data:user[PATH_TO_FILE]
```

### B.3. Demo Site Url

The demo site is ready on [my AWS demo site](#demo-site-url); you can try any APIs on this demo site.

## C. Other Information

### C.1. ERD

My ERD [erd-link](#erd-link).

### C.2. Technical Document

For frontend programmer reading, please check this [technical document](technical-document) to know how to operate those APIs.

- --
