---
name: update-github-info
description: Refresh Mona's GitHub Info page with practical updates from the official GitHub Blog and Changelog.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
network:
  allowed:
    - defaults
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[github-info] "
---

# Update GitHub Info

Read `notes/mona-notes.md` and `site/content/github-info.md` before making any changes. Use Mona's editorial guidance and the current page themes to avoid duplicating existing content.

Use the web-fetch tool to read both official sources:

- https://github.blog/latest/
- https://github.blog/changelog/

Choose only recent, noteworthy updates that provide practical value to developers using GitHub. Verify every factual claim against the fetched pages, keep summaries short, and link each new item to its original source. Do not invent details or make changes when there is no useful update to add.

Edit only `site/content/github-info.md`. Preserve its existing structure and editorial voice, and do not change unrelated files. Review the resulting content for accuracy, concise wording, working source links, and consistency with Mona's notes.

When there is a meaningful update, use the `create-pull-request` safe output to open a pull request proposing the page changes for Mona to review. Give the pull request a clear title and summarize the cited updates in its description. Do not write directly to `main`, merge the pull request, or assume Mona's GitHub username.