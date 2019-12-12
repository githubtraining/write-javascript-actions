## Using your new Action

At this point we can't expect much from our workflow, if you remember all of its contents are commented out. Let's go ahead and fix that now so that we can see our Action fetch us a joke.

### :keyboard: Activity: Restore the workflow file

The great news is that we only need to add a call to our new Action. Follow these steps to do so:

1. [Edit]({{workflowFile}}) your current workflow file
2. Uncomment the contents of the file
3. Add a new `step:` that has a `name:` of **ha-ha** and`uses:` your new `joke-action`
4. Commit the changes to the `action-two` branch
5. Check the workflow results on the [Actions tab]({{actionsUrl}})

I'll respond once I notice your workflow has completed

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

      - name: hello-action
        uses: ./.github/actions/hello-world

      - name: ha-ha
        uses: ./.github/actions/joke-action
```

</details>
