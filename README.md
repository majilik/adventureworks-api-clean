# adventureworks-api-clean
An example of a Clean Architecture API against the MS Adventureworks 2019 example DB.

This example is implemented with the .NET Core Framework, using a Web API to expose REST endpoints.

The example is architectured with Clean Architecture and is strongly focused on Separation of Concerns.
This is met by dividing the software into layers, like the layers of an onion.

This architecture makes the application become independent of frameworks, independent of DBMS and each layer can be tested in separation.
For more information about Clean Architecture, see: https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html

# Layers
Each layer can only depend on layers inwards, this is known as "The Dependency Rule".

## Framework - Outermost layer
Details of the application, such as framework specific code, drivers, etc.
For this application we put the Web API and Db code here.

## Interface
Adapters converting data from formats most convenient for the Application layer, to a format most convenient for the Framework layer.
It glues together the Framework with the Application.

## Application
Contains application specific business logic.
Encapsulates all use cases of the application, orchestrating the data flow between entities, and orders entities to use their enterprise-wide business logic.

## Domain - Innermost layer
Contains enterprise-wide business logic.
Entities that are objects or a collection of functions and data structures, all encapsulating the high-level rules of the application.

