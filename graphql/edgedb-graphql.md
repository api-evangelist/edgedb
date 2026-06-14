# EdgeDB GraphQL API

EdgeDB (rebranded as Gel in 2025) exposes a GraphQL API that automatically reflects your database schema as a full CRUD API. Every object type, computed property, link, and alias defined in your EdgeDB schema is mirrored into the GraphQL schema, providing queries, mutations, and introspection without any manual schema authoring. To enable the GraphQL API, add `using extension graphql;` to your EdgeDB schema and apply a migration.

The GraphQL endpoint supports both GET and POST requests following the standard GraphQL HTTP protocol. POST requests use `application/json` content type with a body containing `query`, optional `variables` (scalar types only), optional `variables["__globals__"]` for Gel global variable assignments, optional `variables["__config__"]` for session configuration (v7.0+), and an optional `operationName` field. Responses follow the standard GraphQL format with `data` and `errors` fields. The interactive GraphiQL explorer is available at the `/branch/<branch-name>/graphql/explore` path.

Authentication uses the same bearer token (secret key) mechanism as the EdgeQL HTTP API. For EdgeDB Cloud instances, include the secret key as a Bearer token in the `Authorization` header. Local instances also support HTTP Basic authentication with a username and password. The GraphQL API dynamically generates query fields for each object type (with filter, order, first, last, before, after arguments), insert mutations (with a data argument), update mutations (combining filter/order/pagination with a data argument), and delete mutations. Custom scalars Int64, Bigint, Decimal, and JSON are defined in addition to the standard GraphQL scalars.

**Endpoint:** `https://<hostname>:<port>/branch/<branch-name>/graphql`

**Documentation:** https://docs.geldata.com/reference/using/graphql

**References:**

- Documentation: https://docs.geldata.com/reference/using/graphql
- GettingStarted: https://docs.geldata.com/reference/using/graphql#getting-started
