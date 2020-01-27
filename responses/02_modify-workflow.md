## Edit the current workflow

Currently `my-workflow.yml` is not set up correctly for our use-case. It worked great for allowing us to take a high-level look at workflows, but if we want to use our custom actions there are some changes that we have to make to it.

### :keyboard: Activity: Modify my-workflow.yml to remove boilerplate steps

1. [Edit]({{workflowFile}}) the `my-workflow.yml`.
2. Change the `name:` property located on `line 1` of `my-workflow.yml` to `JS Actions`
3. Rename the job from `build` to `action`
4. Remove the two steps that run commands, but leave the step that runs the checkout action.
5. Commit these file changes to this branch

I'll respond in this pull request once you make these changes.

---

<details><summary>The complete workflow can be viewed by clicking here</summary>

```yaml
name: JS Actions

on: [push]

jobs:
  action:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v1
```

</details>
