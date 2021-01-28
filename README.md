# Swimm Verify GitHub Action
Verify Swimm units as part of your workflow.

## Usage
Follow the example below to verify your Swimm units on Pull-Requests. 
  
```yaml
name: Swimm
on: pull_request
jobs:
  Verify:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0 # pulling the commits history is required for the verification to function properly
      - uses: actions/setup-node@v2
        with:
          node-version: '14'
      - uses: actions/swimm-verify-action@v1
```