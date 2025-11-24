# Staging the Changes

## Goals
To learn how to stage changes for upcoming commits.

## 1. Add changes
Now instruct Git to stage changes. Check the status.

Command:  
```bash
git add hallo.html
git status
```

You will see...

Result:  
```bash
$ git add hallo.html  
$ git status
# On branch main
# Changes to be committed:
#   (use "git restore --staged <file>..." to unstage)
#  
#   modified:   hallo.html
#
```

Changes to hallo.html have been staged. This means that Git knows about the change, but it is not permanently in the repository yet. The next commit will include the staged changes.

If you decide not to apply the change, the `git status` command reminds you that you can use the `git restore` command to undo these changes.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/04-level.md).