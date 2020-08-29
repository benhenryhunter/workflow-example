# Git Workflow Example

## Overview

This repository stands as an opinionated example workflow for using Github and git.

To install git please follow the directions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## All commands will all be bash commands

## Git Basics

### Repositories

A git repository is a collection of code and the changes that the collection has undergone.

These changes can be adding, deleting, moving, or modifying the contents of files or folders.

### Remote repositories

Remote repositories refer to locations on a common repository hosted on some server.  Repositories can have multiple remotes but generally only have one.

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
