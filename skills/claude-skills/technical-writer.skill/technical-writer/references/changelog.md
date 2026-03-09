# Changelog Template

Follow the [Keep a Changelog](https://keepachangelog.com) format. Changelogs are for humans
(and AI agents consuming release data), not git logs.

---

## Core Principles

- **Changelogs are not commit logs.** Summarize user-facing impact, not implementation details.
- **Group by change type**, not by component or author.
- **Newest version at the top.**
- **Every version has a release date.**
- **Mark breaking changes explicitly** — never bury them.

---

## Standard Format

```markdown
# Changelog

All notable changes to this project are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
This project uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added
- Description of new feature (links to docs or PR where helpful)

### Changed
- Description of change to existing functionality

### Deprecated
- Features that will be removed in a future release

### Removed
- Features removed in this release

### Fixed
- Bug fixes

### Security
- Security fixes — always include CVE ID if applicable

---

## [1.2.0] — 2024-03-15

### Added
- `POST /v1/webhooks` endpoint for real-time event delivery (#234)
- `--dry-run` flag on the CLI to preview changes without applying them

### Changed
- Rate limit headers now use the standard `RateLimit-*` format (was `X-RateLimit-*`)

### Fixed
- Pagination cursor was reset incorrectly when `filter` param changed (#198)

---

## [1.1.0] — 2024-02-01

### ⚠️ Breaking Changes

- Removed `legacy_mode` config option. Migrate using the [upgrade guide](link).
- `user.name` field renamed to `user.display_name` in all API responses.

### Added
- Support for webhook signature verification
- Japanese locale

### Fixed
- Memory leak in the connection pool under high load

---

## [1.0.0] — 2024-01-10

Initial stable release.
```

---

## Change Type Definitions

| Type | Use for |
|------|---------|
| `Added` | New features, new endpoints, new config options |
| `Changed` | Behavior changes to existing features (non-breaking) |
| `Deprecated` | Features that still work but will be removed |
| `Removed` | Features removed in this release |
| `Fixed` | Bug fixes |
| `Security` | Vulnerability fixes |

---

## Breaking Change Rules

- Always mark breaking changes with `⚠️ Breaking Changes` as a subsection before other changes.
- Include a migration path or link to an upgrade guide for every breaking change.
- Never bury a breaking change inside `Changed` without calling it out.

---

## Style Notes

- Write changelog entries in past tense: "Added support for X", not "Adds support for X."
- Be specific: "Fixed pagination cursor reset bug (#198)" not "Fixed a bug."
- Link to PRs, issues, or docs where useful — but don't require them.
- For AI agent consumption: use consistent category headings and version number format
  so changelogs are reliably parseable. Never use freeform section names.
