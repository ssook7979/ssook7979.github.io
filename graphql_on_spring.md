[https://github.com/graphql/graphql-over-http/blob/main/spec/GraphQLOverHTTP.md](https://github.com/graphql/graphql-over-http/blob/main/spec/GraphQLOverHTTP.md)

### recommended url

`<host>/graphql`

### serialization format

must support JSON

### media types

request

- `application/json`

response

- `application/graphql-response+json` (the preferred type)
- `application/json` (An alternative type for responses (to support legacy clients))

<aside>
💡 Note: From 1st Jan 2025, every *server* and *client* must support `application/graphql-response+json`, so including this in the Accept header should give your client compatibility with any *server*.

</aside>

### Request

- A server MUST accept POST requests, and MAY accept other HTTP methods, such as GET.

<aside>
💡 It is RECOMMENDED that a client set the `Accept` header to `application/graphql-response+json; charset=utf-8, application/json; charset=utf-8`.

</aside>

### Request Params

> A *GraphQL-over-HTTP request* is formed of the following parameters:
> 
> - {query} - A Document containing GraphQL Operations and Fragments to execute.
> - {operationName} - (*Optional*): The name of the Operation in the Document to execute.
> - {variables} - (*Optional*): Values for any Variables defined by the Operation.
> - {extensions} - (*Optional*): This entry is reserved for implementors to extend the protocol however they see fit.

### GET

the GraphQL request parameters MUST be provided

예시)

```python
http://example.com/graphql?query=query(%24id%3A%20ID!)%7Buser(id%3A%24id)%7Bname%7D%7D&variables=%7B%22id%22%3A%22QVBJcy5ndXJ1%22%7D
```

### POST

POST request instructs the server to perform a query or mutation operation

POST request MUST have a body which contains values of the request parameters

A client MUST indicate the media type of a request body using the `Content-Type`

A server MUST support POST requests encoded with the `application/json` media type

If the client does not supply a `Content-Type` header with a POST request, the server SHOULD reject the request using the appropriate `4xx`
 status code.