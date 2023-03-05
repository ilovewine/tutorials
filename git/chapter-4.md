# Chapter 4

## About branches

Sometimes when working with multiple developers or in case when the project gets too big, you would like to separate the development to live "its own life". This is possible thanks to git branches. As the name implies, they can be likened to a tree with branches. Its' root is the common codebase that the branches will derive from. As described in [Chapter 1](chapter-1.md), a branch is a collection of commits. Moreover, each branch can be created at any commit point. Branches can be pushed to repository or kept locally. 

## Git branch characteristics

Each branch must have a unique name which you can address later on. The first, root branch is usually named `master` or `main`. Additionally, when initializing the git project with `git init .` command, you create a pointer that indicates a commit from which you are working at the moment. This pointer is called `HEAD` and it can be used to traverse in the branch.

In order to create a new branch, type `git branch <branch_name>`. Then, you will be able to move to that branch with `git checkout <branch_name>`. 

*NOTE: You can perform these two actions together with just one command: `git checkout -b <branch_name>`.*

You can also move to a specific commit. Each commit has it's own SHA key which serves it's purpose as a unique ID. To obtain such information, you can lookup commits in your branch by inspecting `git log`. After you pick up your desired ID, you can do `git checkout <sha_key>` to checkout to this commit.

## Merging branches

There are many ways to merge branches, but before we introduce them, we need to understand why we would want to do that. 

Let's suppose that you're working with your dev team on a project and that each one of you creates a branch from `main` branch to do your task. After making some commits in your branch you want these changes to appear in the `main` branch so that it can be released for production (which usually is being published from the `main` branch) and shared with the rest of the team.

When working with team you will usually come up with the term *pull request*, but for now let's focus on the `git merge` and `git rebase` commands which are the two main ways to go when connecting two branches.

`git merge` works in the following way - firstly, you need to checkout to the desired branch (`git checkout <target_branch>`). Then all you need to do is type `git merge <branch_to_be_merged>`.

This procedure will result in a common commit that will be shared with these two branches. It will contain all changes from `<target_branch>` and `<branch_to_be_merged>`.

`git rebase`, on other hand, will reposition the root commit of `<branch_to_be_merged>` to the last commit on `<target_branch>` and apply all previously created commits there. From this point you will be able to `git merge` without a merge commit (since both these branches will share a common codebase).

### Tasks

1. Create a branch from your `main` or `master` branch (*NOTE: we will refer to this branch as `main`*) - `xyz`
2. Create some commits in `xyz`
3. Create another branch from `xyz` - `abc`
4. Create some commits in `abc`
5. Merge `abc` to `xyz` and then rebase `xyz` with `main`

## Conflicts

Sometimes git will produce something that is called a *git merge conflict*. This can happen when two merging branches have a different codebase and it's impossible to connect them without some manual modifications. They will be represented by two separated sections like this:

```
<<<<<<< HEAD
A piece of code originating from the branch that you're currently on
=======
A piece of code located in the branch to be merged
>>>>>>> <sha_key_of_target_branch>
```

If you're working with some advanced text editors like Visual Studio Code, Sublime or even more sophisticated IDEs like JetBrains of Visual Studio, then you will have the opportunity to use the tools that are or can be installed in order to help you resolve the conflicts. Otherwise, you need to manually remove unwanted lines of code and the unnecessary additions.

*NOTE: for both commands, there are two following options available: `git <command> --abort` and `git <command> --continue`. These prior one is useful when, during the merging operation, you want to revert to the state before merging. The latter is for continuing with merging after fixing conflicts.*

### Tasks

1. Checkout to `main` branch
2. Modify one of your created files - we will call it `file`
3. Commit, then checkout to `xyz` branch
4. From there, modify the same `file` lines (with a different text)
5. Commit, then merge `xyz` into `main` - you should be able to see a git merge conflict message
6. Fix `file`  by removing unwanted lines, then `git add file` and `git merge --continue` to proceed with the merging operation