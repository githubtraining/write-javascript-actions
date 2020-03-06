## Enough talk, lets do this!

Now that we know what action metadata is, let's create the metadata for our current **hello-world** action.

### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

We will start with using the parameters that are **required** and later implement some optional parameters as our action evolves.

1. Create and add the following contents to the `.github/actions/hello-world/action.yml` file:
   ```yaml
   name: "my hello action"

   description: "say hello with GitHub Actions"

   runs:
     using: "node12"
     main: "main.js"
   ```
2. Save the `action.yml` file
3. Commit the changes:
   `git add action.yml`
   `git commit -m 'create action.yml'`
4. Push them to the `hello-world` branch:
   `git push`
   
 ---

I'll respond here once I notice that you've pushed your changes.

