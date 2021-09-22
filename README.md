# postgres-es

> A Postgres implementation of the `EventStore` trait in cqrs-es.

![Build tag](https://codebuild.us-west-2.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiVVUyR0tRbTZmejFBYURoTHdpR3FnSUFqKzFVZE9JNW5haDZhcUFlY2xtREhtaVVJMWsxcWZOeC8zSUR0UWhpaWZMa0ZQSHlEYjg0N2FoU2lwV1FsTXFRPSIsIml2UGFyYW1ldGVyU3BlYyI6IldjUVMzVEpKN1V3aWxXWGUiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)
[![Crates.io](https://img.shields.io/crates/v/postgres-es)](https://crates.io/crates/postgres-es)
[![docs](https://img.shields.io/badge/API-docs-blue.svg)](https://docs.rs/postgres-es)
---

## Installation

```toml
[dependencies]
postgres-es = "0.2.0"
cqrs-es = "0.2.0"
```

## Usage

```
use postgres_es::{postgres_cqrs, PostgresStore, Connection};

let connection = Connection::new("postgresql://demo_user:demo_pass@localhost:5432/demo");
let cqrs = postgres_es::postgres_cqrs(connection, vec![Box::new(my_query)])
```

## Change log

#### `v0.2.0`
Moved to async/await for better tool support.

#### `v0.1.3`
Aggregates now consume events on `apply`.

#### `v0.1.2`
Require queries to also use Send & Sync.

#### `v0.1.1`
Use r2d2_postgres crate to support `Send + Sync` for multi-threaded applications.

## TODOs
- Add support for TLS.
- Additional framework around `GenericQueryRepository` to simplify event replay.

## Demo
A demo application [is available here](https://github.com/serverlesstechnology/cqrs-demo).