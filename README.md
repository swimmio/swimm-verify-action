# Swimm Verify GitHub Action

Verify Swimm units as part of your workflow.

## Usage

Follow the example below to verify your Swimm documentation on Pull-Requests. 
  
```yaml
name: Swimm
on: pull_request
jobs:
  Verify:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0 # pulling the commits history is required for the verification to function properly
      - uses: swimmio/swimm-verify-action@v1.3
```
