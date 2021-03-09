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

## Spring Boot & Spring Cloud

Spring Boot is the response from the Spring team to the monolithic -> microservice migration, Sprint Boot basically strips down all the "entrerprise" features found in Spring and it just provides the features geared towards a Java Rest Oriented application.

Spring Cloud on the other side wraps several popular cloud-management microservice frameworks under a common framework and makes them easy to use on your application by just using annotations.

##Spring microservice request flow
- Client sends HTTP request 
- **Spring Boot** will parse the request and map to a route based on the verb, parameters, URL to a method in a **Spring RestController** class
- Give route method params received.
- Map JSON to Java class (POST, PUT).
- Execute business logic using objects.
- Convert result from bussiness logic to JSON.
- Client receives the response from service as JSON

Spring bood abstracts away the common REST microservice task and lets developers focus on business logic for the service.

## Our first Microservice "Hello World"

For this first Microservice we will just create a simple hello world application which will output the first name and lastname provided as path parameters in the URL.


- [Code of Hello World](https://github.com/eddiarnoldo/Learn2021/blob/main/Spring%20Microservices/chapter1-code/demo/src/main/java/com/example/demo/HelloworldApplication.java)

Let's talk about a little on what the code is doing here and what each annotation gives us. (See code sample first)


**@SpringBootApplication**, this annotation tells Spring Boot that the class with this annotation is the entry point for our service.

**@RestController**, is what tells Springs that this class will expose code as a Spring Rest controller (GET/POST/PUT/DELETE). 

**@RequestMapping(value="hello")**, this will make that every single URLs exposed under this class start with the ```/hello``` prefix.

**@RequestMapping(value="/{firstName}/{lastName}", method=RequesrtMethod.GET)**, this will expose an endpoint which will be a GET-based REST endpoint and it will receive 2 path variables 

**@PathVariable("firstName") String firstName**, this line in the method parameters takes care of grabing path variables from the endpoint and mapping them as a parameter.

### All good and everything but, how do we run this code??

```mvn spring-boot:run``` This command will use a Spring Boot plug-in to start rhe application using an embedded Tomcat server!!


## Why change the way we build applications?
- **Complexity has gone way up** (today applications need to talk to multiple services)
- **Customers want faster delivery** (features delivered as fast as possible)
- **Performance and scalability** (scale up quickly based on volume and down when needs passed)
- **Applications should be available** (Highly resilient applications)


### What do we get if we move to microsercives?

- **Flexible**: Smaller unit of code, less time to deploy
- **Resilient**: Localized failures and easier to contain
- **Scalable**: Scale horizontally instead of scalling a whole monolith 

----
Small, simple and decoupled services = Scalable, Resilient and Flexible applications

--- 

## Cloud Based computing models
- Infrastructure as a Service (IaaS)
- Platform as a Service (PaaS)
- Software as a Service (SaaS)
- Function as a Service (FaaS)
- Container as a Service (CaaS)


![Cloud Infrastructure](https://www.bigcommerce.com/blog/wp-content/uploads/2018/10/saas-vs-paas-vs-iaas-breakdown.jpg)

### Infrastructure as a Service (IaaS)
Cloud vendor provides the infrastructure but you're responsible of selecting the technology and buiding the final solution.

- AWS EC2
- Rackspace
- Google Compute Engine (GCE)

### Platform as a Service (PaaS)
Cloud vendor provides technology we just need to provide the application and data. 

- AWS Elastic Beanstalk
- Heroku
- Windows Azure


### Software as a Service (SaaS)
Passive consumer with no input on the technology selection on any accountability of the infrastructure of the application. 

- Google Workspace
- Dropbox
- Concur

### Function as a Service (FaaS)
Deploy applications as serverless chunks of code, with this approach you don't have to manage any infrastructure (just pay for the computing cycles required to execute your function)

- Amazon's Lambda
- Google Cloud functions

### Containter as a Service (CaaS)
As as developer you just build your microservice as a portable virtual container suck as Docker and ship that to your cloud provider to execute in a virtual container.

- Amazon's Elastic Container Service


## Why IaaS is will be used for this book?
### Simplified infrastucture management
- It allows the most control over your services
- New services can be started with just API calls
- Pay only for infrastructure used

### Massive horizontal scalability
- Can quickly start one or more instances of a service

### High redundancy through geographic distribution
- IaaS has multiple data center rather than using just a single cuslter in a data center



##Microservices main attributes:
###Right Sized
Need to make sure that your microservices is either not to big so it takes too much responsibility and allows faster changes to prevent affecting a whole application

### Location transparent
How to manage physical location of a service? Can new services be added and removed without impacting clients?

# WIP!!!
