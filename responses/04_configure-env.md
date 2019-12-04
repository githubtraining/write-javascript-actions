
### :keyboard: Activity: Configure your environment

Now that you have all the necessary tools installed locally, follow these steps to ensure your environment is configured and ready for Actions.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine
2. Clone your Learning Lab repo to your local machine
   `git clone https://{% raw %}{{repUrl}}{% endraw %}.git`

3. Create a new branch named `hello-world`
4. Clone this repository to your local machine using `git clone`
5. Use `git checkout hello-wolrd` to change to the newly created branch
6. Initialize the a new project with `npm init -y`
7. Install the **core** and **github** dependencies from the [GitHub ToolKit](https://github.com/actions/toolkit) by typing `npm install --save @actions/core @actions/github`
8. Commit those newly added files, including `node_modules`, we will remove the need to upload `node_modules` in a later step
9.  Push you changes to your repository
10. Create a new pull request from the `hello-world` branch to `master` with the title of `Hello Actions`
    - Take notice that the pull request name `Hello Actions` is case-sensitive

I will close this issue and continue responding to you in the `hello-actions` pull request once you have created it.