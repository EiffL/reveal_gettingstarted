# reveal_gettingstarted
Small repository to help you get your reveal.js repository of talks started

## What are the steps?

### Step I: Create a repo

You can create a repo called `talks` under your GitHub username. This is
so that your talks will be available at the following address:
```
https://username.github.io/talks
```

### Step II: Setting up the structure of the repo

Create the following structure:

```
talks/
|- assets/
|- template/
|- node_modules/
```
The `assets` folder will be used to store images and plots you want to
use in your talks. The `template` folder will be a folder with a minimal talk setup you can just copy/paste to get a new talk started.
In addition, we will add a local folder called `node_modules` but **we will not commit it!** To make sure that `node_modules` is never committed to github, let's add a `.gitignore` file with the following content:
```
node_modules/
```

### Step III: Setup the template folder

In the `template` folder we are going to create relative symbolic
links to the `assets` and `node_modules` folders:
```bash
$ ln -s ../assets .
$ ln -s ../node_modules .
```
and you can copy the [index.html](index.html) file example from this
repository into your template folder.
