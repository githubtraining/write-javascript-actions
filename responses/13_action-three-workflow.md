## Action three

Two actions down, one more to go! Before we move on with building our final action let's take a second to do a quick recap since this lesson has thrown a lot of information at you.

**The workflow**
We started out by explaining what a workflow is and how it pertains to the GitHub Actions platform. You learned about how a defined event sets your workflow orchestra in motion.

You learned about runners, jobs, steps and have dabbled in the syntax of a workflow file at every step in this course. I don't want to spoil too much here, but you'll be doing it again in this one as well 😉.

**Action metadata**
You learned that every action is accompanied by an `action.yml` file which contains a series of metadata for how the action behaves. This file defines all of an actions inputs, outputs, runtime environment, name, description and even branding.

**Hello action**
Your first JavaScript action took the traditional path of a "Hello World" introduction. You ended up expanding that action to accept `inputs` to help make it a little more dynamic. Ultimately, the key takeaway was to understand that you can pass input that is defined in the workflow to an action as long as the action's metadata supports it.

When consuming or creating actions it is incredibly helpful to take care to understand that actions metadata file.

**Joke action**
You second JavaScript action demonstrated that your workflow environment is capable of communicating outside of it's own network. We reached out to an external API and used that information to set `outputs` for another action to consume. As with `inputs` your actions metadata must support the ability to set `outputs` if you want to use this option.

**What next?**
Your third, and final, JavaScript action of this course is going to use yet another library from the [Actions ToolKit](https://github.com/actions/toolkit). It is also going to consume the `outputs` of your joke action and use them to help create issues in your repository.

We need to make some edits to the `my-workflow.yml` file to get it configured to use this final action.

### :keyboard: Activity: Final workflow edit

1. [Edit]({{workflowFile}}) your `my-workflow.yml` file to contain the following:
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
              repo-token: {% raw %}${{secrets.GITHUB_TOKEN}}{% endraw %}
              joke: {% raw %}${{steps.jokes.outputs.joke-output}}{% endraw %}
    ```
2. Commit the changes to a new branch, you can name it `action-three`.
3. Create a pull request named **Use outputs**



---

Like our other actions, I'll respond in the new pull request when I detect it has been opened.
