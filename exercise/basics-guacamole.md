# Initializing a New Repository

## Start by Cloning

To clone an existing Git repository you can use the following command.

```bash
git clone REMOTE_URL
```

## Start by Initializing

To initialize a new Git repository in a folder called `recipe` you can use the following command.

```bash
mkdir recipe
cd recipe
git init      # Initializes a new repository
```

That was quite easy! We have now initialized an *empty* Git repository.

We can use `git status` at any point, and in any Git repository to check out what is going on:

```bash
$ git status        # Verify by checking the status

On branch main

No commits yet
```

## Create Some Files

Now let us add some files to our repository.

1. Create a file called `instructions.txt` and contains:

```bash
* chop avocados
* chop onion
* squeeze lime
* add salt
* and mix well
```

2. Create a file called ingredients.txt and contains:

```bash
* 2 avocados
* 1 lime
* 2 tsp salt
```

**Remember** you can always check the status and get a better understanding of your repository at any time using `git status`.

```bash
$ git status

On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

 ingredients.txt
 instructions.txt

nothing added to commit but untracked files present (use "git add" to track)
```

### Check Your Knowledge

* What is the current status of the repository?
* What is the current status of the repository compared to the status in the section above?
* Are the files above `staged` or `committed`?

## Adding Files to the Staging Area

Now there are **two** untracked files the repository. We can add the files from our working directory to our staging area by running:

``` bash
$ git add ingredients.txt
$ git add instructions.txt
$ git status

On branch main

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

 new file:   ingredients.txt
 new file:   instructions.txt
```

You want to add the files to the list of files tracked by Git. Git does not track any files automatically and you need make a conscious decision to add a file.

## Committing Changes to the Local Repository

Now this change (with both `ingredients.txt` and `instructions.txt`) is staged and ready to be committed.

We can commit the change(s) to the local repository by running:

```bash
$ git commit -m "adding ingredients and instructions"

[main (root-commit) aa243ea] adding ingredients and instructions
 2 files changed, 8 insertions(+)
 create mode 100644 ingredients.txt
 create mode 100644 instructions.txt
Right after we query the status to get this useful command into our muscle memory:

$ git status
```

### Check Your Knowledge

* What does the `-m` flag mean? Check out the help page for the `commit` subcommand.

## Git Log

We can use `git log` to display the history of the repository.
Each **commit** is given a unique long hash as an identifier.
Output is in reverse chronological order, *i.e. newest commits on top*.

We can also use:

* `git log --oneline` only displays the first 7 the commit hash.
* `git log --stat` only displays files which have been modified.
* `tig` is an ncurses-based text-mode interface for git. [Read more about Tig.](https://github.com/jonas/tig)

```bash
$ git log

commit 8be119e5fc1acea49b7cc90cda22714b5e138a4d
Author: Some Author <redacted@redacted.rdc>
Date:   Thu Mar 26 11:51:37 2020 +0200

    Added 'ingredients.txt' and 'instructions.txt'
```

Add 1/2 onion to ingredients.txt and also the instruction to “enjoy!” to instructions.txt. Do not stage the changes yet.

## Record Changes

Add **1/2 onion** to `ingredients.txt` and also the instruction to **"enjoy!"** to `instructions.txt`.
Do not stage the changes yet.

Use `git diff` to examine the difference between the files.

Now you can go ahead and stage your changes *separately*, one commit with the changes done to `ingredients.txt`. The other with the changes done to `instructions.txt`.

After committing the changes to your local repository, you can use `git log` to verify your changes have been committed.

### Check Your Knowledge

* What is different between the files?
* How does the diff tool work?
* How can I specify which diff tool is used by Git?
* What happens when we leave out the `-m` flag?
* How many commits were expected? How many are there?

## Comparing and Inspecting Changes

* We can use the `git diff <hash1> <hash2>` to display the difference between two commits.
* We can use the `git show <hash>` to inspect a specific commit.

## Summary

The table below contains a summary of all of the Git command you have learned so far. **Check your knowledge!**

```bash
git init    # Initialize new repository
git add     # Add files or stage file(s)
git commit  # Commit staged file(s)
git status  # See what is going on
git log     # See history
git diff    # Show unstaged/uncommitted modifications
git show    # Show the change for a specific commit
git rm      # Semove tracked files
```
