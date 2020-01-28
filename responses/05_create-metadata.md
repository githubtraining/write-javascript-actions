## Enough talk, lets do this!

Now that we know what action metadata is, let's create the metadata for our current **hello-world** action.

### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

We will start with using the parameters that are **required** and later implement some optional parameters as our action evolves.

1. Create a file named `action.yml`
2. Use the `name` parameter to name your action `"my hello action"`
3. Next, add a `description` parameter and give it a value of `"say hello with GitHub Actions"`
4. Lastly, define the `run` parameter to use `"node12"` to execute the `"main.js"`

   <details><summary>View the complete file</summary>

   ```yaml
   name: "my hello action"

   description: "say hello with GitHub Actions"

   runs:
     using: "node12"
     main: "main.js"
   ```

   </details>

5. Save the `action.yml` file
6. Commit the changes:
   `git add action.yml`
   `git commit -m 'create action.yml'`
7. Push them to the `hello-world` branch:
   `git push`
