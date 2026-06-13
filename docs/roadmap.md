# Roadmap

## Near Term

- Stabilize repository layout and public package names.
- Publish core, drivers, and clients under the MIT License.
- Document Docker Compose deployment with PostgreSQL.
- Define a stable mount schema format for dynamic client forms.
- Expand driver tests for GitHub, GitLab, Gitea, WebDAV, and Zotero.
- Publish a minimal contributor workflow that starts a local VeryFS.Server
  instance from source.

## Core

- Runtime driver loading.
- Capability negotiation.
- Signed service and user request authentication.
- ACL and ownership management APIs.
- Version-safe writes and configurable retention.
- Workspace export for external tools.

## Server

- Keep `VeryFS.Server` as the reference ASP.NET Core host for the Core library.
- Harden Docker Compose deployment with PostgreSQL, health checks, and secrets.
- Provide OpenAPI descriptions for mount management, filesystem operations,
  permissions, and workspace export.
- Add operational guides for reverse proxies, TLS termination, logging, and
  production security modes.

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
- Build a VeryFS CLI client for shell-first workflows, scripting, workspace
  export, mount inspection, and diagnostics.
- Evaluate building the CLI on top of
  [HIT-ReFreSH/MobileSuit](https://github.com/HIT-ReFreSH/MobileSuit) so it can
  share command structure, styling, and plugin conventions with existing
  HitRefresh tooling.
- Build a VeryFS Web client for browsing files, managing mounts, inspecting
  permissions, testing driver connections, and viewing cache/version metadata.

## AI Integrations

- Design and implement a VeryFS MCP server so MCP-compatible AI tools can
  browse mounted resources, read files, inspect manifests, and materialize
  workspaces through scoped permissions.
- Provide agent-oriented workspace export profiles for Codex, Claude Code, and
  other coding or knowledge agents.
- Expose manifest, recent, provenance, cache policy, and version metadata in
  forms that are efficient for tool calls and safe for large repositories.
- Add examples showing signed user requests, least-privilege mounts, and
  no-cache or metadata-only remote mounts for privacy-sensitive workflows.

## Packaging and Distribution

- Publish NuGet packages for Core, Server, driver abstractions, local driver,
  and .NET clients.
- Publish Python and TypeScript clients to their native package ecosystems once
  the public API contract stabilizes.
- Prepare repository templates and conformance tests for third-party driver
  authors.
