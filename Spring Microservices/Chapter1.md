# Chapter #1 "Welcome to the Cloud"
The contept fo the microservice started in the year of 2014 and it was a response to all the challenges of trying to scale both technically and organizationally large monolothic applications.

Microservices are **small, loosely coupled, distributed services**.

Problems it solves is that in a monolithic application all teams even they have they own areas and responsibilities they all share a single code base and every small change needs the full application to be regressed, compiled, deployed, etc.

## Characteristics of a microservice architecture:
- Appplication logic is broken into small-grained components
- Each component has it's own domain (should be reusable)
- They communicate using HTTP, JSON, etc
- The technical implementation of each service is irrelevant as they comunicate using a single mechanism
- Allow organizations to have small development teams

## Spring Boot && Spring Cloud

Spring Boot is the response from the Spring team to the monolithic -> microservice migration, Sprint Boot basically strips down all the "entrerprise" features found in Spring and it just provides the features geared towards a Java Rest Oriented application.

Spring Cloud on the other side wraps several popular cloud-management microservice frameworks under a common framework and makes them easy to use on your application by just using annitations.
