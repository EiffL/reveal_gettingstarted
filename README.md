# reveal_gettingstarted
Small repository to help you get your reveal.js repository of talks started

## What are the steps?

Below I list the steps needed to setup your repo, you can find my `talks` repo if you want to checkout the final product here: https://github.com/EiffL/talks

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

And that's mostly it! We are ready to create a new presentation!

### Step IV: Creating a new presentation

It will always be the same steps, you can copy them in the README of your
repo so that you can easily fund them again next time.

  - Create a new branch, make a copy of `template`, and `cd` there
  - git submodule current version of reveal.js
    ```
    $ git submodule add https://github.com/EiffL/reveal.js.git
    $ cd reveal.js
    $ git submodule update --init --recursive
    ```
  - copy `package.json`, `gruntfile.js`, `gulpfile.js` from  the `reveal.js` folder to the talk directory
  - Update/install npm modules to make sure it works with this version:
    ```
    $ npm install
    ```
  - Start the server:
    ```
    $ npm start
    ```

At that point, you should be able to see your new presentation in your web browser. You can edit the `index.html` file and your browser should reload when you save it.

If you want to add images and files, you can drop them in the `assets` folder, which will be shared between all of your talks.

When you are satisfied with your talk, you can commit your changes, and push to GitHub.

The last step to publish your talk is to make a Pull Request, to merge your talk branch back to the `main` branch.


### Step V: Setting up GitHub Pages

In order to host your presentations online, we need to activate the
GitHub Pages hosting service for this repo:

- Go to your repo `Settings` on GitHub.
- Scroll down to the `GitHub Pages` section.
- Enable hosting from the `root/` directory of your `main` branch


And that's it. After a few minutes, your presentation should be available
at:
```
https://username.github.io/talks/your_presentation_name
```

If that doesn't work, maybe you need to add an empty `.nojekyll` file in your root directory.

Congrats on setting up your Reveal.js repo for talks!
