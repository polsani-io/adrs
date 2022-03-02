# API versioning

* Status: __Accepted__
* Deciders: Henrique Polsani
* Date: 2022-02-04

Technical Story: [Task-10001](http://my-task-management-tool-url/link-to-task)

---

## Context and Problem Statement

To allow the application to evolve, it is often necessary to break the communication contract established in an API.

In order to allow the coexistence of the old version and a new version of an API, a versioning strategy is necessary to minimize the possible impacts.

---

## Decision Drivers

* Market trend (familiar for new collaborators)
* Current team skill and knowledge
* Ease of caching implementation

---

## Considered Options

* __URI__ Versioning
* Use a __Custom Request Header__
* Use __Accept__ header
* __Query String__ Versioning
* No Versioning

---

## Decision Outcome

To versioning APIs, use it through URI Path. This is a widely used pattern in the market.

In order to identify the application is an APIs, we'll use the ```/api``` indicator in the URI Path (check [adr-002-api-naming](https://github.com/polsani-io/adrs/blob/main/exemplos-samples/en-US/adr-002-api-naming.md)), just using the API version as __*MAJOR*__ version with the ```v``` prefix: ```v1```, ```v2```, ```v3```.

The APIs are versioned at the resource level, where if there is a need for a versioning, the entire resource is versioned, such as all related requests of this resource (GET, POST, PUT, DELETE, PATCH, etc).

Example:
```
https://my-application-url/api/v1/my-resource
```

The scenario to version an API is: a breaking change with returned or requested JSON. Only scenarios where the change is not supported by the current contract should cause an API versioning.

### __Positive Consequences__

* More familiar to developers and consumers
* Very simple to understand and implement
* It is currently the most used versioning way by the development team
* Very simple to implementing a cache strategy

### __Negative Consequences__

* Violates the rest principles where only one URI should represent a single resource

---

## Pros and Cons of the Options 

### Use a __Custom Request Header__

* Good, because it maintains the rest principles where only one uri should represent a single resource
* Bad, because it needs a specific cache strategy
* Bad, because it's not a market trend
* Bad, because it's something intrinsic from the company itself

Example:
```
Api-Version: v1
[GET] https://my-application-url/api/my-resource
```

### Use __Accept__ header

* Good, because it maintains the rest principles where only one uri should represent a single resource
* Bad, because it's not a market trend
* Bad, because it's a little confusing for those who never used

Example:
```
Accept: application/my-company.my-app.resource-v1+json
[GET] https://my-application-url/api/my-resource
```

### __Query String__ Versioning

* Good, because it's very simple to understand and implement
* Good, because it's simple to implementing a cache strategy
* Bad, because it's not a market trend

Example:
```
[GET] https://my-application-url/api/my-resource?version=v1
```

### No Versioning

* Good, because it's force the use of HATEOAS as a rest practice to make communication clearer
* Good, because it maintains the rest principles where only one uri should represent a single resource
* Bad, because it's not a market trend
* Bad, because it's not familiar for development team

Example:
```
https://my-application-url/api/my-resource
```

---

## Links

* Referenced [adr-002-api-naming](https://github.com/polsani-io/adrs/blob/main/exemplos-samples/en-US/adr-002-api-naming.md)