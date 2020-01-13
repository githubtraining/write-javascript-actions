## {{user.login}} it's time to get ready for the third action 🎉

As with the other actions we wrote, we are going to need to setup a few directories and files.

### :keyboard: Activity: Configure your third action

Let's create our final project directory and install all the necessary dependencies. We will take this a step further near the end of this action and we will show you how to avoid needing to check in `node_modules`.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine and navigate to your course repo directory.
2. Checkout the `master` branch
   `git checkout master`
3. Update the contents of your Learning Lab repo to your local machine:
   `git pull`
4. Checkout the `action-three` branch you created for this pull request.
   `git checkout action-three`
5. Create a new folder for our actions files:
   `mkdir -p .github/actions/issue-maker`
6. Navigate to the `issue-maker` folder you just created:
   `cd .github/actions/issue-maker`
7. Initialize a new project:
   `npm init -y`
8. Install the **request** and **request-promise** dependencies using `npm`:
   `npm install --save @actions/core @actions/github`
9. Commit those newly added files,we will remove the need to upload **node_modules** in a later step:
   `git add .`
   `git commit -m 'initial issue maker action'`
10. Push you changes to your repository:
    `git push`

---

I will respond once you have finished.
