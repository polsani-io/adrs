# API naming

## Status

Accepted

## Context

In order to standardize and make it more readable and easy to identify the resources and sub-resources, including the intentions to change the state of these resources, a strategy for naming them is necessary.

## Decision

To naming an API, use kebab case.

In order to make the URI more readable and use a widely used pattern in the market.

Example:
```
https://my-application-url/api/v1/my-resource

https://my-application-url/api/v1/my-resource/{id}/my-sub-resource
```

## Consequences

### Positive Consequences

* More readable
* Market trend
* Fluent typing (not pressing more than one key)

### Negative Consequences

* Longs URI can be weird