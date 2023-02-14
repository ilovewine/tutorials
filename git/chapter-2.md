# Chapter 2

## Git workflow

Inside this [Git Book chapter](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) you will be able to find useful information about how git operates. The most vital information is "The Three States" section which visualizes the way the git works.

Basically, these state are the following:

1. _Modified_

    This is the stage where you're actively working on with the files. If the files are fresh new, they need to be added to the staged state by typing `git add <file/folder>`. Most of the time you will use `git add .` when the command `pwd` points to the project root directory.

2. _Staged_

    This is a point where your files a marked to be transitioned to a commit. You may face a situation where you would like only a portion of your changes to be commited. As mentioned previously, you can specify those files and add them to this stage. Afterwards, you can create a commit by using the `git commit` command. The command will prompt you to type a commit message which will describe the changes made to the project. As a shortcut you may use `git commit -m "<message>"`.

3. _Commited_

    This is the last, but also, the first stage you will encounter in your project. These stages are made into a cycle and it's purpose is to collect changes into this stage. You can view your commit tree with `git log`.

INFO: You can use `git status` to see which stage the files are currently in.

### Tasks

_NOTE: Make sure to do the tasks listed in [Chapter 1](chapter-1.md)._

1. After adding the files to your project, add them to the _staged_ database with the `git add .` command.
2. Commit the changes as described above.
3. Make sure everything is commited by using `git status` and `git log`.
 