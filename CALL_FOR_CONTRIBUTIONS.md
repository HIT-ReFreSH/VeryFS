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

## Start a Minimal Development Instance

Clone the umbrella repository with submodules:

```powershell
git clone --recurse-submodules https://github.com/HIT-ReFreSH/VeryFS.git
cd VeryFS
```

Fastest path, using the JSON metadata store and permissive security mode:

```powershell
dotnet build .\VeryFS.Core\src\VeryFS.Core\VeryFS.Core.csproj
dotnet build .\VeryFS.Server\src\VeryFS.Server\VeryFS.Server.csproj
dotnet run --project .\VeryFS.Server\src\VeryFS.Server\VeryFS.Server.csproj
```

In another terminal:

```powershell
curl http://localhost:5000/health
curl http://localhost:5000/v1/drivers
```

If your local ASP.NET Core profile chooses another port, use the URL printed by
`dotnet run`.

To run the minimal test suite:

```powershell
cd VeryFS.Core
dotnet run --project .\tests\VeryFS.Core.Tests\VeryFS.Core.Tests.csproj
```

Docker Compose is available from `VeryFS.Server` for a closer-to-deployment
instance. It expects a PostgreSQL connection string and uses the repository
parent as the build context so Core and driver projects can be copied into the
image:

```powershell
cd VeryFS.Server
$env:VERYFS_POSTGRES_CONNECTION="Host=localhost;Port=5432;Database=postgres;Username=postgres;Password=postgres"
docker compose up --build
curl http://localhost:5080/health
```

For first-time contributors, start with the direct `dotnet run` path. Use
Docker Compose when working on packaging, PostgreSQL metadata, authentication,
or deployment behavior.

## Design Topics Open for Discussion

- Runtime driver loading and compatibility guarantees.
- Driver capability negotiation.
- Versioning interfaces for Git-backed and remote-backed resources.
- Cache retention, encrypted cache, and privacy-preserving remote mounts.
- Workspace export for external tools and agents.

## License

VeryFS is MIT licensed. Contributions must be compatible with the MIT License.
