## {{user.login}} it's time to get ready for the third action 🎉

As with the other actions we wrote, we are going to need to setup a few directories and files.

### :keyboard: Activity: Configure your third action

Let's create our final project directory and install all the necessary dependencies. We will take this a step further near the end of this action and we will show you how to avoid needing to check in `node_modules`.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine
1. navigate to the `.github/actions` directory.
1. Checkout the `master` branch
   `git checkout master`
1. Update the contents of your Learning Lab repo to your local machine:
   `git pull`
1. Checkout the `action-three` branch you created for this pull request.
   `git checkout action-three`
1. Create a new folder for our actions files:
   `mkdir issue-maker`
   **The full path should be `.github/actions/issue-maker`**
1. Navigate to the `issue-maker` folder you just created:
   `cd issue-maker`
   **The full path should be `.github/actions/issue-maker`**
1. Initialize a new project:
   `npm init -y`
1. Install the **@actions/core** and **@actions/github** dependencies using `npm`:
   `npm install --save @actions/core @actions/github`
1. Commit those newly added files,we will remove the need to upload **node_modules** in a later step:
   `git add .`
   `git commit -m 'add issue maker dependencies'`
1. Push you changes to your repository:
   `git push`

---

I will respond once you have finished.
