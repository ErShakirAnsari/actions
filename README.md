# actions

GitHub Reusable Actions

# Dirty Git Repo

This action checks if there are any uncommitted changes in a specified repository and outputs whether the repository is
`dirty` or `clean`.

## Usage

### Example Workflow

```yaml
name: Check for Changes Workflow

on:
  push:
    branches:
      - main

jobs:
  check-for-changes:
    runs-on: ubuntu-latest
    steps:
      - name: Check for Changes
        uses: ershakiransari/actions/dirty-git-repo@main
        id: check
        with:
          directory: '/path/to/git/repo'

      - name: Display Result
        run: |
          echo "Repository dirty: ${{ steps.check.outputs.dirty }}"
```