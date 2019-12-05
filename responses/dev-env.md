## On to your development environment

@{{user.login}} our JavaScript Actions are going to leverage the [GitHub ToolKit](https://github.com/actions/toolkit) for developing GitHub Actions.

This is an external library that we will install using `npm` which means that you will need [Node.js](https://nodejs.org/) installed.

I find writing Actions to be easier from a local environment vs trying to do everything right here in the repository.  Doing these steps locally allows you to use the editor of your choice so that you have all the extensions and snippets you are used to when writing code.

If you do not have a preferred environment then I suggest following along with me exactly as you see on the screen, which means you'll need to install [Visual Studio Code](https://code.visualstudio.com/).

## Don't forget to set up your workstation 😉

Most of your work going forward will take place away from your Learning Lab repository, so before continuing with the course ensure you have the following installed on your **local machine**.  

1. [ ] [Node.js](https://nodejs.org)
2. [ ] [Visual Studio Code](https://code.visualstudio.com/) or your editor of choice
3. [ ] [Git](https://git-scm.com/)


### :keyboard: Activity: Configure your environment

Now that you have all the necessary tools installed locally, follow these steps to ensure your environment is configured and ready for Actions.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine
2. Clone your Learning Lab repo to your local machine:
   `git clone {{repoUrl}}.git`
   <details><summary>View GIF</summary><img src="https://media.giphy.com/media/YnvmISGo2MbXpn2bc5/giphy.gif" alt="git clone example" /></details>
    <!-- ![alt text](https://media.giphy.com/media/YnvmISGo2MbXpn2bc5/giphy.gif) -->

3. Navigate to the folder you just cloned:
   `cd writing-javascript-actions`
      <details><summary>View GIF</summary><img src="https://media.giphy.com/media/duA6JVCuXbt5gKqNLw/giphy.gif" alt="directory navigation" /></details>
    <!-- ![alt text](https://media.giphy.com/media/duA6JVCuXbt5gKqNLw/giphy.gif) -->
4. Create a new branch named `hello-world`.  This is the branch we will use to write our first Action.  **Please do not capitalize letters unless I do, I run case-sensitive checks to make sure I can help you along the way!**
   `git checkout -b hello-world`
    <details><summary>View GIF</summary><img src="https://media.giphy.com/media/hvdeWGkjoy4UdfwbfQ/giphy.gif" alt="git checkout example" /></details>
   
5. Create a new folder for our Actions files:
   `mkdir -p .github/actions/hello-world`
    <details><summary>View GIF</summary><img src="https://media.giphy.com/media/Wn03sc0QsywHHD1LeN/giphy.gif" alt="create folder for action example" /></details>
6. Navigate to the `hello-world` folder you just created:
   `cd .github/actions/hello-world`
    <details><summary>View GIF</summary><img src="https://media.giphy.com/media/ckCMgczjpbjNwkfJq4/giphy.gif" alt="navigate to folder for action example" /></details>
   
7. Initialize a new project:
   `npm init -y`
    <details><summary>View GIF</summary><img src="https://media.giphy.com/media/mEW0fJYx4oUjdgYHDV/giphy.gif" alt="navigate to folder for action example" /></details>

8. Install the **core** and **github** dependencies from the [GitHub ToolKit](https://github.com/actions/toolkit):
   `npm install --save @actions/core @actions/github`
   <details><summary>View GIF</summary><img src="https://media.giphy.com/media/H3kGNqDI24lNOEKk5k/giphy.gif" alt="navigate to folder for action example" /></details>
9.  Commit those newly added files,we will remove the need to upload **node_modules** in a later step:
    `git add .`
    `git commit -m 'initial hello-world'`
10. Push you changes to your repository:
    `git push -u origin hello-world`


---

I will respond once you have finished.


