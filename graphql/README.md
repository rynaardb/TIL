# GraphQL

GraphQL is a query language for your API, and a server-side runtime for executing queries by using a type system you define for your data. GraphQL isn't tied to any specific database or storage engine and is instead backed by your existing code and data.

![graphql](https://github.com/rynaardb/TIL/blob/master/images/graphql.png?raw=true)

A GraphQL service is created by defining types and fields on those types, then providing functions for each field on each type.

For example, a GraphQL service that tells us who the logged in user is (me) as well as that user's name might look something like this:

```
type Query {
  me: User
}

type User {
  id: ID
  name: String
}
```

## Basic Terminology

### Queries

**Fields**

At its simplest, GraphQL is about asking for specific fields on objects.

**Arguments**

In a system like REST, you can only pass a single set of arguments - the query parameters and URL segments in your request. But in GraphQL, every field and nested object can get its own set of arguments, making GraphQL a complete replacement for making multiple API fetches.

**Aliases**

Let you rename the result of a field to anything you want.

**Fragments**

GraphQL includes reusable units called fragments. Fragments let you construct sets of fields, and then include them in queries where you need to.

**Operation Name**

Allows you to name your queries to make your code less ambiguous.

**Variables**

GraphQL has a first-class way to factor dynamic values out of the query, and pass them as a separate dictionary. These values are called variables.

**Directives**

A directive can be attached to a field or fragment inclusion, and can affect execution of the query in any way the server desires.

### Mutations

In REST, any request might end up causing some side-effects on the server, but by convention it's suggested that one doesn't use GET requests to modify data. GraphQL is similar - technically any query could be implemented to cause a data write. However, it's useful to establish a convention that any operations that cause writes should be sent explicitly via a mutation.

Just like in queries, if the mutation field returns an object type, you can ask for nested fields. This can be useful for fetching the new state of an object after an update.

### Schema & Types

Every GraphQL service defines a set of types which completely describe the set of possible data you can query on that service. Then, when queries come in, they are validated and executed against that schema.

The most basic components of a GraphQL schema are object types, which just represent a kind of object you can fetch from your service, and what fields it has. In the GraphQL schema language, we might represent it like this:

```
type Character {
  name: String!
  appearsIn: [Episode!]!
}
```
* Every field on a GraphQL object type can have zero or more arguments
* Arguments can be either required or optional. When an argument is optional, we can define a default value
* Every GraphQL service has a query type and may or may not have a mutation type. These types are the same as a regular object type, but they are special because they define the entry point of every GraphQL query.

## Online Resources

* [GraphQL](https://graphql.github.io)
* [Apollo](https://www.apollographql.com)
* [GraphQL with Vapor](https://github.com/HappySwifter/CapoServer)
