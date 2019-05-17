# GraphQL directives
## Why & How?

```
Author: Dailos
Date: 17/07/2019
```

## Why?
### Directives goals
Implement decorator pattern (as typescript) in graphQl.

### Build-In directives
Exists 3 directive 
* @include(if: Boolean!)
* @skip(if: Boolean!)
* @deprecated(reason: String)
This directives can be used in backend or frontend. For example deprecated has no sense to be used in front.

Ex:
```
query {
    getAllUsers {
        name
        surname @include(if: true)
    }
}

```

## How?
### How directiver are defined?

### Where directives can be used?
For example we can use it to consume different apis, depending on directives definition (internal code)
You can use it, for example, for require a specific format for a property ex: date @format('dd-mm-yyyy').

### Who has implemented directives?
