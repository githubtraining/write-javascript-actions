## While we wait!

Great job adding the workflow. Adding that file to this branch is enough for GitHub Actions to begin running on your repository. The time this takes will vary based on the complexity of the workflow. While this runs I'll briefly explain the components of the workflow you just added.

---

<details><summary>Actions workflow not running? Click here</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below.

![Checks in progress box](https://i.imgur.com/uO6iqYd.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
  </details>
