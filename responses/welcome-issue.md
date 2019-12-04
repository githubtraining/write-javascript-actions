# Hi there 👋!

Hello @{{user.login}}, I'm so excited to teach you how to create your own Actions 😄

### Prerequisites

We will be using `Node.js` to build our Action and GitHub to consume our Action.  This presents us with a hybrid environment that you may not be used to if you've taken other Learning Lab courses.

Before we can get started there are a few things you need to setup on your **Local Machine**

1. Install [Node.js](https://nodejs.org/en/) for your operating system.
2. Ensure you have a text editor installed.  I'll be using **Visual Studio Code**, and although you are free to use your editor of choice you should be aware that using a different editor will result in your screen not matching my examples.  Here are some editor options for you:
   1. [Visual Studio Code](https://code.visualstudio.com/) **(recommended)**
   2. [Atom](https://atom.io/)
   3. [Sublime Text](https://www.sublimetext.com/)
3. Lastly, you're going to need a local installation of [Git](https://git-scm.com/) so that you can interact with this repository as you write code.

### Getting started

In this repository we will be diving into the world of GitHub Actions writing!  I will guide you through the process of writing a custom GitHub Action using the **JavaScript** programming language.

You may be asking yourself, "what are Actions and is **JavaScript** the only language used to create GitHub Actions?"

Currently, there are **two** supported ways to create your own GitHub Actions:

- [Docker Container Actions](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/about-actions#docker-container-actions) 
- [JavaScript Actions](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/about-actions#javascript-actions) 

As you can see we aren't necessarily limited to **JavaScript** even though it is the focal point for this course.


### Creating vs Consuming Actions

Although we are going to focus on creating and consuming a custom Action, in this course we will also be consuming some Actions that have been made public to us.  Because your workflows will most likely do the same, I found it important to show you where to look for Actions that already exist.

After all, for each time we need to reinvent the wheel for our specific use-case there are a handful of times when we are better off using a wheel that's already made!

- The [GitHub Actions Marketplace](https://github.com/marketplace?type=actions) is the primary place to find open-source Actions that the community has written and released.  Your Action, should you choose to release it, could also reside here one day, ready to be consumed by the world!
- The [GitHub Actions Repository](https://github.com/actions) is where you can find Actions that are written by GitHub.  We will leverage an Action named "[checkout](https://github.com/actions/checkout)" from this repository as we go through this course.  I'll explain more about what it does when we use it!
- Your repositories may also contain **private Actions** and they will most likely be located in the `.github/actions` directory in the root of your repository.  **This is the convention we will be using as we learn how to create our own Action.**

### Using Actions and Learning Lab

In other courses, you may have noticed that some behaviors take me longer to respond to than others. In this course, many of the behaviors will be related to our Actions workflow. Those workflows sometimes take longer to complete, up to several minutes. Don't be concerned if I take a few minutes to respond, or if I respond too quickly. Sometimes, I'll let you know what the workflow will say before it finishes! Please wait for the workflows to finish before moving on to your next step.

If you aren't already familiar, it may be a good idea to go through the [Introduction to GitHub Learning Lab](https://lab.github.com/githubtraining/introduction-to-github).

## Step 1: Preparing your repository

Actions are enabled on your repository by default, but we still have to tell our repository to use them.  We do this by creating a **workflow** file in our repository.

A **workflow** file can be thought of as the recipe for automating a task.  They house the start to finish instructions, in the form of `jobs` and `steps`, for what should happen based on specific triggers.

These individual steps take one of two forms.  
- Run a raw command such as `echo` or `npm install`
- Use an Action such as the one we will be building

📖Read more about [workflows](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/configuring-a-workflow#choosing-the-type-of-actions-for-your-workflow)

### :keyboard: Activity: Create a pull request to prepare the repository

1. Go to the [Actions tab]({{ actionsUrl }}).
2. Choose the **Set up a workflow yourself** option, located on the top right hand corner of the screen.
3. Change the name of the file from `main.yml` to `my-workflow.yml`
4. Commit the workflow to a new branch.
5. Create a pull request titled **Initial Workflow**.

I'll respond in the new pull request when I detect it has been created.

---

If at any point you're expecting a response and don't see one, refresh the page.

`git clone https://{% raw %}{{repUrl}}{% endraw %}.git`

`{{repUrl}}`

{{repoUrl}}


