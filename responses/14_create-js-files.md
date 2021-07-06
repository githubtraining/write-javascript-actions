## Let's write some JavaScript

@{{user.login}} your **joke-action** stores a value in an `output:` parameter. We are going to use that value to create a new issue inside this repository!

Sometimes going from code-to-cloud requires more automation than CI/CD can provide. Actions can be used for this automation and hopefully after you learn how to interact with this repository through writing this action you'll go on to write many more amazing pieces of automation.

**Scenario**

You run an open source repository that is community driven. Every month you are getting tons of contributions from random developers within the community. Sometimes these contributions are amazing because the developers have read your contributing guidelines. Sometimes the opposite occurs. In both events you would like to thank your community for their contribution and ensure that every contributor is aware that you do in fact have guidelines for contributions. How would you do this?

You can imagine just how much time would be consumed if we sent a human... if we can call developers human in the first place 😉, to respond to all of our projects first time contributors with the same kind of message. Enter GitHub Actions! We can easily automate this process and many more using what you've learned up to this point.

Allow me to show you the final piece and get you started with interacting with your repository through an action.

### About the issue maker action

**Our action**
Unlike the joke action you wrote, this issue maker will have only one JavaScript file.

Let's take a look at what the source code for this action will look like and I'll explain what is happening before having your write it.

**Importing packages**

The first two lines will import packages from the [Actions ToolKit](https://github.com/actions/toolkit). You'll find yourself using these libraries a lot, so its good to get familiar with them.

```javascript
const core = require("@actions/core");
const github = require("@actions/github");
const { Octokit} = require('@octokit/rest')
```

**Creating the main function**
Next we declare an asynchronous function since we are going to be using the HTTP protocol with octokit later.  
Wrapping our code in a try/catch block is good practice for error handling, so we will go ahead and do that here. Once that is complete we define a few variables.

```javascript
async function run() {
  try {
  } catch (err) {}
}

run();
```

**Getting input for the issue title**
Every issue on GitHub needs a title. If you recall we had the `issue-title` property set in our `action.yml` file for this action, so let's read that in from the workflow file. We do that by calling `core.getInput("name of the input")`. In our case the input is named `issue-title` so we will use that.

Wait a minute... I know what you're thinking. I said read this property from the workflow file, but we never actually defined it in the workflow. You're right, but why does this work? Do you remember what happens when we give a property a default value and enforce that it is required?

Since the default value can be overwritten we will include it in our code just in case you decide to provide a different title for your joke issues.

```javascript
async function run() {
  try {
    const issueTitle = core.getInput("issue-title");
  } catch (err) {}
}

run();
```

**Using the other inputs from the metadata**
Okay, what about the other variables we set up:

- `jokeBody`
- `token`
- `octokit`

The `jokeBody` uses the `core.getInput()` method but this time that input is going to be defined by the previous action. If you recall, in the workflow we specified `joke: {% raw %}${{steps.jokes.outputs.joke-output}}{% endraw %}` to be used `with:` this action. This is one way we can pass the output of one action to the another one in the workflow.

We also need to define a `token`. This token allows us to interact with the GitHub API, which we will do using [octokit/rest.js](https://octokit.github.io/rest.js/).

Where does the `token` come from?

We specified a `repo-token:` parameter for use `with:` this action and gave it a value of `{% raw %}${{secrets.GITHUB_TOKEN}}{% endraw %}`. I didn't tell you where we got the `GITHUB_TOKEN` from so let me do that now.

GitHub sets default environment variables that are available to every step in a workflow run. You also have access to any [secrets](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets#creating-encrypted-secrets) you have setup in your repository, to include this action specific `GITHUB_TOKEN` that is automatically set for you.

You can [read more](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/authenticating-with-the-github_token) about using the `GITHUB_TOKEN` for authentication purposes.

Its also worth taking a look at the different [Contexts and expressions](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/contexts-and-expression-syntax-for-github-actions) that you can use with GitHub Actions.

**Adding the octokit client**
Long story short, we use the default `GITHUB_TOKEN` for authentication with the Octokit client.

```javascript
async function run() {
  try {
    const issueTitle = core.getInput("issue-title");
    const jokeBody = core.getInput("joke");
    const token = core.getInput("repo-token");

    const octokit = new Octokit({
        auth: token,
        userAgent: 'action-three',
    });
  } catch (err) {}
}

run();
```

**Creating an issue in the repository**
Next we use that octokit client to create an issue in your repository, which will make the HTTP request to the GitHub API for us. [Look here](https://octokit.github.io/rest.js/#octokit-routes-issues-create) to learn more about `octokit.issues.create()`.

```javascript
async function run() {
  try {
    const issueTitle = core.getInput("issue-title");
    const jokeBody = core.getInput("joke");
    const token = core.getInput("repo-token");

    const octokit = new Octokit({
        auth: token,
        userAgent: 'action-three',
    });

    const newIssue = await octokit.issues.create({
        repo: github.context.repo.repo,
        owner: github.context.repo.owner,
        title: issueTitle,
        body; jokeBody
    });
  } catch (err) {}
}

run()
```

💡Octokit makes interacting with the GitHub API easy, but if you are writing actions using a different language, or you prefer to not use a library, the same issue can be created with [this API endpoint](https://developer.github.com/v3/issues/#create-an-issue)

**Let's handle any errors**
Lastly, we write the `catch` portion of our try/catch block and you use `core.setFailed()` method to force our action to fail if something goes wrong, but also produce an error message in the workflow logs.

```javascript
async function run() {
  try {
    const issueTitle = core.getInput("issue-title");
    const jokeBody = core.getInput("joke");
    const token = core.getInput("repo-token");

    const octokit = new Octokit({
        auth: token,
        userAgent: 'action-three',
    });

    const newIssue = await octokit.issues.create({
        repo: github.context.repo.repo,
        owner: github.context.repo.owner,
        title: issueTitle,
        body; jokeBody
    });
  } catch (err) {
      core.setFailed(err.message);
  }
}

run()
```

_Don't forget to call the function, `run()`, on the last line so that your action executes!_
