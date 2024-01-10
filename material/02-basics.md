# Git basics

## Reading Resources

### Git

* [Git](https://git-scm.com/) is a distributed version-control system for tracking changes in source code during software development.
* [Git Book](https://git-scm.com/book/en/v2) -- **IMPORTANT**
* [Learn Git from Atlassian](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)

### Github

* [Github](https://github.com) is a US-based global company that provides hosting for software development version control using Git.

### Command Tutorials

* [Git Commands Tutorial - Part 1](https://kolosek.com/git-commands-tutorial-part1/)
* [Git Commands Tutorial - Part 2](https://kolosek.com/git-commands-tutorial-part2/)

## Installation

Installation file:  [01-installation.md](/material/01-installation.md)

## Initializing repositories

### What is a Git repository?

A Git repository is a directory containing all of a project's files, and it is managed by Git, where you can see a `.git` directory in **all** Git repositories, this directory allows Git to keep track of each file's revision history, and other Git data like branches and merges.

### Initializing in the same directory (folder)

To initialize Git in an existing project, go to that project's directory and run the command

```bash
git init
```

This will create the `.git` directory allowing Git to keep track of your files' changes.

### Initializing into a new directory (folder)

To a Git managed project, run the following command

```bash
git init <directory-name>
```

This will create a new directory with the specified name with `.git` directory inside of it allowing Git to keep track of your files' changes.

### Cloning an existing repository

Since Git is a distributed version controlling system, repositories may exist on some remote host like GitHub, Gitlab, or Bitbucket.

For example cloning this repository

```bash
git clone https://github.com/jordanopensource/git-training
```

This will create a new directory named `git-training` with the content of the clone repository's files.

### Forking a repository

Forking; and its name gives it away, it's making a fork, like road forks, where a main road is forked side road(s), and eventually it looks like an eating fork, the same concept applied to Git repositories, where there's a main branch (road) on a repository, and you create a fork branch (side road) of it.

All Git hosts support forking a public repository, where you copy the repository into your account or organization.

## Staging and commits

Each file in a Git repository goes through the four Git file stages:

* **Untracked**: The file is newly created or moved from another directory to a Git directory, and Git doesn't keep any track of it.
* **Unmodified**: The file is tracked by Git, i.e has been committed before, and has no new changes.
* **Modified**: An uncommitted file that has been modified but not committed yet.
* **Staged**: A modified file that has been added to be committed.

Here's a figure showing the relations between the four stages.
![git files stages](/resourses/git-files-stages.png)

### Committing a file

After creating a file (untracked) or editing an existing one (unmodified), you can add the file to the staging area, by running this command.

```bash
git add <file-name>
```

Or using this command to add all of the files in the current directory.

```bash
git add .
```

Now to move the file into the unmodified stage, commit the file with a commit message

> Commit messages should describe what happened to a file, in an imperative way
> e.g "Create <file-name>"

```bash
git commit -m "Create <file-name>"
```

Now the file that you have just committed is in the unmodified stage, where if you made a new modification to it it will get moved to the modified stage, and the cycle continues...

### Discarding changes done after a commit

If you modified a file, after a commit, and then realized that the changes weren't needed, you can rollback to the latest tracked version by Git, by running the following command.

```bash
git checkout -- <file-name>
```

## Pushing and Pulling

When you make changes on a local repository, you need to synchronize those changes with the remote repository, and the way to do that is **pushing** your changes

```bash
git push
```

And vice versa, when you want to update your local repository from the remote repository, you **pull** the changes to your local repository

```bash
git pull
```

## Understanding status and logs

You can view the full commit history of a repository's branch by running the command

```bash
git log
```

And you can check the repository's current status (untracked, modified and staged files), by running the command

```bash
git status
```

___

### [⇐ Previous](/material/01-installation.md) | [Next ⇒](/material/03-branching.md)
