## {{user.login}} you're doing great 👍

Just like the first action you wrote, you are going to need to setup a few directories and files.

### :keyboard: Activity: Configure your second action

Now that you have all the necessary tools installed locally, follow these steps to ensure your environment is configured and ready for actions.

1. Open the **Terminal** (Mac and Linux) or **Command Prompt** (Windows) on your local machine
1. Navigate to the `.github/` directory.
1. Checkout the `master` branch
   ```shell
   git checkout master
   ```
1. Update the contents of your Learning Lab repo to your local machine:
   ```shell
   git pull
   ```
1. Checkout the `action-two` branch you created for this pull request.
   ```shell
   git checkout action-two
   ```
1. Create a new folder for our actions files:
   ```shell
   mkdir actions/joke-action
   ```
   **The full path should be `.github/actions/joke-action`**
1. Navigate to the `joke-action` folder you just created:
   ```shell
   cd actions/joke-action
   ```
   **This may be different depending on your current directory**
1. Initialize a new project:
   ```shell
   npm init -y
   ```
1. Install the **request**, **request-promise** and **@actions/core** dependencies using `npm`:
   ```shell
   npm install --save request request-promise @actions/core
   ```
1. Commit those newly added files. We will remove the need to upload **node_modules** in a later step:
   ```shell
   git add .
   git commit -m 'add joke action dependencies'
   ```
1. Push you changes to your repository:
   ```shell
   git push
   ```

---

I will respond once you have finished.
