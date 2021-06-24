# Chapter 2 - Building Microservices with Spring Boot

#### Monolith applications granularity typically have the following problems:

- **Tighly coupled**: Invocation of of business logic happens at the programming language level instead of through implementation neutral protocols (JSON/SOAP)
- **Leaky**: No boundaries on data stores which can create hidden dependencies
- **Monolithic**: Single change, application completelly compiled/deployed/tested

#### Microservice-based architecture have the following characteristics:

- **Constraiend**: UNIX philosphy a service just does one thing and it just does that thing really well
- **Loosely Coupled**: Collection of small services, as long as the interface for the service does not change the owners of the microservice have more freedom to make modifications to the service
- **Abstracted**: Microservices completely own their data structure and data sources which can be only modified by that service and prevent direct access to just itself.
- **Independent**: Compiled/Tested/Deployed independently

#### Cloud based applications characteristics
