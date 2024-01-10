# Merging

## Shiny day merge

Merging branches in Git, combines work from two different branches, creates a special commit that has two unique parents

Switch to destination branch:

```bash
git checkout <destination-branch-name>
```

To merge a branch into the current branch, run this command

```bash
git merge <branch-name>
```

This will merge the provided branch into the current (checked out) branch.

## CONFLICTS

Basic scenario of a conflict, is when two programmers modify the same file on different branches, and they merge the two branches into the original branch that they checked out from, the first merge always works, it's the second merge that causes the conflict,
for example, a file named `index.html` has a contact section, one developer wrote _contact : absi.gittawi@josa.ngo_ and the other wrote _please contact us at gittawi.absi@josa.ngo_, when doing the second merge git notified the merger that there's a conflict in the file `index.html`,
and leaves the file as shown below.

```bash
<<<<<<< HEAD:index.html
contact : absi.gittawi@josa.ngo

=======

 please contact us at gittawi.absi@josa.ngo

>>>>>>> iss53:index.html
```

So there are tools that does the exact boring process for us, for example [GNU Meld](http://meldmerge.org/),

This tool is ran using git, with the merge tool command

```bash
git mergetool
```

Of-course running this command when there are no conflicts in the current branch will do nothing, cuz, well, there are no conflicts, imagine someone telling you to move a chair that doesn't exist!

This will prompt you what tool to use to resolve conflicts for each file with conflicts in it, and you can then accept the new, or old changes for that particular file.

If you are using a modern IDE or text editor, there's a 90% chance that it has a merge conflict resolver tool built into it,

For example:

- Visual Studio Code
- Visual Studio
- JetBrains IDEs (all of them)
- Android Studio

If your IDE doesn't have a merge resolver tool, use meld it does the job perfectly.

___

### [⇐ Previous](/material/03-branching.md.) | [Get to start ⇒](/README.md)
