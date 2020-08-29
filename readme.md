# Git Workflow Example

## Overview

This repository stands as an opinionated example workflow for using Github and git.

To install git please follow the directions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

**All commands will all be bash commands**

## Git Basics

### Repositories

A git repository is a collection of code and the changes that the collection has undergone.

These changes can be adding, deleting, moving, or modifying the contents of files or folders.

### Remote repositories

Remote repositories refer to locations on a common repository hosted on some server.  Repositories can have multiple remotes but generally only have one called `origin`

### Starting a new repository

To start a new repository run:

``` bash
git init
```

This will turn the directory which you ran this command into a repository by adding a `.git/` folder.

### Cloning an remote repository

Cloning a repository is copying the code and history to your computer.  To do this we use the command `git clone {remote}`

``` bash
git clone https://github.com/dickmanben/workflow-example.git
```

When this command is run, it will copy the contents from this repository into a folder named `workflow-example`.

### Branches

Branches are used to organize code in a repository. The root branch of a file is generally called master.  In this repository we will be using master as our root branch.

Changes in a branch are recorded in the git history and are separate from other branches until the changes are brought into another branch using pull requests or rebasing.

When changes are going to be made to a repository it is common and most development teams will require you to "branch" off of master and make those changes in a separate branch.

Commands:

To get a list of branches in your repository

``` bash
git branch -l
```

To create a new branch:

``` bash
git branch new-branch-name
```

And to switch to the new branch:

``` bash
git checkout new-branch-name
```

To do both of these in one command:

``` bash
git checkout -b new-branch-name
```

### Commit

Git history is tracked using commits. Commits are a set of changes to the files in a repository which have a message tied to them that describes what these changes are.  Commit messages should be clear and concise, often as imperative sentences.

Changes must be staged and committed to a branch before they can be shared.  The commit can contain small or large changes but most development teams require you to commit small changes often.

To view all of our current changes:

``` bash
git status
```

To stage all changes:

``` bash
git add .
```

To stage select files:

``` bash
git add {file path} {another file path}
```

Once changes are staged you can commit them to your branch:

``` bash
git commit -m "Imperative sentence describing your changes"
```

### Pushing Changes

Once you have changes committed to a repository you need to push them in order to publish these changes.  If you are on a new branch your remote will not know what branch you are trying to push to so you will need to create a reference on your remote using `git push --set-upstream {remote name} {branch-name}`

```bash
git push --set-upstream origin new-branch-name
```

When your branch has a reference you can just run `git push` to push new commits.

```bash
git push
```

pro-tip: if you run `git push` it will print the exact command you need to push your changes to a new remote branch where you can just copy and paste.

### Pull Requests

Pull requests are used to get changes from one branch into a different "base" branch.

To create a pull request we use github.com.  Click on the *Pull requests* tab in a repository and then click the *New pull request* button.

Pull requests should be reviewed by another developer before merging.

### Merging

Merging refers to the combining of git history from two different branches.  When a new commit is added to a branch and a pull request has been merged, the new commit is carried over to the base branch.

### Pulling Changes

When commits are merged into a branch, we will "pull" those changes using the command `git pull`.  Git pull will realign your branch with the new commits in the repository.

If a new branch got merged into master, in order to pull those changes we will do the following steps:

``` bash
git checkout master
git pull
```

### Stashing Changes

If we have any changes on the branch we're currently working on that we don't want to commit yet and need to switch to another branch, we can stash those.  To stash changes we use the command `git stash`.

To stash all changes:

``` bash
git stash
```

To unstash changes, switch back to the branch you were working on and run:

``` bash
git stash apply
```

### Forks

Forks are <s>what western cultures use to eat some food with</s> copies of repositories.  Forks are used to keep a copy of a repository in a different remote.

## Work flow exercises

We're going to practice some common work flows modifying this repository.

To begin we'll assume git is already installed and that you already have an account on github.

### Step 1: Forking this repository

We'll begin by forking this repository so that you can have a copy of this and make changes to it yourself.

Click on the `Fork` button on the top right of this page.

### Step 2: Checkout a new branch

Lets checkout a new branch called `update-readme`.

Run the command for listing branches and you should see two branches listed: master and update-readme.

### Step 3: Edit the readme.md

Change the first sentence of the readme to say `This repository stands as my example workflow for using Github and git.`

### Step 4: Commit the changes

Commit the changes using an imperative sentence. Example commit message: `Update the readme to show my proficiency using git`

### Step 5: Push your changes

Run `git push` to see that you don't have remote branch associated with your local branch.  Copy, paste, and execute the command that git tells you to use.

### Step 6: Create a pull request to your repository

If just pushed to a branch, other than your root branch, github will have a prompt to create a pull request from the main repo page.  Otherwise you can go to the `Pull requests` tab and click `New pull request`, select `master` as the "base" and your new branch as the "head"

Add a description of your change in the textarea.

### Step 7: Review your changes

Review your change and merge.

As a bonus you can add my user `dickmanben` to your repository via the collaborator settings and ask me to review your change.

## Congratulations

:tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada::tada:

You have just completed a standard git workflow!  This is a very typical workflow for many software developers and is a very basic and necessary skill to have in development industry.

While there are different branch strategies, this exercise covered the basics that you will need to know in order to work in the majority of git workflows.
