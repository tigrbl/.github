# Tigrbl

Tigrbl builds governed ASGI infrastructure: schema-first API runtimes, modern
Python servers, authentication packages, and portable ASGI contract artifacts.
The public repositories are designed for teams that need REST, JSON-RPC,
WebSocket, HTTP/2, HTTP/3, QUIC, typed validation, lifecycle hooks, and
release evidence to move together.

## Start Here

| Need | Public repository | What it provides |
| --- | --- | --- |
| Build REST and JSON-RPC APIs from SQLAlchemy models | [tigrbl](https://github.com/Tigrbl/tigrbl) | Mixed Python and Rust workspace for schema-first API generation, typed validation, lifecycle hooks, engine-backed execution, conformance records, and SSOT-governed release evidence. |
| Run ASGI apps over modern protocols | [tigrcorn](https://github.com/Tigrbl/tigrcorn) | ASGI3 server with HTTP/1.1, HTTP/2, HTTP/3, QUIC, WebSocket, TLS, static delivery, operator controls, embedding APIs, and release-gate checks. |
| Add authentication and authorization to Tigrbl apps | [tigrbl_auth](https://github.com/Tigrbl/tigrbl_auth) | Tigrbl-native auth package with ASGI app exports, plugin installation, runner profiles, constraints, CLI metadata, and compliance reports. |
| Share ASGI transport contracts across languages | [tigr-asgi-contracts](https://github.com/Tigrbl/tigr-asgi-contracts) | Canonical ASGI3 contract source plus generated Python, npm, and Rust contract and artifact packages. |

## What Tigrbl Is

Tigrbl is a framework and runtime ecosystem for building APIs where the code,
contracts, documentation, tests, claims, and evidence stay connected. The core
workspace focuses on SQLAlchemy-backed REST and JSON-RPC APIs with Pydantic
schema generation, lifecycle hooks, pluggable engines, and governed release
records.

Tigrcorn is the server line for deploying ASGI applications with modern
transport support. It documents its protocol and operator surface in the same
repository as its implementation, including HTTP/1.1, HTTP/2, HTTP/3, QUIC,
WebSocket, TLS handling, static delivery, config loading, metrics, logging,
workers, reload behavior, and embedding APIs.

The contract and auth repositories extend that surface: `tigr-asgi-contracts`
publishes portable ASGI event and capability contracts for Python, TypeScript,
and Rust consumers, while `tigrbl_auth` provides the Tigrbl-aligned
authentication and authorization package for applications that need governed
identity, runtime profiles, and compliance reporting.

## Common Questions

### What should I install first?

For the API framework, start with the public `tigrbl` package and the
repository README for the current package line. For the server, install
`tigrcorn` and follow its quick start and operator docs.

```bash
python -m pip install tigrbl
python -m pip install tigrcorn
```

### Which repository owns current truth?

Each repository owns its own source of truth. In the main `tigrbl` workspace,
the `.ssot/` tree is authoritative for ADRs, specs, features, claims, tests,
evidence, boundaries, and releases. In `tigrcorn`, protocol support and release
status are tied to the repository's conformance and current-state documents.
In `tigr-asgi-contracts`, `contract/` is the canonical contract source.

### Is this only an API framework?

No. The public ecosystem covers API construction, ASGI serving, identity
integration, and cross-language contracts:

- `tigrbl`: schema-first REST and JSON-RPC runtime workspace.
- `tigrcorn`: ASGI3 server and operator/runtime surface.
- `tigrbl_auth`: Tigrbl-native authentication and authorization package.
- `tigr-asgi-contracts`: portable ASGI contract artifacts for Python, npm, and Rust.

### Where should contributors begin?

Start with the README and governance documents in the repository you want to
change. Claims about support, release readiness, protocol coverage, and
certification status should be changed with the corresponding registry,
documentation, tests, and evidence in that repository.

## Public Package Map

| Package or artifact | Repository | Primary audience |
| --- | --- | --- |
| `tigrbl` | [Tigrbl/tigrbl](https://github.com/Tigrbl/tigrbl) | API framework users, engine authors, runtime maintainers. |
| `tigrcorn` | [Tigrbl/tigrcorn](https://github.com/Tigrbl/tigrcorn) | ASGI operators, application hosts, protocol/runtime maintainers. |
| `tigrbl_auth` | [Tigrbl/tigrbl_auth](https://github.com/Tigrbl/tigrbl_auth) | Teams adding governed authentication and authorization to Tigrbl applications. |
| `tigr-asgi-contract` | [Tigrbl/tigr-asgi-contracts](https://github.com/Tigrbl/tigr-asgi-contracts) | Python consumers of the canonical ASGI contract. |
| `@tigrbljs/tigr-asgi-contract` | [Tigrbl/tigr-asgi-contracts](https://github.com/Tigrbl/tigr-asgi-contracts) | TypeScript and JavaScript consumers of the canonical ASGI contract. |
| `tigr_asgi_contract_rs` | [Tigrbl/tigr-asgi-contracts](https://github.com/Tigrbl/tigr-asgi-contracts) | Rust consumers of the canonical ASGI contract. |

## Development Model

The public repositories favor explicit contracts, generated artifacts when
appropriate, current-state documents, and verification commands that live near
the code they protect. When a behavior is public, the repository should make it
clear where to find the implementation, the contract, the tests, and the
release evidence.
