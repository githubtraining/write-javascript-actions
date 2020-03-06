## Edit the current workflow

Currently `my-workflow.yml` is not set up correctly for our use-case. It worked great for allowing us to take a high-level look at workflows, but if we want to use our custom actions there are some changes that we have to make to it.

### :keyboard: Activity: Modify my-workflow.yml to remove boilerplate steps

1. [Edit]({{workflowFile}}) the `my-workflow.yml` to have the following contents:
    ```yaml
    name: JS Actions

    on: [push]

    jobs:
      action:
        runs-on: ubuntu-latest

        steps:
          - uses: actions/checkout@v1
    ```
2. Commit these file changes to this branch

---

I'll respond in this pull request once you make these changes.


