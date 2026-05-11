# amalgame-lang/packages-index

Curated index of official and community-listed packages for the
[Amalgame](https://github.com/amalgame-lang/Amalgame) language.

`amc add <shortname>@<tag>` looks up this file to resolve a
shortname (e.g. `redis`) to a full git URL (e.g.
`github.com/amalgame-lang/amalgame-database-nosql-redis`).
Without this index, users would always have to type the long
form.

## Browse

See [`packages.toml`](packages.toml) for the full machine-
readable list. Each entry has:

| Field | Meaning |
|---|---|
| `name` | Shortname used in `amc add <name>@<tag>` |
| `url` | Full git URL (`github.com/owner/repo`) |
| `description` | One-line summary |
| `tier` | `official` (under `amalgame-lang/`) or `listed` (third-party verified) |
| `maintainer` | GitHub handle or org |
| `license` | SPDX identifier |
| `category` | `database`, `messaging`, `format`, etc. |
| `verified_on`, `verified_by` | For `listed` tier only |

## Trust tiers

### Official — `amalgame-lang/*` packages

Hosted under the `amalgame-lang` GitHub organization, maintained
directly by Bastien Mouget. Strongest trust signal: the package
is part of the canonical Amalgame ecosystem, follows the same
release cadence and quality bar as the compiler.

### Listed — third-party packages

Hosted at the author's own GitHub (or other git host) URL. The
listing on this index is a "yes, I've reviewed this and it's
reasonable" stamp — not an ownership transfer. The author keeps
copyright; the code stays at their URL; we just maintain the
pointer so `amc add` can resolve the shortname.

Review criteria for inclusion:
- The repo exists, builds, and its own CI is green.
- The manifest declares a non-empty `license` compatible with
  Apache-2.0 redistribution.
- The README honestly describes what the package does.
- The author isn't impersonating an existing project.

### Unlisted — anything else

Any package the user installs via the full URL form
(`amc add github.com/foo/bar@v1.0.0`) works fine but installs
with an "⚠ unverified" warning. Users are responsible for their
own due-diligence on unlisted packages.

## Adding a package

Open a PR adding a new `[[package]]` block to
[`packages.toml`](packages.toml). Make sure your repo's CI is
green before requesting review.

## Removal

Open a PR removing the entry. Reasons we'd remove:
- Repo deleted / 404
- License changed to something incompatible
- Maintainer asks
- Discovered to be malware

## Licence

The packages-index data itself is licensed Apache-2.0 (see
[`LICENSE`](LICENSE)). Each individual listed package keeps its
own licence — refer to that package's `amalgame.toml` or repo.
