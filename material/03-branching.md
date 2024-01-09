# Branching

Again, since Git is a distributed version control system, multiple people can work on the same repository, but that can't be done without order, so, to do that each branch has the ability to create branches,
where there's a default branch that has the original code, and each new branch is a clone of the default branch at the checkout time, to accept changes from a checked out branch, the repository's owner have to merge those changes with the default branch.

Branches in Git:

- Incredibly lightweight
- References to a specific commit -- nothing more
- A branch is a pointer that moves forward with every new commit
- The default branch name in git is master
- GitHub calls the default branch main

To create a new branch from the latest revision (last commit) of the default branch, run this command

```bash
git branch <branch-name>
```

To switch to the new branch, run this command

```bash
git checkout <branch-name>
```

You can also create a new branch and checkout into it at the same time using this command

```bash
git checkout -b <branch-name>
```

To delete a branch that have been merged with the default branch, run this command

```bash
git branch -d <branch-name>
```

To delete a branch either way, run this command

```bash
git branch -D <branch-name>
```

Keep in mind that this is a dangerous command, where it will delete the branch without any confirmation.

To delete a remote branch, run this command

```bash
git push <remote_name> --delete <branch_name>
```
