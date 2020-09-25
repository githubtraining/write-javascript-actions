## Your turn!

### :keyboard: Activity: Add input parameters

That was a lot of information that you just learned. @{{user.login}} it is time for you to put it in practice.

1. Using your code editor change these files to reflect the code in the examples shown above:

     <details><summary><code>.github/actions/hello-world/main.js</code></summary>

   ```javascript
   const core = require("@actions/core");

   const firstGreeting = core.getInput("first-greeting");
   const secondGreeting = core.getInput("second-greeting");
   const thirdGreeting = core.getInput("third-greeting");

   console.log(`Hello ${firstGreeting}`);
   console.log(`Hello ${secondGreeting}`);
   if (thirdGreeting) {
     console.log(`Hello ${thirdGreeting}`);
   }
   ```

     </details>

     <details><summary><code>.github/actions/hello-world/action.yml</code></summary>

   ```yaml
   name: "my hello action"

   description: "say hello with actions"

   inputs:
     first-greeting:
       description: "who would you like to greet in the console"
       required: true
       default: "Hubot"

     second-greeting:
       description: "another person to greet"
       required: true
       default: "Mona the Octocat"

     third-greeting:
       description: "a third greeting"
       required: false

   runs:
     using: "node12"
     main: "main.js"
   ```

     </details>


      <details><summary><code>.github/workflows/my-workflow.yml</code></summary>

      ```yaml

      name: "JS Actions"

      on: [push]

      jobs:
        action:
          runs-on: "ubuntu-latest"
          steps:
            - uses: actions/checkout@v1

            - name: "hello-action"
              uses: ./.github/actions/hello-world
              with:
                first-greeting: "Learning Lab User"
      ```
      </details>

2. Save the changes to each file
3. Commit the changes to this branch and push them to GitHub:

   ```shell
   git add main.js action.yml my-workflow.yml
   git commit -m 'allow input in all action files'
   git push
   ```

---

I'll respond here when GitHub Actions reports it's finished.

<details><summary>Is your workflow failing?</summary>

If you workflow is failing, please double check your:
- JavaScript source code
- action metadata
- workflow file

Look for linter errors or any errors reported on the Actions tab. I will respond when I receive another workflow run is completed.
</details>
