## Create and edit the third Actions action.yml file

Like our "hello world" Action, this Action will require at least one `input:` parameter. We need this parameter so that our JavaScript for this Action has access to the `output:` from the joke Action.

If you recall, in the `my-workflow.yml` file, we stated this Action would take a specific input named `joke:` and we set it's value to the output of the previous Action.

```yaml
- name: create-issue
  uses: ./.github/actions/issue-maker
  with:
    joke: ${{steps.jokes.outputs.joke-output}}
```

Because of this, we need to define `joke:` as one of our `inputs:` for this action. Remember when we did this with the first Action? It looked a little like this:

```yaml
inputs:
  first-greeting:
    description: who you would like to greet in the console
    required: true
    default: Hubot
```

Now, we will do something similar so that our Action matches what our workflow expects.

### :keyboard: Activity: Create the final metadata file

💡All of the following steps take place inside of the `.github/actions/issue-maker` directory.

We will use the `joke-output`, as well as an issue title, in in this portion of the course so we need to accept `inputs:` for our Action.

1. Create a file named `action.yml`
2. Use the `name` parameter to name your Action `"issue maker"`
3. Next, add a `description` parameter and give it a value of `"consume the output of the previous Action and create a new issue in the repository"`
4. Create an `inputs:` with an id of `joke:` and add a `description:` of `"This will become the body of the created issue"`
5. Create another `inputs:` with an id of `issue-title:` and a `description:` of `"Every issue needs a title, it's nice to supply one, even though you could do this dynamically within your code"`
6. Give the `issue-title:` a `default:` value of `"a joke for you"`
7. Lastly, define the `run` parameter to use `"node12"` to execute the `"main.js"`
8. Save the `action.yml` file
9. commit the changes:
   `git add .`
   `git commit -m 'update action.yml'`
10. push the changes to the `action-three` branch:
    `git push`

---

<details><summary>View the complete file</summary>

```yaml
name: "I have issues"

description: "consume the output of the previous Action and create a new issue in the repository"

inputs:
  joke:
    description: "This will become the body of the created issue"
  issue-title:
    description: "Every issue needs a title, it's nice to supply one, even though you could do this dynamically within your code"
    default: "a joke for you"

runs:
  using: "node12"
  main: "main.js"
```

</details>
