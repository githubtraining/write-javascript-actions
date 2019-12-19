# Great job!

You did it 🎉

You have successfully written three different JavaScript Actions.

Let's take a quick look at all the things you learned in this course:

**Workflows**
Along the way you learned a little about workflows and how to configure them. You managed to accomplish all these things:

- Define two different event triggers
- Filter an event trigger to run only when a label is added to a pull request
- You configured one unique job containing three unique steps within a workflow
- You learned how to overwrite default Action values by defining them in a workflow
- One of your steps consumed a secret
- One of your steps consumed the output of a previous step

That's quite a bit for a course that doesn't cover workflows!

**Action metadata**

- You became familiar with over 1/2 of the syntax keywords that can be used in an `action.yml` file
- Using `inputs:` and `outputs:` allowed you to create more dynamic and reusable metadata files for your Actions.
- You've mow written the metadata for three different Actions

**JavaScript Actions**
Wow, what a series of tasks! You started with the traditional `hello world` in the console, which was then expanded to use the `input:` parameters specified in the Actions metadata. Through the use of that metadata you were able to be flexible with your greeting.

You learned how GitHub Actions behave when consuming external APIs and you also used the response from an external API as an `output:` parameter for a later step in the workflow.

Lastly you saw how to use Actions to interact with a repository by creating an issue containing a joke.

You used multiple packages in your Action source code, you consumed `inputs:` and set `outputs:`.

You learned how to use the `@actions/core` package to write errors and terminate a misbehaving Action.

At this point you are armed with everything you need to know to go out there and begin creating your own custom JavaScript Actions.

### We aren't done yet 😉

Throughout this course I have promised to show you how to get rid of the `node_modules` folder in your repository.

I also want to take a few minutes to point you to the information you need to place your own custom Actions on the [GitHub Marketplace](https://github.com/marketplace?type=actions) for others to use.
