## Action three

Two Actions down, one more to go! Before we move on with building our final Action let's take a second to do a quick recap since this lesson has thrown a lot of information at you.

**The Workflow**
We started out by explaining what a workflow is and how it pertains to the GitHub Actions platform. You learned about how a defined event sets your workflow orchestra in motion.

You learned about runners, jobs, steps and have dabbled in the syntax of a workflow file at every step in this course. I don't want to spoil too much here, but you'll be doing it again in this one as well 😉.

**Action Metadata**
You learned that every Action is accompanied by an `action.yml` file which contains a series of metadata for how the Action behaves. This file defines all of an Actions inputs, outputs, runtime environment, name, description and even branding.

**Hello Action**
Your first JavaScript Action took the traditional path of a "Hello World" introduction. You ended up expanding that Action to accept `inputs` to help make it a little more dynamic. Ultimately, the key takeaway was to understand that you can pass input that is defined in the workflow to an Action as long as the Action's metadata supports it.

When consuming or creating Actions it is incredibly helpful to take care to understand that Actions metadata file.

**Joke Action**
You second JavaScript Action demonstrated that your workflow environment is capable of communicating outside of it's own network. We reached out to an external API and used that information to set `outputs` for another Action to consume. As with `inputs` your Actions metadata must support the ability to set `outputs` if you want to use this option.

**What Next?**
Your third, and final, JavaScript Action of this course is going to use yet another library from the [Actions ToolKit](https://github.com/actions/toolkit). It is also going to consume the `outputs` of your joke Action and use them to help create issues in your repository.

We need to make some edits to the `my-workflow.yml` file to get it configured to use this final Action.

### :keyboard: Activity: Final workflow edit

1. [Edit]({{workflowFile}) your `my-workflow.yml` file.
2. Assign the `ha-ha` step an `id:` of **jokes**
3. Add a new step named `create-issue`.
4. The new step should have its `uses:` property point to `./.github/actions/issue-maker`
5. The `issue-maker` Action should consume the output of the `joke-action`. Add a `with:` property that takes a parameter of `joke:` with a value of `${{steps.jokes.outputs.joke-output}}`
6. Commit the changes to a new branch and name it `action-three`.
7. Create a pull request named **Use Outputs**

Like our other Actions, I'll respond in the new pull request when I detect it has been opened.

---

<details><summary>The complete workflow can be viewed by clicking here</summary>

```yaml
name: JS Actions

on:
  pull_request:
    types: [labeled]

jobs:
  action:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v1

      - name: hello-action
        uses: ./.github/actions/hello-world

      - name: ha-ha
        uses: ./.github/actions/joke-action
        id: jokes

      - name: create-issue
        uses: ./.github/actions/issue-maker
        with:
          joke: ${{steps.jokes.outputs.joke-output}}
```

</details>
