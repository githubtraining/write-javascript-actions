
### :keyboard: Activity: Configure your environment

Now that you have all the necessary tools installed locally, follow these steps to ensure your environment is configured and ready for Actions.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine
2. Clone your Learning Lab repo to your local machine:
   `git clone https://{{repoUrl}}.git`
   <details><summary>View GIF</summary><img src="https://media.giphy.com/media/YnvmISGo2MbXpn2bc5/giphy.gif" alt="git clone example" /></details>
    <!-- ![alt text](https://media.giphy.com/media/YnvmISGo2MbXpn2bc5/giphy.gif) -->

3. Navigate to the folder you just cloned:
   `cd writing-javacript-actions`
      <details><summary>View GIF</summary><img src="https://media.giphy.com/media/duA6JVCuXbt5gKqNLw/giphy.gif" alt="directory navigation" /></details>
    <!-- ![alt text](https://media.giphy.com/media/duA6JVCuXbt5gKqNLw/giphy.gif) -->
4. Create a new branch named `hello-world`.  This is the branch we will use to write our first Action.  **Please do not capitalize letters unless I do, I run case-sensitive checks to make sure I can help you along the way!**
   `git checkout -b hello-world`
    <details><summary>View GIF</summary><img src="https://media.giphy.com/media/hvdeWGkjoy4UdfwbfQ/giphy.gif" alt="git checkout example" /></details>
   
5. Create a new folder for our Actions files:
   `mkdir -p .github/actions/hello-world`
6. Navigate to the `hello-world` folder you just created:
   `cd .github/actions/hello-world`
7. Initialize the a new project with `npm init -y`
8. Install the **core** and **github** dependencies from the [GitHub ToolKit](https://github.com/actions/toolkit) by typing `npm install --save @actions/core @actions/github`
9.  Commit those newly added files, including `node_modules`, we will remove the need to upload `node_modules` in a later step
10. Push you changes to your repository
11. Create a new pull request from the `hello-world` branch to `master` with the title of `Hello Actions`
    - Take notice that the pull request name `Hello Actions` is case-sensitive

I will close this issue and continue responding to you in the `hello-actions` pull request once you have created it.