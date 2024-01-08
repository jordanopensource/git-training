# Git basics

Make sure that you have `git` installed on your machine, if not, refer to [this](/material/01-installation.md) page.

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

Forking; and its name gives it away, it's making a fork, like road forks, where a main road is forked side road(s), and evantually it looks like an eating fork, the same concept applied to Git repositories, where there's a main branch (road) on a repository, and you create a fork branch (side road) of it.

All Git hosts support forking a public repository, where you copy the repository into your account or organization.

## Staging and commits

Each file in a Git repository goes throgh the four Git file stages:

- **Untracked**: The file is newly created or moved from another directory to a Git directory, and Git doesn't keep any track of it.
- **Unmodified**: The file is tracked by Git, i.e has been commited before, and has no new changes.
- **Modified**: An uncommited file that has been modified but not committed yet.
- **Staged**: A modified file that has been added to be commited.

Here's a figure showing the relations between the four stages.
![git files stages](/resourses/git-files-stages.png)

### Commiting a file

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

Now the file that you have just commited is in the unmodified stage, where if you made a new modification to it it will get moved to the modified stage, and the cycle continues...

### Discarding changes done after a commit

If you modified a file, after a commit, and then realized that the changes weren't needed, you can rollback to the latest tracked version by Git, by running the following command.

```bash
git checkout -- <file-name>
```

## Pushing and Pulling

## Understanding status and logs
