---
name: update-github-info
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[ai] "
    draft: true
---

Read `notes/mona-notes.md` to understand Mona's editorial guidelines for the website.

Fetch the latest content from these three URLs using web-fetch:
- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Review `site/content/github-info.md` to understand the current content.

Update `site/content/github-info.md` with a concise summary of the most notable recent items from the GitHub Blog, GitHub Changelog, and Awesome Copilot workflows. Follow Mona's editorial guidelines from `notes/mona-notes.md`:
- Keep summaries short and practical.
- Prefer updates that help developers learn GitHub faster.
- Mention the source whenever a change comes from the GitHub Blog or GitHub Changelog.

Open a pull request with the updated `site/content/github-info.md` file for Mona to review.
