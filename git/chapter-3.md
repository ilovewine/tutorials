# Chapter 3

## About remote repositories

A remote repository is just a git repository stored in the cloud that can be accessed anywhere (assuming you have internet connection and appropriate credentials).

The remote repos are useful when working with multiple collaborators, multiple devices or just for sharing purposes. It is often a good practice to store your code remotely in case it gets corrupted locally. Without the existence of this concept you wouldn't able to read this guide - how else would I publish it? :smile:

There are many tools for remote reporistory creating & maintenance. You may have heard of tools like Github, Bitbucket or Gitlab. This guide will focus on [Github](https://github.com/) only (but feel free to check out other resources as well).

## Setup remote repository

In order to start working with a remote repo you must first create an account on git hosting service. Go to [Github](https://github.com/) and create your account. After logging in, press "New" button. You will be prompted to name your repo as well as provide additional information. Afterwards you will receive information on how to connect you local repository with the remote one. Basically it should be: `git remote add origin <URL>` where the `<URL>` is the given url which follows one of the following formats: `https://github.com/USER/REPO.git` (https) or `git@github.com:USER/REPO.git` (ssh). 

These two formats refer to the way you will access your repo, so before proceeding please familiarize yourself with 

For example, if your username is "user1" and repository name is "repo1" then the url for https url would be `https://github.com/user1/repo1.git`. 

For more information regarding https and ssh please refer to [this site](https://ourtechroom.com/tech/https-vs-ssh-in-git/).

## Push & pull your commits

In order to publish your commits to your remote repo, simply type in `git push`. This will copy all your local branches to the remote.

`git pull` is responsible for pulling all branches and new commits to your local branch tree. This is especially helpful when you're working with collaborators.

### Tasks

1. Create your Github account
2. Create your first new remote repository and give it a name
3. Connect your local git project with the brand new remote repo
4. Publish your changes