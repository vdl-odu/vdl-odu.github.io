# vdl-odu.github.io

Public website of the Valkyrie Defense Lab at Old Dominion University.

- **Live address:** https://vdl-odu.github.io/
- **Built with:** [al-folio](https://github.com/alshedivat/al-folio) v1.2 (Jekyll), MIT license
- **Build plan and content rules:** [WEBSITE_PLAN.md](WEBSITE_PLAN.md). Read section 3 before editing any page.

## Where the content lives

| Page | File |
| --- | --- |
| Home | `_pages/about.md` |
| Research (one card per area) | `_pages/research.md` and `_projects/*.md` |
| Publications | `_bibliography/papers.bib` |
| Team | `_pages/team.md` |
| Facilities | `_pages/facilities.md` |
| Outreach | `_pages/outreach.md` |
| News | One Markdown file per item in `_news/` |
| Join | `_pages/join.md` |
| Site settings | `_config.yml` |
| Logos | `assets/img/` (ODU logos go in `assets/img/odu/`) |
| Lab authors highlighted in publications | `_data/lab_members.yml` (opted-in members only) |

Every placeholder is marked `[TODO`. Search for it to see what is left before launch.

## Run it locally

With Docker installed:

```bash
docker compose pull
docker compose up
```

Then open http://localhost:8080/. See `docs/INSTALL.md` for other options.

## Publishing

- Pushing to `main` builds the site and publishes it (the `Deploy site` workflow writes the `gh-pages` branch).
- **Until launch, work on the `prototype` branch and do not merge to `main`.** This repository is public, so the source is visible, but nothing is published until `main` changes.
- One-time setup after the first deploy: Settings, Pages, Source: **Deploy from a branch**, Branch: `gh-pages`.
