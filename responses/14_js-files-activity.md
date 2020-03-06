### :keyboard: Activity: Create the final JavaScript file

I'm counting on you this time! In the previous steps I have guided you heavily on what to type along the way. This time I ask that you look back on the things you've done in this course and pull from the knowledge you already have to accomplish these tasks.

1. Create a file named `index.js`. **Its full path should be: `.github/actions/issue-makes/index.js`.**
2. Create the `core` and `github` variables
3. Create an asynchronous function named `run()`
4. Inside a try/catch block define the `issueTitle`, `jokeBody`, `token` and `octokit` variables
5. Use the `issues.create()` octokit method to define your API request
6. Add the catch portion of the try/catch block
7. Use the `setFailed()` method from the `@actions/core` package to stop your action and log and error if something goes wrong
8. Save the file
9. Commit and push the changes to this branch
   ```shell
   git add index.js
   git commit -m 'create index.js'
   git push
   ```

I'll respond once you push to this branch.

---

<details><summary>View the complete file</summary>

```javascript
const core = require("@actions/core");
const github = require("@actions/github");

async function run() {
  try {
    const issueTitle = core.getInput("issue-title");
    const jokeBody = core.getInput("joke");
    const token = core.getInput("repo-token");

    const octokit = new github.GitHub(token);

    const newIssue = await octokit.issues.create({
      repo: github.context.repo.repo,
      owner: github.context.repo.owner,
      title: issueTitle,
      body: jokeBody
    });
  } catch (error) {
    core.setFailed(error.message);
  }
}

run();
```

</details>
