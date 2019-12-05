## Enough talk, lets do this!

Now that we know what Action metadata is, let's create the metadata for our current **hello-world** Action.

I will be doing this from within [Visual Studio Code](https://code.visualstudio.com/) and that will be reflected in the images that I show you.  If you are using a different editor then your screen may look different.

### :keyboard: Activity: Create the metadata file

💡All of the following steps take place inside of the `.github/actions/hello-world` directory. 

We will start with using the parameters that are **required** and later implement some optional parameters as our Action evolves.

1. Create a file named `action.yml`
2. Use the `name` parameter to name your Action `"my hello action"`
3. Next, add a `description` parameter and give it a value of `"say hello with Actions"`
4. Lastly, define the `run` parameter to use `"node12"` to execute the `"main.js"` file that doesn't exist yet.

<details><summary>View the complete file</summary><img src="https://i.imgur.com/xCuBdI4.png" alt="screenshot of action.yml file" />

<details><summary>Raw code to copy</summary>

```yaml
name: "my hello action"

description: "say hello with Actions"

runs:
  using: "node12"
  main: "main.js"
```
</details>

</details>

5. Save the `action.yml` file
6. commit the changes:
   `git add .`
   `git commit -m 'update action.yml'`
7. push them to the `hello-world` branch:
   `git push`
   