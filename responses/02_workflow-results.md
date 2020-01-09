## Our workflow has finished 🎉

Our workflow has finished so let's take a look at the results now that we have learned a little bit about workflows while we waited.

![Workflow results screen showing status of each job](https://i.imgur.com/6EL8i5o.png)

In the left-hand panel of this screen you can see that this workflow, named `CI` was triggered `on: push` and ran the job titled `build`.

The right-hand panel shows real-time logging of the steps executed by the `build` job.  There are currently 5 steps defined for this job:

- Set up job
- Run actions/checkout@v1
- Run a one-line script
- Run a multi-line script
- Complete job

🤔This is interesting, in the `my-workflow.yml` file we defined 3 steps, not 5, so what happened?

GitHub Actions will **always** add the `Set up job` and `Complete job` steps to each job in a workflow.  These steps are what configure the [virtual environment](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/virtual-environments-for-github-hosted-runners) before running your steps and shut it down properly before moving onto the next job in your workflow.

If you recall, we had 1 step that used an action and 2 steps that ran commands, can you identify which step used the action?

If you said `actions/checkout@v1` you'd be correct 😄!

---


If you want to see this for yourself head over to your [Actions tab]({{actinosUrl}}) and examine the workflow named `CI`