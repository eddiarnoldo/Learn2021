# Chapter 2 - Building Microservices with Spring Boot

## Monolith applications granularity typically have the following problems:

- **Tighly coupled**: Invocation of of business logic happens at the programming language level instead of through implementation neutral protocols (JSON/SOAP)
- **Leaky**: No boundaries on data stores which can create hidden dependencies
- **Monolithic**: Single change, application completelly compiled/deployed/tested

## Microservice-based architecture have the following characteristics:

- **Constraiend**: UNIX philosphy a service just does one thing and it just does that thing really wellbut ye
- **Loosely Coupled**:
	-  Collection of small services
	-  As long as the interface for the service does not change the owners of the microservice have more freedom to make modifications to the service
- **Abstracted**:
	- Completely own their data structure
	- Data sources can be only modified by that service
	- Prevent direct access to just itself.
- **Independent**: Compiled/Tested/Deployed independently

## Cloud based applications characteristics

- **Large and diverse user base**
	- Different customers want different features
	- Features can be delivered quickly
	- Services are for small scope and well defined interfaces

- **Extremely high uptime**
	- Descentralized nature
	- Resistent to problems
	- Reduces overall downtime

- **Uneven volume requirements**
	- Hard to have an idea on the demand cost for a simple action
	- But at the same time it's easier to identify components under load to scale them

> Desing a microservice as if you were a detective, include perspectives o multiple individuals.

## Input from Critical roles for microservices:

- **Architect**:
	- See the big picture
	- How to decompose into individual microservices
	- Interaction between microservices
- **Software developer**:
	- Writes the code
	- Understands the language and development framework
- **DevOps Eng**: 
	- How services are deployed
	- Management of services prod/non-prod

----


## Building a Microservice on each role perspective:

### Architect's story:

> Provide the scaffolding against which developers will build their code

 **Key tasks**
 
 - Decomposing business problem
 - Establishing service granularity
 - Defining the service interfaces

#### Decomposing the Business problem:
 
Break business problem into chunks that represent discrete domains of activity.

Look where the data domain doesn't seem to fit together.

The presence of two data domain is a good indicator that multiple services are at play.

How the two interact usually becomes the service interface.
 
#### Guidelines for identifying & decomposing business problem

- Describe the business problem, and the listen to the nouns you're using.

	> Example in Eagle Eye: *contracts* , *licenses*, *assets*
	
- Pay attention to the verbs

	> When Mike from desktop services is setting up a new PC, he ***looks*** up the number of licenses available, installs the software. He then ***updates*** the number of licenses used in his tracking spreadsheet.
	
- Look for data cohesion
	
	> Microservices should completely own their data

<img src="https://github.com/eddiarnoldo/Learn2021/blob/main/Spring%20Microservices/Chapters/Chapter2/Images/Chapter2/chapter-2-nouns.png" alt="drawing" width="200"/>



 
