## Action metadata

Every GitHub Action that we write needs to be accompanied by a metadata file.  This file has a few rules to it, lets outline those now:

- Filename **must** be `action.yml`
- Placed in the root directory of your Action
- Required for both Docker container and JavaScript Actions
- Written in YAML syntax

This file defines the following information about your Action:

<details><summary>Name</summary>This parameter is <b>required</b>. The name of your action. Helps visually identify the Actions in a job.</details>
<details><summary>Author</summary>This parameter is <b>optional</b>. The name of who wrote the Action.</details>
<details><summary>Description</summary>This parameter is <b>required</b>. A summary of what your Action does.</details>
<details><summary>Inputs</summary>This parameter is <b>optional</b>. Input parameters allow you to specify data that the action expects to use during runtime. These parameters become environment variables in the runner.</details>
<details><summary>Outputs</summary>This parameter is <b>optional</b>.  Specifies the data that subsequent actions can use later in the workflow after the action that defines these outputs has run.</details>
<details><summary>Runs</summary>This parameter is <b>required</b>.  The command to run when the Action executes.</details>
<details><summary>Branding</summary>This parameter is <b>optional</b>.  You can use a color and Feather icon to create a badge to personalize and distinguish your action in GitHub Marketplace.</details>

---

📖Read more about [Action metadata](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions)