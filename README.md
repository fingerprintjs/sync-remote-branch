# Github Actions: sync repository

![Build status](https://github.com/fingerprintjs/sync-repository/actions/workflows/build.yml/badge.svg)

## Action
* Synchronize changes from the specified repository to the current one

## Inputs
#### `source` (Required)
The URL (HTTPS protocol only; SSH isn't supported) to the repository from which updates will be applied.
The repository must be publicly available.

#### `branch` (Optional)
The name of the branch to update.
The default value is `main`.

## Example usage
```yaml
name: Update worker's repository from the public template

on:
  # Add cron expression if you need to update automatically periodically
  schedule:
  - cron: "0 0 * * *"
  # Used for a manual run from Github Actions
  workflow_dispatch:

jobs:
  update:
    steps:
      - uses: actions/checkout@v2
      
      - name: Get updates from the public template and merge into the repository branch
        uses: fingerprintjs/sync-remote-branch@v1.0.0
        with:
          source: https://github.com/fingerprintjs/fingerprintjs-pro-cloudflare-worker.git
          branch: master
```
