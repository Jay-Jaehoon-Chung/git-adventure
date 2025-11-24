# Removing Commits from a Branch

## Goal
- How to delete the last commits of the branch.

`Revert` is a powerful command from the previous level that allows you to undo all transfers to the repository. However, both original and reverted commits are still displayed in the branch history (when using the `git log` command).

Often, after a commit has already been made, we realize that it was a mistake. It would be nice to have an undo command that allows us to immediately delete the incorrect commits. This command would prevent one or more unwanted commits from appearing in the Git log history.

## 1. The Reset command
When a commit reference is specified (i.e., a branch, hash, or tag name), the `reset` command will:

1. Overwrite the current branch so that it points to the correct commit.
2. Optionally reset the staging area so that it matches the specified commit.
3. Optionally reset the working directory so that it matches the specified commit.

## 2. Check the history
Let’s do a quick scan of our commit history.

Command:  
```bash
git hist
```

Result:  
```bash
$ git hist
# * 744ff5f 2022-01-16 | Revert "Oops, we didn't want this commit" (HEAD -> main) [Gregor Biswanger]
# * 076f969 2022-01-16 | Oops, we didn't want this commit [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

We see that the last two commits in this branch are “Oops” and “Revert Oops.” Let’s remove these two using the reset command.

## 3. First mark this branch
Let’s mark the last commit with a tag so that you can find it after removing a commit.

Command:  
```bash
git tag oops
```

## 4. Reset commit to previous "Oops"
In the history log above, the commit labeled “v1” is before the “Oops” and “Revert Oops” commits. Let’s reset the branch to this point. Since the branch has a tag, we can use the tag name in the reset command (if it didn’t have a tag, we could use the hash value).

Command:  
```bash
git reset --hard v1
git hist
```

Result:
```bash
# * 5a9e60b 2022-01-15 | Added HTML header (HEAD -> main, tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

Our main branch now points to commit v1, and the “Revert Oops” and “Oops” commits no longer exist in the branch. The `--hard` parameter ensures the working directory reflects the new branch head.

## 5. Nothing is ever lost
What happened to the incorrect commits? They are still in the repository. We can still reference them. At the beginning of the lesson, we created the “oops” tag for the reverted commit. Let’s take a look at all commits.

Command:  
```bash
git hist --all
```

Result:
```bash
# * 744ff5f 2022-01-16 | Revert "Oops, we didn't want this commit" (tag: oops) [Gregor Biswanger]
# * 076f969 2022-01-16 | Oops, we didn't want this commit [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (HEAD -> main, tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

We can see that the incorrect commits have not disappeared. They are no longer listed in the main branch but still remain in the repository. They would still be in the repository even if we didn’t tag them, but then we could only reference them via their hash names.

Unreferenced commits remain in the repository until garbage collection is performed by the system.

## 6. Dangers of resetting with `reset`
Resets on local branches are generally harmless. The consequences of a “mistake” can be reversed by using the correct commit.

However, other users sharing the branch may become confused if the branch is shared on remote repositories.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/14-level.md).