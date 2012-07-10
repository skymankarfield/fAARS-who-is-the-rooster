Welcome to fAARS-who-is-the-rooster API Documentation
========================

fAARS - Rocketfuel Games, Who's the Rooster?

# fAARS API Documentation

_Current base URI:_ http://faars-rocketfuel.javakafe.com/

_[gameKey]:_ who_is_the_rooster

_[gameInstanceKey]:_ rooster1

_Base system:_ CentOS release 6.2 (Final)

_Base Kernel:_ Linux 2.6.32.28-xenU #1 SMP Thu Jan 20 00:41:40 UTC 2011 i686 i686 i386 GNU/Linux

This is the version 1.0 of the fAARS API. It encompasses a set of features that allows read and write access. 
The v1.0 API introduces a number of features that were not available in the prototype version, including:
* Fully Game-Object management
* Access to internal actions and operations from RESTful interfaces
* Create an unlimited number of variables for any given Game-Object
* Unlimited Multiple inheritance defined by a Groups structure
* Multiple game instances running in parallel for multiple virtual scenarios
* Support for multiplayer modality
* Among other multiple proper RESTful POST, PUT, GET, DELETE operations

The platform works entirely using JSON files, which is a very lightweight and natural file structure/format for supporting interactions among multiple platforms and environments. Although XML and other formats can be easily supported, they will become available in future releases.

## Game >> Game-Instance >> Game-Group/Game-Object data types
Although Game and Game-Instance can be considered a data type in the context of fAARS, operations, actions and events can only be performed over/by Game-Group/Game-Object data types.

## Game-Group
A Game-Group data type is an abstraction that groups Game-Objects together in order to allow the fAARS platform to perform operations, actions, and events over/by all the members of a given group. A Game-Group doesn't contain any attributes, but it provides abstract methods to Game-Objects. Game-Group data types can be seen as interfaces to allow Game-Objects to inherit the same set of actions, operations, and events among multiple groups. At the same time, this allows to express fAARS ECA game rules at the group level. 

## Game-Object
A Game-Object data type is the minimal and essential component of every game deployed on fAARS. It contains a specific set of default attributes, but it also allows support for an unlimited multiple inheritance and 'game developer-created' attributes.

### Default list of Game-Object attributes
* fullObjectName
* objectKey
* allowLogin
* loginInfo
* currentStateKey
* active
* transient
* currentGPSLocation
* currentZone

### Groups
Groups are contained in the "groups" attribute set. Every group element contained in the "groups" attribute set is specified by two parameters:
* groupKey
* active

### Extra attributes
Besides the default list of Game-Object attributes, any number of extra attributes can be supported in the "attributes" attribute set. Every extra attribute contained in the "attributes" attribute set is specified by two parameters:
* attributeKey
* value
* active

### Operations
All the Game-Object data types support the primitive set of operations "add/substract/divide/multiply" over any of their default and extra set of attributes. Any Game-Object data type can access any of the primitive operations.

### Actions
There is a set of internal actions (functionality) like push-notifications, email, etc; that can be accessed internally (via fAARS ECA game rules) or through RESTful interfaces. Any Game-Object data type can access any of the internal built-in fAARS functionality.

### Events
Events are domain specific, which means that the name of the events embedded in the URL is decided by the game creator. The name of the events are entered in the fAARS ECA game rules, and they are contained as part of the RESTful URL structure. The scope and set of events that a Game-Object can perform is defined via the fAARS ECA game rules.

## HTTP-based & RESTful
The fAARS API is currently entirely based on HTTP requests, and conforms to the design principles of Representational State Transfer (REST). The three main data types are represented hierarchically in the URL in the same way they are related, i.e. game >> game instance >> groups/game objects >> (operations/actions/events). RESTful access uses the HTTP verbs to determine which action to perform:
* GET : Used to retrieve data. Retrieves information about game objects and game state.
* PUT : Used to update data in fAARS. Updates a game object and triggers events, operations and actions.
* POST : Used to store new game objects.
* DELETE : Used to Deletes a game objects.

## HTTP Status Codes
The fAARS API attempts to return appropriate HTTP status codes (see http://en.wikipedia.org/wiki/List_of_HTTP_status_codes) for every request.

### Common status codes include:

* 200 OK: request processed successfully.
* 401 Not Authorized: either you need to provide authentication credentials, or the credentials provided aren't valid.
* 403 Forbidden: fAARS understands your request, but refuses to fulfill it. An accompanying error message should explain why.
* 404 Not Found: You're requesting an invalid URI.
* 500 Internal Server Error: Something went wrong...

## Summary of fAARS response codes
Whenever appropriate, some of the fAARS APIs will return a JSON formatted {"status":0} when the requested API successfully completes performing an operation. There will be times when the operation won't be completed, and the following is a list of some of the returned messages by some of the fAARS APIs:
* 1 = SQL Execution Error
* 2 = No game ID or game instance ID found
* 3 = Error inserting game object into the database
* 4 = Error inserting game object attributes into the database
* 5 = Error inserting game object groups into the database
* 6 = A game object attribute is missing: <attributeName>
* 7 = A required game object attribute is empty: <attributeName>
* 8 = No game object ID found
* 9 = No game object entry found in database with given keys
* 10 = No game object attributes entry found in database with given keys
* 11 = No game object groups entry found in database with given keys
* 12 = No game object entries found in database with given game instance key
* 13 = No game object entries found in database with given object group key