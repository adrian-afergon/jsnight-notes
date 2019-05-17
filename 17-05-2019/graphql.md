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
```
class AuthDirective extends SchemaDirectiveVisitor
```
With apollo client -> We must to override the field visitFieldDefinition. We add logic or fields that we need, and add params that we recieve in args `this.args.requires`.

At the end, we have to return a promise returning an apply `return await resolve.apply(this, args)`.

Always that you query a field that you haven't access, you will get `401`. If you remove this fields from the query, the data are returned by graphql `200`.

##Questions?
- Can we stack multiple directives?
We can stack multiple directive. The resolvin order is fron the last to the first.
