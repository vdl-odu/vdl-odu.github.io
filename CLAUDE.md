# Instructions for coding agents (Cursor, Claude, Copilot)

This is the Valkyrie Defense Lab website, built on al-folio v1.2. Read `WEBSITE_PLAN.md` before making changes.

## Content rules (always)

1. Never invent content: no publications, people, results, partners, quotes or facts. Anything not supplied stays as `[TODO: Katie]`.
2. No sponsor or partner names or logos until Katie confirms approval.
3. People: only those who opted in. Name, role and an optional photo only.
4. Nothing controlled or proprietary: no technical details of sponsored work, internal screenshots, or system names that are not already public.
5. No em dashes anywhere. Use commas, colons or parentheses.
6. Accessibility: alt text on every image, WCAG AA contrast, headings in order.
7. ODU logos: use official files only, unchanged.

## Code rules

- Change content in `_pages`, `_projects`, `_news`, `_bibliography`, `_data` and `_config.yml` first.
- Layouts, includes and styles come from the `al_folio_core` gem and other `al-*` gems. Override one only when config and content cannot do the job, and say so in the pull request.
- If you add or remove a plugin, edit both `Gemfile` and the `plugins:` list in `_config.yml`.
- `baseurl` must stay empty (this is an organization site at the domain root).
- Check every change with a local build (`docker compose up`) before opening a pull request.

## Local overrides

- `_layouts/bib.liquid` overrides the al_folio_core 1.0.15 layout to style lab authors by role (`_data/lab_members.yml`, colors in `_includes/lab_author_styles.liquid`). When upgrading al_folio_core, re-copy the new layout and reapply the marked block.

The upstream al-folio documentation is in `docs/`.
