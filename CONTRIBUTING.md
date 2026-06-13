# Contributing to VeryFS

VeryFS welcomes contributions in design, implementation, testing, driver
development, documentation, and operational hardening.

## Areas That Need Help

- Runtime driver loading and versioned driver contracts.
- Driver test harnesses for Git providers, WebDAV servers, and remote VeryFS.
- Client SDK ergonomics for C#, Python, and TypeScript.
- Security review for signatures, ACLs, cache policy, and secret handling.
- Cache retention and garbage collection policies.
- Documentation, examples, and deployment guides.

## Development Principles

- Keep the core small and independent from application-specific logic.
- Prefer protocol compatibility and predictable behavior over clever shortcuts.
- Treat data safety as a core requirement.
- Add focused tests for behavior that affects storage, permissions, or sync.
- Keep public APIs documented and stable once they are marked as supported.

## Contribution Flow

1. Open an issue describing the problem, design proposal, or driver target.
2. Keep pull requests small enough to review.
3. Include tests or a clear manual verification note.
4. Update documentation when behavior or public APIs change.
5. Use MIT-compatible dependencies unless there is a clear reason not to.

## Driver Contributions

New drivers should define:

- Provider name and mount configuration schema.
- Required credentials and minimum permissions.
- Supported capabilities such as list, stat, read, write, delete, rename,
  manifest, recent, materialize, and versioning.
- Caching behavior and invalidation strategy.
- Tests using deterministic mock HTTP or filesystem fixtures.
