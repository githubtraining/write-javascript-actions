## Anatomy of GitHub Actions

GitHub Actions is a unique world that lives alongside your repository.  It is one made up of many moving parts and having a general understanding of these parts will help us understand the behavior we are going to program into our Action.

From 30,000 feet GitHub Actions is made up of the following components, with each component having its own complexities:

Each component can be expanded for more information.

<details><summary>Action</summary>
Individual tasks that you combine as <b>steps</b> to create a <b>job</b>. <b>Actions</b> are the smallest portable building block of a workflow.  To use an <b>action</b> in a workflow, you <b>must include it as a step.</b></details>
<details><summary>Artifact</summary>
<b>Artifacts</b> are the files created when you build and test your code. <b>Artifacts</b> might include binary or package files, test results, screenshots, or log files.  <b>Artifacts</b> can be used by the other <b>jobs</b> in the workflow or deployed directly by the <b>workflow</b>.</details>
<details><summary>Event</summary>
A specific activity that triggers a <b>workflow</b> run.</details>
<details><summary>Job</summary>
A defined task made up of <b>steps</b>. Each <b>job</b> is run in a fresh instance of the <b>virtual environment</b>. <b>Jobs</b> can run at the same time in parallel or be dependent on the status of a previous <b>job</b> and run sequentially.</details>
<details><summary>Runner</summary>
Any machine with the GitHub Actions <b>runner</b> application installed. You can use a <b>runner</b> hosted by GitHub or host your own <b>runner</b>. A <b>runner</b> waits for available <b>jobs</b>. <b>Runners</b> run one <b>job</b> at a time reporting the progress, logs, and final result back to GitHub.</details>
<details><summary>Step</summary>
A <b>step</b> is a set of tasks performed by a <b>job</b>.  <b>Steps</b> can run <b>commands</b> or <b>actions</b>.
</details>
<details><summary>Virtual Environment</summary>
The <b>virtual environment</b> of a GitHub-hosted <b>runner</b> includes the virtual machine's hardware configuration, operating system, and installed software.
</details>
<details><summary>Workflow</summary>
A configurable automated process that you can set up in your repository.  <b>Workflows</b> are made up of one or more <b>jobs</b> and can be scheduled or activated by an <b>event</b>.</details>

### How these pieces fit together

![Actions workflow diagram](https://i.imgur.com/CwxGobh.png)

When a repository is configured with a **workflow** file, like we just created, the following series of events occurs.

1.  Your GitHub repository listens for an event
2.  That event triggers a workflow run which starts a runner
3.  The runner, regardless of the hosting method, is responsible for carrying out the jobs which are defined.
4.  A job is series of steps, which can be Actions or commands
5.  When the steps complete a report is generated and can be viewed by anyone with access to the repository.







