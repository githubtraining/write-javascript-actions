### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/joke-action` directory.

Our action does not require much metadata for it to run correctly. We will not be accepting any inputs, we will however be setting a single output this time.

We will not use the `joke-output` in in this portion of the course. There will be a later step that will rely on this actions output.

1. Create the action metadata file `.github/actions/joke-action/action.yml`
2. Use the `name` parameter to name your action `"external API action"`
3. Next, add a `description` parameter and give it a value of `"use an external API to retrieve and display a joke"`
4. Create an `outputs:` with an id of `joke-output:` and add a `description:` so we know what the output is for
5. Lastly, define the `runs:` parameter to use `"node12"` and set the `main:` parameter to `"main.js"`

   <details><summary>View the complete file</summary>

   ```yaml
   name: "external API action"

   description: "use an external API to retrieve and display a joke"

   outputs:
     joke-output:
       description: The resulting joke from the icanhazdadjokes API

   runs:
     using: "node12"
     main: "main.js"
   ```

   </details>

6. Save the `action.yml` file
7. Commit the changes and push them to GitHub:
   ```shell
   git add action.yml
   git commit -m 'add metadata for the joke action'
   git push
   ```

---

I'll respond when you push to this branch. 