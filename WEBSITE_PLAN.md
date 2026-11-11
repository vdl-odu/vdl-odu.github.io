# Valkyrie Defense Lab Website: Build Plan

**Owner:** Gul
**Approver:** Dr. Katherine Smith
**Prepared:** 2026-11-11
**Time budget:** prototype (Milestones 0 to 2) in about 2 weeks at roughly 8 hours a week, running in parallel with the driving simulator work.

This file is written so you can hand it to Cursor one milestone at a time. Keep it in the root of the website repo.

---

## 1. Goal

A public lab website that:

1. Explains what the lab does in plain language for students, sponsors and collaborators.
2. Lists publications automatically from a BibTeX file.
3. Recruits students through a Join page with open projects and an interest form.
4. Can be maintained by students by editing small Markdown files, without touching the design.

**Reference site:** https://nail-uh.github.io/ (built with the al-folio template).

## 2. Stack

- **Template:** al-folio (Jekyll, MIT license): https://github.com/alshedivat/al-folio
- **Hosting:** GitHub Pages.
- **Local preview:** al-folio's Docker setup (`docker compose up`), so no local Ruby install is needed.
- **Logos:** Valkyrie Defense Lab logo in `assets/img/` (SVG for light and dark mode, plus a shield favicon). ODU logos go in `assets/img/odu/` (see the README there).

**Address:** `https://vdl-odu.github.io/`

- **Organization:** `vdl-odu` (public). At least two owners, Katie and Gul, with two-factor authentication required.
- **Repository:** `vdl-odu/vdl-odu.github.io` (public).
- **Branches:** build on the `prototype` branch. Pushing to `main` publishes the site, so nothing merges to `main` until launch (Milestone 5).
- **Pages:** after the first deploy, Settings, Pages, Source: **Deploy from a branch**, Branch: `gh-pages` (al-folio's deploy workflow writes that branch).
- **Optional later:** a custom address such as an odu.edu subdomain, if ODU IT will add the DNS record.

## 3. Content rules (apply to every page)

These are not optional. Tell Cursor about them at the start of every session.

1. **No invented content.** Cursor must never write a publication, person, project result, partner or quote. Anything not supplied goes in as `[TODO: Katie]`.
2. **Sponsors and partners:** no sponsor or partner names or logos until Katie confirms each one has approved it. Use `[TODO: partner logos pending approval]`.
3. **People:** list only people who have opted in. Names, role and an optional photo only, nothing else about students.
4. **Nothing controlled or proprietary:** no technical details of sponsored work, no internal screenshots, no system names that are not already public.
5. **Style:** no em dashes anywhere on the site. Use commas, colons or parentheses instead. Plain, short sentences.
6. **Accessibility:** every image has alt text; color contrast meets WCAG AA; headings in order.
7. **ODU branding:** check ODU's web and wordmark guidelines before launch (Katie to confirm requirements).

## 4. Site map

| Page | Purpose | Content source |
| --- | --- | --- |
| Home | One-paragraph mission, research areas as cards, latest news, partner strip (empty until approved) | Katie provides mission text |
| Research | One section per research area, each with a short description and related publications | Draft blurbs below; Katie edits |
| Publications | Generated from `_bibliography/papers.bib` | Katie exports BibTeX from her CV data file |
| Team | Director, staff and students who opted in; alumni list | Katie provides list |
| Facilities | Lab capabilities: autonomous ground robots, motion capture, edge AI computing, driving simulator | Katie confirms what can be public |
| Outreach | ODU MathFest, ASNE student chapter, Marine Engineering minor | Katie provides links and photos |
| News | Short posts, newest first. First post: lab ribbon cutting, November 4, 2026 | Markdown posts in `_news/` |
| Join | Open projects (skills needed, hours, level), how to apply, link to the interest form | Katie provides project list each semester |

**Draft research area titles (Katie to edit before they go live):**

1. Cyber-physical resilience and autonomy testbeds
2. Trustworthy AI and retrieval for technical documentation
3. Edge and physical AI, moving into quantum
4. AI for competency and learning engineering

**Interest form:** use an ODU Microsoft Form and link to it. The form asks for interests, skills, availability and level only. It must not ask for GPA, grades or other education records.

## 5. Milestones

Work one milestone per branch, following the developer handbook's Git workflow (`feature/<issue>-website-<milestone>`, pull request, Katie or a reviewer approves).

### Milestone 0: Run the scaffold (about 2 hours)

The repo already holds a scaffold (Milestones 1 and 2 below, drafted 2026-11-11) on al-folio v1.2. It has **not been built yet**, because the build tools were not available where it was drafted.

- Run it locally with Docker (`docker compose pull`, then `docker compose up`).
- Fix any build errors. Likely spots: the removed example content and features (blog, CV, books, teaching) and the empty `papers.bib`.
- Check each page in the navigation renders.

**Done means:** the site builds with no errors and every page in section 4 loads locally.

**Cursor prompt:** "This al-folio v1.2 site does not build yet. Run the build, then fix errors with the smallest change, preferring `_config.yml` and content files over overriding gem layouts. Do not write any content. Follow AGENTS.md. Explain each change."

### Milestone 1: Skeleton (scaffolded; check it)

- Set the site title, URL and base URL in `_config.yml`.
- Create the pages in the site map with `[TODO: Katie]` placeholders.
- Remove al-folio features we do not use (for example blog, CV page, repositories page) so nothing empty shows.
- Set a simple color theme; check it in light and dark mode.

**Done means:** every page in the site map exists in the navigation, nothing else does, and the site builds without warnings.

**Cursor prompt:** "Using WEBSITE_PLAN.md section 4, create these pages with placeholder text marked [TODO: Katie]. Remove unused al-folio pages from navigation. Do not write any real content. Follow the content rules in section 3."

### Milestone 2: Content scaffolding (scaffolded; check it)

- Home: mission paragraph placeholder, four research area cards, news list.
- Research: one section per area with placeholder text.
- Facilities and Outreach: structure with placeholders.
- News: one post for the November 4, 2026 ribbon cutting with `[TODO: Katie]` body text.
- Join: a table of open projects (columns: project, skills, hours per week, level) with one example row clearly marked as an example, plus a link placeholder for the interest form.

**Done means:** Katie can review the full structure in one sitting and fill in text without asking where anything goes. **This is the prototype to show Katie.**

### Milestone 3: Publications (about 2 hours)

- Add `_bibliography/papers.bib` from Katie's export.
- Check that every entry renders, links (DOI or PDF) work, and Katie's name is highlighted.

**Done means:** the publications page matches the BibTeX file entry for entry.

### Milestone 4: Polish (about 3 hours)

- Mobile layout check at phone width.
- Accessibility check (alt text, contrast, heading order) and a link check.
- Lighthouse score of 90 or more for accessibility.

**Done means:** a short checklist in the pull request showing each check passed.

### Milestone 5: Review and launch

- Katie fills in or approves all `[TODO: Katie]` items.
- Confirm approvals: each sponsor or partner name and logo, each team member's opt-in, ODU branding.
- Move to the public location decided in section 2 and launch.

**Done means:** the site is live at its public URL and no `[TODO` strings remain (search the repo for them).

## 6. Maintenance after launch

| Task | How | Who |
| --- | --- | --- |
| Add news | New Markdown file in `_news/` | Any student, reviewed by Gul |
| Add a publication | Add the entry to `papers.bib` | Gul or Katie |
| Update open projects | Edit the Join page each semester | Katie supplies the list; Gul or a student edits |
| Add or remove team members | Edit the team data file after opt-in | Gul |

## 7. Questions for Katie before Milestone 2 review

1. Has ODU confirmed the `vdl-odu` organization may be public and use "ODU" in its name?
2. Mission paragraph and research area text.
3. Team list (opt-in only) and alumni.
4. Which facilities can be described publicly.
5. Which partners have approved being named, and their logo files.
6. BibTeX export of publications.
