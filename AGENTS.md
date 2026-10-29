# AGENTS.md

This is an awesome list with no code. All content is in `README.md`. Entry formats and inclusion rules are in `CONTRIBUTING.md`. Read it before adding anything, and follow it exactly.

## Editing README.md

- Sections `00`–`10` follow the layers of a home-ops repo. If you rename or renumber a section, update its row in the `The Map` code block, the anchor table under it, and the nav links at the top.
- Tools within a layer are ordered by how often home-ops repos use them, not alphabetically. Put a new tool where it fits and give the reason in the PR. The Blogs and YouTube lists under `Explore` are alphabetical.
- Separators are different by entry type. Tool and Read entries use ` - ` (a hyphen). In the wild entries use ` — ` (an em dash): `- **owner** — [path/](url)`.
- Tables (`10 Apps`, `Real Repos`) use padded, aligned columns. When you add a row, re-pad the whole table, for example with `npx prettier --write README.md`. Prettier isn't installed globally.
- A GitHub alert marker such as `> [!TIP]` has to sit on its own line, with the body on the next `>` line. If both are on one line (`> [!TIP] > ...`), the alert doesn't render. Check this after running a formatter.
- Only add free resources from maintained projects (a commit in the last 12 months). Use the canonical URL after redirects and repo renames.

## Verification

CI (`.github/workflows/lint.yml`) only checks links, using lychee. To run the same check locally:

```sh
lychee --config lychee.toml README.md CONTRIBUTING.md
```

- `lychee.toml` skips reddit, discord.gg, and youtube links because those sites block bots. Open those links by hand.
- The config accepts 403 and 429 responses, so a passing run doesn't prove a link points to the right page. When a repo reorganizes, In the wild and "Start reading at" links to `tree/main/<path>` often break or move. Check that each path still exists.

## Git

- Commit messages use the prefix of the area they change: `readme: add <owner>/<repo> to Real Repos`, `lychee: ...`.
- Make one pull request per addition, filled out with `.github/pull_request_template.md`.
