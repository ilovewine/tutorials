# Chapter 4

## About branches

Sometimes when working with multiple developers or in case when the project gets too big, you would like to separate the development to live "its own life". This is possible thanks to git branches. As the name implies, they can be likened to a tree with branches. Its' root is the common codebase that the branches will derive from. As described in [Chapter 1](chapter-1.md), a branch is a collection of commits. Moreover, each branch can be created at any commit point. Branches can be pushed to repository or kept locally. 

## Git branch characteristics

Each branch must have a unique name which you can address later on. The first, root branch is usually named `master` or `main`. Additionally, when initializing the git project with `git init .` command, you create a pointer that indicates a commit from which you are working at the moment. This pointer is called `HEAD` and it can be used to traverse in the branch.

In order to create a new branch, type `git branch <branch_name>`. Then, you will be able to move to that branch with `git checkout <branch_name>`. 

*NOTE: You can perform these two actions together with just one command: `git checkout -b <branch_name>`.*

You can also move to a specific commit. Each commit has it's own SHA key which serves it's purpose as a unique ID. To obtain such information, you can lookup commits in your branch by inspecting `git log`. After you pick up your desired ID, you can do `git checkout <sha_key>` to checkout to this commit.