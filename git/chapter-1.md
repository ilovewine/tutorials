# Chapter 1

## About git

Git is an open source distributed version control system. It allows you to create multiple version of the same project simultaneously. Thanks to git you can also create commits, which refer to the changes you (or other collaborators) made. With git you are able to create, compare and merge branches.

**Def:** A _commit_ is a record of changes made to the repository. It contains meta information, such as author name, an email and a timestamp. 

**Def:** A _branch_ is an ordered list of commits. Each branch must be named.

In a git repository there must be at least one branch from which the branch tree can be expanded. It is considered to be a main branch and is usually called _master_ or _main_. 

For detailed information about git, it's history and how it works you are encouraged to read the [Git Book](https://git-scm.com/book/en/v2).

## Git initialization

In your project directory type:
```bash
git init .
```
This command will create a hidden directory `.git` which contains all information about your repository. Without that directory, the `git` tool will not recognize your project as the `git` repository.

Thanks to that command you will be able to use `git` properly.

### Tasks

1. Create a folder on your desktop called 'git_practice' and open it in your terminal (`cd path/to/desktop/git_practice`). From there, initialize a git repository in the folder (as described above).
2. Create a text file called `README.md`
3. Paste an image of your choosing to `git_practice` folder
4. Create a subfolder in `git_practice` and put another file of your choosing in that subfolder 