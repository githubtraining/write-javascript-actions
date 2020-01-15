## Configuring a workflow

Actions are enabled on your repository by default, but we still have to tell our repository to use them. We do this by creating a workflow file in our repository.

A **workflow** file can be thought of as the recipe for automating a task. They house the start to finish instructions, in the form of `jobs` and `steps`, for what should happen based on specific triggers.

These individual steps take one of two forms.

- Run a raw command such as `echo` or `npm install`
- Use an action such as the one we will be building

📖Read more about [workflows](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/configuring-a-workflow#choosing-the-type-of-actions-for-your-workflow)

### :keyboard: Activity: Create a pull request to prepare the repository for actions

1. Create a new workflow file titled `my-workflow.yml` by using the instructions below, or [this quicklink]({{quicklink}}).
   - Go to the [Actions tab]({{ actionsUrl }}).
   - Choose the **Set up a workflow yourself** option, located on the top right hand corner of the screen.
   - Change the name of the file from `main.yml` to `my-workflow.yml`
1. Commit the workflow to a new branch.
1. Create a pull request titled **Initial workflow**.

I'll respond in the new pull request when I detect it has been created.

---

If at any point you're expecting a response and don't see one, refresh the page.
