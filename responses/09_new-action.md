### :keyboard: Activity: Setting up the next Action

Before we continue we are going to need to do a few things. First and foremost our workflow is currently setup to run each time there is a `push` event to this repository. Let's comment out our current workflow to prevent things from running but preserve the things you've worked on up to this point.

You will still see the workflow trying to execute with every push if you look at the [Actions tab]({{actionsUrl}}), however it will seem as though it fails. This is because there is a workflow file in the `.github/workflows` directory. The failure isn't actually a failure either, if you expand it you will see that there is simple no triggers for that given workflow and therefore it doesn't run. I have placed a screenshot below so you can become familiar with what this error looks like without the need to go to your [Actions tab]({{actionsUrl}}).

![No trigger screenshot](https://i.imgur.com/rARtXc1.png)

<!-- add action.yml -->
<!-- open pull request -->
