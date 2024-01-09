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

Conflicts are good (in the right context), and git conflicts are the right context, think of it as some sort of a constructive difference of ideas, both sides have the same **goal** which is in this case adding a feature, or fixing a bug to a codebase,
but they differ in the way of achiving it, or the place of that particular change, so git comes to the rescue and lists those conflicts in a resolvable way.

Basic scenario of a conflict, is when two programmers modify the same file on different branches, and they merge the two branches into the original branch that they checked out from, the first merge always works, it's the second merge that causes the conflict,
for example, a file named `index.html` has a contact section, one developer wrote _contact : absi.gittawi@josa.ngo_ and the other wrote _please contact us at gittawi.absi@josa.ngo_, when doing the second merge git notified the merger that there's a conflict in the file `index.html`,
and leaves the file as shown below.

```
<<<<<<< HEAD:index.html
contact : absi.gittawi@josa.ngo

=======

 please contact us at gittawi.absi@josa.ngo

>>>>>>> iss53:index.html
```

This doesn't look good at all, the html file renders fine, but imagine if the conflict was in a real code file, for example a `cpp` file, the file is uncompilable now, sinde it has the weird `>>>>>>>` and the other git conflict indicators that's not defined in C++'s grammer,
as you can see this is a real issue, to resolve this, you have to choose one of the versions, and delete the other one and the conflict indicators, that seems tedious right? I mean imagine if you have 10 conflicts across 7 files, resolving this will be hell.

So there are tools that does the exact boring process for us, for example [GNU Meld](http://meldmerge.org/),

This tool is ran using git, with the mergetool command

```bash
git mergetool
```

Of-course running this command when there are no conflicts in the current branch will do nothing, cuz, well, there are no conflicts, imagine someone telling you to move a chair that doen't exist!

This will prompt you what tool to use to resolve conflicts for each file with conflicts in it, and you can then accept the new, or old changes for that particular file.

If you are using a modern IDE or text editor, there's a 90% chance that it has a merge conflict resolver tool built into it,

For example:

- Visual Studio Code
- Visual Studio
- JetBrains IDEs (all of them)
- Android Studio

If your IDE doen't have a merge resolver tool, use meld it does the job perfectly.
