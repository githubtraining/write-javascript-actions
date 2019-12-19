## {{user.login}} you're doing great 👍

Just like the first Action we wrote, we are going to need to setup a few directories and files.

### :keyboard: Activity: Configure your second Action

Now that you have all the necessary tools installed locally, follow these steps to ensure your environment is configured and ready for Actions.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine and navigate to your course repo directory.
2. Checkout the `master` branch
   `git checkout master`
3. Update the contents of your Learning Lab repo to your local machine:
   `git pull`
4. Checkout the `action-two` branch you created for this pull request.
   `git checkout action-two`
5. Create a new folder for our Actions files:
   `mkdir -p .github/actions/joke-action`
6. Navigate to the `joke-action` folder you just created:
   `cd .github/actions/joke-action`
7. Initialize a new project:
   `npm init -y`
8. Install the **request** and **request-promise** dependencies using `npm`:
   `npm install --save request request-promise @actions/core`
9. Commit those newly added files,we will remove the need to upload **node_modules** in a later step:
   `git add .`
   `git commit -m 'initial joke action'`
10. Push you changes to your repository:
    `git push`

---

I will respond once you have finished.
