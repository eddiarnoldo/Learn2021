# Microservice patterns

## Development pattern
Basics of building a microservice.

- **Service granularity**: Right level of responsibility
	- *Too coarse* (overlap in bussiness problems) / *Too fine* (dumb data abstraction layer)
- **Communication protocols**: Communication client - service
	- JSON, XML, Thrift, etc 
- **Interface design**: Endpoints
	- Structure of URLs to communicate intent
	- Versioning of services 
- **Configuration management**: Manage app specific config, code and config independent
	- How to manage configs in the cloud 
- **Event processing**: Use of events to communicate changes/state
	- Use events to minimize hardcoded dependencies

	
## Routing patterns
Consume microservices, abstract IP address, single point of entry, ensure secutiry and content policies.

- **Service discovery**: Abstract physical location
	- Could find the microservice without hardcoded location
	- Remove misbehaving services from pool

- **Service routing**: Single logical URL
	- Single URL so security and routing rules are applied uniformly

You can implement service discovery without service routing and vice-versa

##  Resilency patterns
Prevent problem on single service to cascade to consumers.

- **Client side load balancing**: Cache locations on client (provided from service discovery)
	- Cache location on clients to load balance request to healthy instances.
- **Circuit breakers pattern**: Fail fast
	- Prevent clients to continue calling falling services
	- Client respond quickly and take action

- **Fallback pattern**: When it fails provide a plug-in
	- Provide plug-ins to try to carry out its work through alternative means
- **Bulkhead pattern**: How to segregate calls on resources
	-  Prevent mis-behavior of one service to impact rest of application

## Security patterns
- **Authentication**: Determine trusted clients
- **Authorization**: Validate if clients can perform actions
- **Credential management & propagation**: Prevent a client to constantly present their credentials
	-  OAuth2, JWT

## Logging & Tracing
Difficult logging and debug so need to follow patterns

- **Log correlation**: Tie all logs produced between service for a single transaction
	- Correlation ID
	
- **Log aggregation**: Put all logs into a single queryable database, use correlation ID for search

- **Microservice tracing**: Visualize flow of a client transaction accross service and track performance


[Back to -> Welcome to the cloud]()






	


