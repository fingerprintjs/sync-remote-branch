# Github Actions: sync repository

## Action
* Synchronize changes from the specified repository to the current one

## Inputs
#### `source` (Required)
The URL (https only, SSH isn't supported there) to a repository to update from.
The repository must be publicly available.

#### `branch` (Optional)
The name of the branch to update.
The default value is `main`.

## Example usage
```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      - name: Update main branch of the repository from the another one
        uses: fingerprintjs/repository@v0.0.1
        with:
          source: https://github.com/fingerprintjs/cf-worker.git          
```
