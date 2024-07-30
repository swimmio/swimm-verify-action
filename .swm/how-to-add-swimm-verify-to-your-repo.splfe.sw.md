---
title: How to add Swimm Verify to your Repo?
---
## Before we start, just letting you know...

### Swimm is on GitHub Marketplace! 🎉

We built a smart bot🤖 that helps keeping your internal documentation up to date!

Want to learn more? Check out our [docs site](https://docs.swimm.io/docs/continuous-integration/github-app) or install our GitHub app [here](https://github.com/apps/swimm-io)

**If you prefer, this is how to use the GitHub Swimm Verify workflow**

# Swimm Verify GitHub Action

Verify Swimm units as part of your workflow.

## Usage

Running verification on your repo could be done by using [GitHub Actions](https://docs.github.com/en/actions/quickstart), by adding a simple workflow to your repo.

Follow the example below to verify your Swimm units on Pull-Requests:

In your repository, create a new file named <SwmPath>[.github/workflows/swimm_verify.yml](/.github/workflows/swimm_verify.yml)</SwmPath>. This file describes the workflow steps that will run on your pull request.

(If you are not familiar with the syntax, head over to [this link](https://www.codeproject.com/Articles/1214409/Learn-YAML-in-five-minutes) to learn more)

<SwmSnippet path="/.github/workflows/swimm_verify.yml" line="1">

---

In your new workflow file, write down this content.

If you prefer, you can control **when** will this check run, by replacing the <SwmToken path="/.github/workflows/swimm_verify.yml" pos="3:0:0" line-data="on: pull_request">`on`</SwmToken> definition.

You can also control the **operating system** that the workflow will run over by replacing <SwmToken path="/.github/workflows/swimm_verify.yml" pos="7:6:8" line-data="    runs-on: ubuntu-latest">`ubuntu-latest`</SwmToken> with another OS.

```yaml
name: Swimm Verify

on: pull_request

jobs:
  Verify:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
          ref: ${{ github.head_ref }}
      - uses: swimmio/swimm-verify-action@v1.3
```

---

</SwmSnippet>

Once added to your repository, it should look like that on pull requests (when all of your documents are verified 😉)

<p align="center"><img src="https://firebasestorage.googleapis.com/v0/b/swimmio-content/o/repositories%2FZ2l0aHViJTNBJTNBc3dpbW0tdmVyaWZ5LWFjdGlvbiUzQSUzQXN3aW1taW8%3D%2F295d4c50-75da-497a-beb7-22f9c995b935.png?alt=media&amp;token=eb319251-3f1e-4143-b120-03e67cf5a6d4" style="width: 100%"></p>

Have fun Swimming! 🏊‍♀️🏊

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc3dpbW0tdmVyaWZ5LWFjdGlvbiUzQSUzQXN3aW1taW8=" repo-name="swimm-verify-action"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
