# Call for Contributions

VeryFS is looking for contributors interested in virtual filesystems,
knowledge tooling, storage integrations, and AI-friendly workspaces.

The project is still early. This is a good time to influence the API shape,
driver contract, security model, and developer experience.

## We Are Looking For

- Driver maintainers for GitHub, GitLab, Gitea, WebDAV, Zotero, and other
  storage or knowledge systems.
- Client SDK contributors for C#, Python, and TypeScript.
- ASP.NET Core contributors for API design, authentication, authorization,
  metadata storage, and deployment hardening.
- Security reviewers for ACLs, signed requests, secret storage, cache policy,
  and remote mount behavior.
- Documentation contributors for examples, tutorials, deployment guides, and
  driver authoring guides.

## Good First Contributions

- Add integration tests for a driver using deterministic mock HTTP fixtures.
- Improve a client SDK method and document its usage.
- Document mount configuration for a provider.
- Add examples for browsing files, creating mounts, and reading content.
- Review cache behavior and propose a retention policy.

## Design Topics Open for Discussion

- Runtime driver loading and compatibility guarantees.
- Driver capability negotiation.
- Versioning interfaces for Git-backed and remote-backed resources.
- Cache retention, encrypted cache, and privacy-preserving remote mounts.
- Workspace export for external tools and agents.

## License

VeryFS is MIT licensed. Contributions must be compatible with the MIT License.
