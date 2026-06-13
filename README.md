# VeryFS

VeryFS is an AI-native Virtual File System for connecting applications,
automation tools, and AI agents to heterogeneous knowledge and storage sources.

It provides a Unix-style namespace over mounted resources such as local
directories, Git repositories, WebDAV endpoints, remote VeryFS instances, and
research libraries. The project is designed around a small core, pluggable
drivers, language clients, and workspace export paths that are friendly to
agentic coding and research workflows.

## Why AI-Native

Most filesystems are built for human-operated applications first. VeryFS treats
AI agents as first-class users of the filesystem contract:

- **Stable workspace views**: external tools can receive a predictable
  workspace layout instead of bespoke application APIs.
- **Mount-aware provenance**: files can retain their source driver, mount path,
  ETag, version hints, and cache policy so agents can reason about where data
  came from.
- **Capability-based access**: drivers declare supported operations such as
  list, stat, read, write, manifest, recent, materialize, and versioning before
  an agent attempts an action.
- **Least-privilege integration**: user-scoped mounts, ACLs, signed requests,
  secret references, and remote mount cache policy are part of the core design.
- **Agent-friendly discovery**: manifest and recent queries help agents inspect
  large workspaces without recursively crawling every mounted source.
- **Data-safety bias**: cache, versioning, and retention work is designed around
  preserving user data first, even when storage usage is higher in early
  deployments.

## Goals

- Provide a stable VFS API for files, directories, mounts, and links.
- Keep the core independent from application-specific business logic.
- Support drivers for common storage and knowledge systems.
- Make resources available to AI agents and external tools through predictable
  workspaces.
- Prefer mature protocols and implementation techniques over custom formats.

## Repository Index

The project is split into focused repositories:

| Repository | Purpose |
| --- | --- |
| `VeryFS.Core` | Core API, metadata storage, ACLs, virtual namespace, local driver, and driver abstractions. |
| `VeryFS.Drivers` | Driver packages for Git providers, WebDAV, Zotero, remote VeryFS, and shared driver utilities. |
| `VeryFS.Clients.CSharp` | C# SDK for the VeryFS API. |
| `VeryFS.Clients.Python` | Python SDK for the VeryFS API. |
| `VeryFS.Clients.TypeScript` | TypeScript SDK for the VeryFS API. |
| `VeryFS` | Project overview, roadmap, contribution guide, and repository index. |

This repository will later include the other repositories as Git submodules.

## Current Status

VeryFS is pre-1.0 software. APIs and driver contracts may change while the
project converges on a stable plugin and client model.

The current implementation focuses on:

- ASP.NET Core based VeryFS Core service.
- PostgreSQL-backed metadata and secret storage.
- User-scoped access control and signed request support.
- Virtual directories and links.
- Repository, WebDAV, Zotero, remote VeryFS, and local filesystem drivers.
- C#, Python, and TypeScript client repositories.

## License

VeryFS is released under the MIT License.
