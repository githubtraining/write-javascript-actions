## Breaking our workflow

Before we continue we are going to need to do a few things. First and foremost our workflow is currently setup to run each time there is a `push` event to this repository. Let's comment out our current workflow to prevent things from running but preserve the things you've worked on up to this point.

### :keyboard: Activity: Setting up the next Action

1. [Edit]({{workflowFile}) your workflow file by commenting out every single line.
2. Commit the changes to a new branch and name it `action-two`.
3. Create a pull request named **External APIs**

You will still see the workflow trying to execute with every push if you look at the [Actions tab]({{actionsUrl}}), however it will seem as though it fails. This is because there is a workflow file in the `.github/workflows` directory. The failure isn't actually a failure either, if you expand it you will see that there is simple no triggers for that given workflow and therefore it doesn't run. I have placed a screenshot below so you can become familiar with what this error looks like without the need to go to your [Actions tab]({{actionsUrl}}).

![No trigger screenshot](https://i.imgur.com/rARtXc1.png)
Like our first Action, I'll respond in the new pull request when I detect it has been opened.

---

<details><summary>The complete workflow can be viewed by clicking here</summary>

```yaml
# name: JS Actions

# on: [push]

# jobs:
#   action:

#     runs-on: ubuntu-latest

#     steps:
#     - uses: actions/checkout@v1

#     - name: hello-action
#       uses: ./.github/actions/hello-world
```

</details>
