## Action metadata

#### The failing workflow
Before we jump into the details of action metadata, it might be helpful to examine our workflow to understand the order that things happen.  I have attached a screenshot below of the most recent workflow run, you can also follow along by clicking on the [Actions tab]({{actionsUrl}}) for your repository.

![](https://i.imgur.com/FPOjK3R.png)

Notice that our third workflow step, the one that is looking for our action is failing.  We expect this, but the magic ✨is in the error message!  

That step is looking for a specific file, and in our case it's looking for the `action.yml` file.  It's not looking for a JavaScript file or a `config.yml` file.

Because that file is non-existent in the `hello-world` directory we see this error.  So let's start by talking about, and creating, that `action.yml` file.

#### The need to know of action metadata


Every GitHub Action that we write needs to be accompanied by a metadata file.  This file has a few rules to it, lets outline those now:

- Filename **must** be `action.yml`
- Required for both Docker container and JavaScript actions
- Written in YAML syntax

This file defines the following information about your action:



| Parameter   | Description                                                                                                                                            |      Required      |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :----------------: |
| Name        | The name of your action. Helps visually identify the actions in a job.                                                                                 | :white_check_mark: |
| Description | A summary of what your action does.                                                                                                                    | :white_check_mark: |
| Inputs      | Input parameters allow you to specify data that the action expects to use during runtime. These parameters become environment variables in the runner. |         ❌          |
| Outputs     | Specifies the data that subsequent actions can use later in the workflow after the action that defines these outputs has run.                          |         ❌          |
| Runs        | The command to run when the action executes.                                                                                                           | :white_check_mark: |
| Branding    | You can use a color and Feather icon to create a badge to personalize and distinguish your action in GitHub Marketplace.                               |         ❌          |

---

📖Read more about [Action metadata](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions)