---
name: weekly-report-status
description: Review recent repository activity and produce a concise weekly status report.
on:
  schedule:
    - cron: "0 9 * * 1"
  workflow_dispatch:
permissions:
  contents: read
  copilot-requests: write
engine: copilot
strict: true
tools:
  edit: true
---

# Weekly Report Status

Review the repository state for the past week and summarize the most relevant updates in a concise report.

- Inspect recent repository changes, open issues, and pull requests when available.
- Summarize the current status clearly and concisely.
- If there are no meaningful updates, say so directly.
