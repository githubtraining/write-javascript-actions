## Anatomy of an action

Earlier you learned how the different pieces of the GitHub Actions feature work together. Now you will learn about the components that make up an individual action.

Remember, an action is the unit of work that a workflow file executes when it reaches that task. They are called by referencing them as the value to the `uses:` key in a workflow step.

### What makes up an action?

JavaScript actions are consist of two key components:

| Component                    | Description                                                                                                                                                                                                                 |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JavaScript source code files | These files contain the logic of your action. This includes any dependencies or custom modules that your main logic may need.                                                                                               |
| Action metadata file         | This file contains information that the actions source code can use. An example of this is allowing a developer to specify an API key as an input variable for your action to consume. This file MUST be named `action.yml` |

### Let's take a look at how those components fit in with the workflow file.

<p align="center">
<img src="https://user-images.githubusercontent.com/38021615/72563499-ab4b2300-3862-11ea-98bf-97aa991d12a3.png" alt="Screenshot depicting the interaction between the JavaScript files, action metadata file and workflow file." />
</p>

_Although the **workflow** file is used to allow us to set the `inputs` and `outputs` using the `with:` keyword it is **not** a required component of an individual action._

### The failing workflow

Before we jump into the details of action metadata, it might be helpful to examine our workflow to understand the order that things happen. I have attached a screenshot below of the most recent workflow run, you can also follow along by clicking on the [Actions tab]({{actionsUrl}}) for your repository.

![This screenshot shows the results of a failing workflow run.  These result can be found by clicking the actions tab of this repository](https://i.imgur.com/FPOjK3R.png)

Notice that our third workflow step, the one that is looking for our action is failing. We expect this, but the magic ✨is in the error message!

That step is looking for a file named `action.yml`.

Because `action.yml` is non-existent in the `hello-world` directory we see this error. So let's start by talking about, and creating, the missing `action.yml` file.
