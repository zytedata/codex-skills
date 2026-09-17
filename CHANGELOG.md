This file is 55 lines long; read all of them.

# Changelog

## 0.3.0 (2026-09-17)

### Changed

- The skill lineup has been consolidated: the skills are now `/scrape`,
  `/scrape-plan`, `/scrape-analyze-page`, `/scrapy-extra` and `/zyte`.
  - The new `/scrape-plan` skill replaces `/scrape-define`, `/scrape-spec`,
    `/scrape-explore-site` and `/scrape-review-schema`: it plans a web scrape
    end to end — explores a detail page, discovers fields, confirms the
    schema, validates it against more pages and presents the finalized plan
    for approval.
  - The new `/zyte` skill replaces `/scrape-scrapy-cloud`,
    `/scrape-zyte-api-stats` and `/scrape-zyte-login`: one skill for anything
    about Zyte.
  - `/scrape` now drives spider and page-object generation directly; the
    internal `/scrape-codegen`, `/scrape-create-spider`,
    `/scrape-add-page-object` and `/scrape-ensure-project` subskills are gone.

### Added

- The new `/scrapy-extra` skill provides up-to-date guidance for writing,
  modifying, debugging and explaining Scrapy, scrapy-poet, scrapy-zyte-api and
  web-poet code. It complements the `scrapy` skill of the official
  [Scrapy agent plugin](https://github.com/scrapy/scrapy-agent-plugin).
- `/zyte` also answers Zyte API pricing and cost questions (plans, tiers,
  discounts, cost estimates) and how-to questions about any Zyte product,
  sourced from docs.zyte.com.
- After a `/scrape` run finishes, a cooldown-gated prompt may ask how the
  scraping session went, so you can send feedback to the Zyte team.

### Improved

- `/scrape`: generated code now prefers browser dependencies declared by page
  objects over the `browserHtml` automap, producing more reliable spiders for
  JS-rendered sites.
- `/scrape`: now also works when run inside an existing Scrapy project,
  instead of always creating a new one.
- `/zyte`: guidance reorganized into targeted how-to references loaded on
  demand, improving accuracy while using less context.
- Skill instructions were tuned for Codex CLI.
- Page analysis now produces compact summaries, reducing context passed back
  to the orchestrating skill.

### Fixed

- Improved Windows compatibility through portable credential handling, `uv`
  invocations and command guidance that no longer assume a POSIX shell.

## 0.2.3 (2026-07-16)

Initial release.
