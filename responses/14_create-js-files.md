## Let's write some JavaScript

@{{user.login}} your **joke-action** stores a value in an `output:` parameter. We are going to use that value to create a new issue inside this repository!

Sometimes going from code-to-cloud requires more automation than CI/CD can provide. Actions can be used for this automation and hopefully after you learn how to interact with this repository through writing this Action you'll go on to write many more amazing pieces of automation.

**Scenario**

You run an open source repository that is community driven. Every month you are getting tons of contributions from random developers within the community. Sometimes these contributions are amazing because the developers have read your contributing guidelines. Sometimes the opposite occurs. In both events you would like to thank your community for their contribution and ensure that every contributor is aware that you do in fact have guidelines for contributions. How would you do this?

You can imagine just how much time would be consumed if we sent a human... if we can call developers human in the first place 😉, to respond to all of our projects first time contributors with the same kind of message. Enter GitHub Actions! We can easily automate this process and many more using what you've learned up to this point.

Allow me to show you the final piece and get you started with interacting with your repository through an Action.

**Our Action**
Unlike the previous Action you wrote, this one will have only one file.

Let's take a look at what the source code for this Action will look like and I'll explain what is happening before having your write it.

**index.js**

The first two lines will import packages from the [Actions ToolKit](https://github.com/actions/toolkit). You'll find yourself using these libraries a lot, so its good to get familiar with them.

![Lines 1-3 of index.js](https://i.imgur.com/sYwXYWL.png)

Next we declare an asynchronous function since we are going to be using the HTTP protocol later.  
Wrapping our code in a try/catch block is good practice, so we will go ahead and do that here. Once that is complete we define a few variables.

First, every issue on GitHub needs a title, and if you recall we had the `issue-title` property set in our `action.yml` file for this Action. So let's read that in from the workflow file. We do that by calling `core.getInput("name of the input")`. In our case the input is named `issue-title` so we will use that.

Wait a minute... I know what you're thinking. I said read this property from the workflow file, but we never actually defined it in the workflow. You're right, but why does this work? Do you remember what happens when we give a property a default value and enforce that it is required?

Since the default value can be overwritten we will include it in our code just in case you decide to provide a different title for your joke issues.

![Lines 4-10 of index.js](https://i.imgur.com/Sp5L5sz.png)

Okay, what about the other variables we set up:

- `jokeBody`
- `token`
- `octokit`

The `jokeBody` uses the `core.getInput()` method but this time that input is going to be defined by the previous action. If you recall, in the workflow we specified `joke: ${{steps.jokes.outputs.joke-output}}` to be used `with:` this Action. This is one way we can pass the output of one Action to the another one in the workflow.

We also need to define a `token`. This token allows us to interact with the GitHub API, which we will do using [octokit/rest.js](https://octokit.github.io/rest.js/).

Where does the `token` come from?

We specified a `repo-token:` parameter for use `with:` this Action and gave it a value of `${{secrets.GITHUB_TOKEN}}`. I didn't tell you where we got the `GITHUB_TOKEN` from so let me do that now.

GitHub sets default environment variables that are available to every step in a workflow run. You also have access to any [secrets](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets#creating-encrypted-secrets) you have setup in your repository, to include this Action specific `GITHUB_TOKEN` that is automatically set for you.

You can [read more](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/authenticating-with-the-github_token) about using the `GITHUB_TOKEN` for authentication purposes.

Its also worth taking a look at the different [Contexts and expressions](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/contexts-and-expression-syntax-for-github-actions) that you can use with GitHub Actions.

Long story short, on lines 8-10 we use the default `GITHUB_TOKEN` for authentication with the Octokit client.

Next we use that octokit client to create and issue in your repository. [Look here](https://octokit.github.io/rest.js/#octokit-routes-issues-create) to learn more about `octokit.issues.create()`.

![Lines 12-18 of index.js](https://i.imgur.com/ZJg89W5.png)

💡Octokit makes interacting with the GitHub API easy, but if you are writing Actions using a different language, or you prefer to not use a library, the same issue can be created with [this API endpoint](https://developer.github.com/v3/issues/#create-an-issue)

Lastly, we write the `catch` portion of our try/catch block and you use `core.setFailed()` method to force our Action to fail if something goes wrong, but also produce an error message in the workflow logs.

![Lines 19-24 of index.js](https://i.imgur.com/XvHDrI2.png)

Don't forget to call the function, `run()`, on the last line so that your Action executes!

<details><summary>View the complete index.js file</summary><img src="https://i.imgur.com/U0V0LK3.png" alt="complete index.js file" />
</details>
