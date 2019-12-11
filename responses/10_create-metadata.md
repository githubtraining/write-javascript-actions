### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory.

Our Action does not require much metadata for it to run correctly. We will not be accepting any inputs, nor setting any outputs. Because of that we simply need to name it, give it a description and define its environment.

1. Create a file named `action.yml`
2. Use the `name` parameter to name your Action `"external API action"`
3. Next, add a `description` parameter and give it a value of `"use an external API to retrieve and display a joke"`
4. Lastly, define the `run` parameter to use `"node12"` to execute the `"main.js"`

   <details><summary>View the complete file</summary>

   ```yaml
   name: "external API action"

   description: "use an external API to retrieve and display a joke"

   runs:
     using: "node12"
     main: "main.js"
   ```

   </details>

5. Save the `action.yml` file
6. commit the changes:
   `git add .`
   `git commit -m 'update action.yml'`
7. push them to the `action-two` branch:
   `git push`
