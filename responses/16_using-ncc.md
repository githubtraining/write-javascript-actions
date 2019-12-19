## Getting rid of node_modules

We typically don't commit a `node_modules` folder in a repository. These can often grow to be huge if your project has many dependencies. Because of the way Node works this folder is a necessary evil, but there is a way to get rid of it!

First you need to install a tool called [ncc](https://github.com/zeit/ncc). You'll want to install this tool globally so that you can use as if it's any other CLI tool on your machine.

What **ncc** does is take all the dependencies within your project and compile them into a single JavaScript file. This allows you to avoid committing the `node_modules` folder in your Actions source code.

**Install ncc**
`npm install -g @zeit/ncc`

**Using ncc**
When you use ncc:

`ncc build <input-file>`

A new directory named `dist` will be created. Within that directory you will find a file named `index.js`. To tell GitHub Actions that this new `index.js` file is the one that should run when your Action is used a small edit to the `action.yml` file needs to be made.

_before:_

```yaml
runs:
  using: "node12"
  main: "index.js"
```

_after:_

```yaml
runs:
  using: "node12"
  main: "dist/index.js"
```

Once you make this change you can delete the `node_modules` folder and commit those changes to the repository that contains your Actions source code.

---

📖Further help [using ncc](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-a-javascript-action#commit-and-push-your-action-to-github) is in the GitHub Actions documentation.
