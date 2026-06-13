# Roadmap

## Near Term

- Stabilize repository layout and public package names.
- Publish core, drivers, and clients under the MIT License.
- Document Docker Compose deployment with PostgreSQL.
- Define a stable mount schema format for dynamic client forms.
- Expand driver tests for GitHub, GitLab, Gitea, WebDAV, and Zotero.

## Core

- Runtime driver loading.
- Capability negotiation.
- Signed service and user request authentication.
- ACL and ownership management APIs.
- Version-safe writes and configurable retention.
- Workspace export for external tools.

## Drivers

- Harden WebDAV support against common server variations.
- Improve Git provider support with branches, tags, and commit metadata.
- Expand Zotero attachment handling and indexing support.
- Add cache retention and encrypted cache options.
- Add conformance tests for third-party drivers.

## Clients

- Bring the C#, Python, and TypeScript clients to API parity.
- Add generated types from the public API contract.
- Provide examples for browsing, mounting, linking, and workspace export.
