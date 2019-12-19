## Your turn!

### :keyboard: Activity: Add input parameters

That was a lot of information that you just learned. @{{user.login}} it is time for you to put it in practice.

1. Using your code editor change these files to reflect the code in the examples shown above:

   <details><summary>main.js</summary>

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

   <details><summary>Action.yml</summary>

   ```yaml
   name: "my hello action"

   description: "say hello with Actions"

   inputs:
     first-greeting:
       description: who you would like to greet in the console
       required: true
       default: Hubot

     second-greeting:
       description: who to greet
       required: true
       default: Mona the Octocat

     third-greeting:
       description: another greeting
       required: false

   runs:
     using: "node12"
     main: "main.js"
   ```

   </details>

   <details><summary>my-workflow.yml</summary>

   ```yaml
   name: JS Actions

   on: [push]

   jobs:
   action:
       runs-on: ubuntu-latest

       steps:
       - uses: actions/checkout@v1

       - name: hello-action
           uses: ./.github/actions/hello-world
           with:
           first-greeting: Learning Lab User

   ```

   </details>

2. Save the changes to each file
3. Commit the changes to this branch
   `git add .`
   `git commit -m 'updating our files'`
4. Push the changes from your local machine to this repository.
   `git push`

---

I'll respond here when you finish this step.
