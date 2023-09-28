## Environment
- Java version: 17
- Maven version: 3.*
- Spring Boot version: 3.0.6

## Data

Example of a Home data JSON object:

```json
{
  "id": 1,
  "area": 36.1189,
  "price": 86.6892,
  "city": "Noida"
}
```

## Requirements

In this project, The home data are provided for many countries with API endpoints for fetching specific information.
Note that all the data are virtual.

Following REST Endpoints have been implemented and all the endpoints are secured by http basic authentication.

`POST` request to `/api/home`:

* accepts a home object without id and returns status code 201 of creation
* if the home object with id is provided, returns status code 400
* it's secured by http basic auth where username and password is 'admin' and 'admin'

`GET` request to `/api/home/{id}`:

* returns the home entry with given id and status code 200
* returns status code 404 if requested home doesn't exist
* returns status code 400 if requested home id is invalid
* this should be publicly accessible and shouldn't require http basic authentication

* `GET` request to `/api/home`:
* returns all the home entries with status code 200
* it's secured by http basic auth where username and password is 'admin' and 'admin'

There are 5 tests already written and of which a few are failing due to the bug in the implementation of http basic
security configuration. Your task is to find the bug and fix so that all the tests pass.

## Commands

- run:

```bash
mvn clean spring-boot:run
```

- install:

```bash
mvn clean install
```

- test:

```bash
mvn clean test
```