# Mjolnir

Close issues related to the merge of a pull request.

Useful:

- to close multiple issues related to a pull request.
- to close issues related to a pull request not based on the default branch (i.e. `master`).
For example, when a branch is related to version (e.g. `v1.5`, `v2.0`, ...)

## Supported Syntaxes

- prefixes (case insensitive): `close`, `closes`, `closed`, `fix`, `fixes`, `fixed`, `resolve`, `resolves`, `resolved`
- issues references separators (can be mixed): ` ` (space), `,` (period)
- prefix and issues references can be separated by: ` ` (space), `:` (colon), or both.

Examples:

```
Fixes #1,#2,#3
close #1, #2, #3
fix #1 #2 #3
resolve #1,#2 #3
Resolves: #1,#2,#3
closed : #1, #2, #3
```

## Usage

```yaml
name: Close issues related to a merged pull request based on master branch.

on:
  pull_request:
    types: [closed]
    branches:
      - master

jobs:
  closeIssueOnPrMergeTrigger:

    runs-on: ubuntu-latest

    steps:
      - name: Closes issues related to a merged pull request.
        uses: Skyyo/gha-mjolnir@v1.0.3
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
