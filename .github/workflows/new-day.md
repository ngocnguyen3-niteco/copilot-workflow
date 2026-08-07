---
name: new-day
description: Add a daily update entry for the workflow run UTC date and open a pull request if the page changes.
on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:
permissions:
  contents: read
  copilot-requests: write
engine: copilot
strict: true
tools:
  edit: true
safe-outputs:
  create-pull-request:
    allowed-files:
      - index.html
    max: 1
---

# New Day

Update the daily updates section in index.html for the current UTC date.

- Determine the current UTC date from the workflow run environment (for example with `date -u`).
- If the UTC date is already present in the Daily Updates navigation and matching dialog, make no change.
- Preserve every existing daily update and do not modify styles.css.
- Add a new navigation control in the existing Daily Updates list using the same button structure and wording pattern as the existing entries.
- Add a matching accessible dialog with the same structure and styling as the existing dialogs.
- Ensure the new navigation control and dialog use IDs derived from the UTC date in the same convention as the existing entries.
- Only change index.html.
- If the file changes, create a pull request with the update.
