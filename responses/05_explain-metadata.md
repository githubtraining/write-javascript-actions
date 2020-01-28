## Action metadata

Every GitHub Action that we write needs to be accompanied by a metadata file. This file has a few rules to it, lets outline those now:

- Filename **must** be `action.yml`
- Required for both Docker container and JavaScript actions
- Written in YAML syntax

This file defines the following information about your action:

| Parameter   | Description                                                                                                                                            |      Required      |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :----------------: |
| Name        | The name of your action. Helps visually identify the actions in a job.                                                                                 | :white_check_mark: |
| Description | A summary of what your action does.                                                                                                                    | :white_check_mark: |
| Inputs      | Input parameters allow you to specify data that the action expects to use during runtime. These parameters become environment variables in the runner. |         ❌         |
| Outputs     | Specifies the data that subsequent actions can use later in the workflow after the action that defines these outputs has run.                          |         ❌         |
| Runs        | The command to run when the action executes.                                                                                                           | :white_check_mark: |
| Branding    | You can use a color and Feather icon to create a badge to personalize and distinguish your action in GitHub Marketplace.                               |         ❌         |

---

📖Read more about [Action metadata](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions)
