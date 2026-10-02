---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read

tools:
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  report-failure-as-issue: false
  create-pull-request:
    title-prefix: "Update GitHub info: "
    draft: false
    max: 1
---

# Update GitHub Info

Keep Mona's GitHub Info website current with practical, official GitHub updates.

## Sources and context

1. Read `notes/mona-notes.md` and `site/content/github-info.md` before making changes.
2. Use web-fetch to read each of these pages on every run:
    - https://github.blog/latest/
    - https://github.blog/changelog/
    - https://awesome-copilot.github.com/workflows/
3. Select only recent items that are relevant to the website's existing themes and useful to developers learning GitHub. Verify each item's date and details from its official source. Do not invent or infer unsupported claims.

## Update

- Edit only `site/content/github-info.md`.
- Keep summaries short and practical, preserve the existing editorial direction, and link each new item directly to its GitHub Blog or Changelog source.
- Add or refresh a concise recent-updates section with dates and source links. Avoid duplicating items already present; replace stale entries when useful.
- If neither source has a relevant item that warrants a change, leave the file unchanged.

## Review

When the file changes, use the `create-pull-request` safe output to open one pull request for Mona to review. Summarize the updates and include their official source links in the pull request description. Do not write directly to the default branch or use any other mechanism to publish changes.

## Latest updates

- New agentic workflow examples are available in the Awesome Copilot collection.
  Source: https://awesome-copilot.github.com/workflows/
- Recent GitHub product news is published on the GitHub Blog.
  Source: https://github.blog/