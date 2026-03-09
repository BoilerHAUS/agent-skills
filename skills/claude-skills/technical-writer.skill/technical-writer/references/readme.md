# README Template

Every software project README follows this structure. Sections marked (required) must always
be present. Others are included when applicable.

---

```markdown
# Project Name

> One-sentence tagline. What it does and for whom.

[![Build Status](badge-url)](link) [![License](badge-url)](link)  <!-- optional badges -->

Brief paragraph (2–4 sentences) expanding on the tagline. What problem does this solve?
What makes it notable? Who is the intended user?

## Requirements (required if non-trivial)

- Node.js 18+
- PostgreSQL 14+
- An API key from [Service Name](https://example.com)

## Installation (required)

Step-by-step. Every command on its own line.

```bash
npm install my-package
```

For monorepos or multi-step setups:

```bash
git clone https://github.com/org/repo.git
cd repo
npm install
cp .env.example .env
```

## Configuration (required if applicable)

List every environment variable or config file option.

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `API_KEY` | Yes | — | Your API key from the dashboard |
| `PORT` | No | `3000` | Port to listen on |
| `LOG_LEVEL` | No | `info` | One of: `debug`, `info`, `warn`, `error` |

## Usage (required)

Show the most common use case first. Then cover variations.

```bash
my-tool --input file.json --output result.json
```

For libraries, show a minimal working code example:

```javascript
import { Client } from 'my-package';

const client = new Client({ apiKey: process.env.API_KEY });
const result = await client.doThing({ param: 'value' });
console.log(result);
```

## API (required for libraries)

Brief overview with a link to full API reference if it exists elsewhere.
Or embed key functions inline for smaller libraries.

## Examples (recommended)

Link to or embed a few real-world use cases beyond the minimal example.

## Development (required for open source)

How to set up a local development environment and run tests.

```bash
npm run dev        # start dev server
npm test           # run test suite
npm run lint       # lint and format
```

## Contributing (required for open source)

Brief guidelines or a link to CONTRIBUTING.md.

## License (required)

[MIT](LICENSE) — or whatever applies.

## Acknowledgements (optional)

Credit dependencies, inspirations, or contributors.
```

---

## Style Notes for READMEs

- The first code block a reader sees should be the fastest path to a working result.
- Never start with history, motivation, or philosophy. Start with what it does and how to install it.
- Badge soup (10+ badges) is a red flag. Use only badges that convey real-time status.
- Keep the README focused on getting started. Long reference content belongs in separate docs.
- For AI agent consumption: ensure all config options are in a table with types and defaults,
  not scattered through prose.
