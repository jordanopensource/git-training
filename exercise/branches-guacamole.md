# Identify your Branch

To see on which branch HEAD is pointing, you can use the command below:

```bash
$ git branch

* main
```

Remember, this command shows where we are, it does not create a branch.

There is only main and we are on main (star represents the HEAD).

## Creating Branches

Now will learn how to create new branches. In the example below we will create a branch `experiment` where we add `cilantro` to `ingredients.txt`.

```bash
git branch experiment    # create branch called "experiment" pointing to the present commit
git checkout experiment  # switch to branch "experiment"
git branch               # list all local branches and show on which branch we are
```

Verify that you are on the experiment branch (note that git graph also makes it clear what branch you
are on: HEAD -> branchname):

```bash
$ git branch

* experiment
  main
```

Then add `2 tbsp cilantro` on top of the `ingredients.txt`:

```
* 2 tbsp cilantro
* 2 avocados
* 1 lime
* 2 tsp salt
* 1/2 onion
```

Stage this and commit it with the message “let us try with some cilantro”.

Then reduce the amount of cilantro to 1 tbsp, stage and commit again with “maybe little bit less cilantro”.

## Merging Branches

Now that we are happy with our changes, we can merge our changes back into the branch we diverged from.

First we make sure we are on the branch we wish to merge **into**:

```bash
$ git branch

  experiment
  less-salt
* main
```

Then we merge `experiment` into `main`:

```bash
git merge experiment
```

## Merging Branches

To delete branches in Git, we use the command below:

```bash
git branch -d experiment
```

## Exercise: Branches

#### Create a New Branch

* Change to the branch `main`.
* Create another branch called `less-salt` where you reduce the amount of salt to `1`.
* Commit your changes to the `less-salt` branch.
* Examine the differences in the file `ingredients.txt` on branch `main` and on `less-salt`.

#### Update and Existing Branch

* Change to the branch `main`.
* Create a file called `README.md` with the content below, then commit your changes.

```
# Guacamole Recipe

Used in teaching Git.
Git is important for DevOps, and software engineering.
```

#### Deleting a Branch

* Merge your changes from `less-salt` back into `main`.

## Summary

The table below contains a summary of all of the Git command you have learned so far. **Check your knowledge!**

```bash
git branch               # see where we are
git branch <name>        # create branch <name>
git checkout <name>      # switch to branch <name>
git merge <name>         # merge branch <name> (to current branch)
git branch -d <name>     # delete branch <name>
git branch -D <name>     # delete unmerged branch
```

The shorthand form to create and checkout a branch:

```bash
git checkout -b <name>   # create branch <name> and switch to it
```
