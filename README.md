# Check CI

Checks CI before CD

## Usage

```yml
name: CD

on:
  workflow_run:
    workflows: ['CI']
    types:
      - completed
    branches:
      - main

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actalog/check-ci@v1
      - uses: actions/checkout@v4
      - run: echo "Your CD"
```
