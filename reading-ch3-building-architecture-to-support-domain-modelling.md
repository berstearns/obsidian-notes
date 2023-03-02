# building an architecture to support domain modelling


## behaviour should come first and drive our storage requirements
	the first part of the book looks at how to build a rich object model through TDD and then we will show how to keep that model decoupled from techincal concerns. 
	how to build a persistant-ignorant code 
	how to create stable API's around our domain so that we can refactor agressively
## The key design patterns used:
	1. The repository pattern, an abstraction over the idea of persistent storage
	2. the service layer pattern to clearly define where our use case begin and end
	3. The Unit of Work pattern to provide atomic operations
	4. The Aggregate pattern to enforce the integrity of our data

## the services are similar to the idea of Use Cases
flask deals with the http domain, mapping http to services. 
services is where the domain objects reign
services call unit of works that which are boundaries for data access and processing

## Chapter 1. Domain Modelling
	-> Mapping business processes into models in a way that is compatible with tdd
	-> Few concepts, entity valueo object, and domain service
	-> domain model pattern

# Appendix B 
	write-up of the infrastructure for the example code
	how to build and run docker images
	managing config info and how to run different tests

Appendix C
	"proof is in the pudding" kind of content
	showing how easy it is to swap out the entire infrastructure
	changing hte flask api, the ORM, postgres for I/O model, CLI, and csv

Appendix D 
	Applying the same patterns in django

