# Recording Changes

## Goals
Save changes with commits.

## Staging and Committing

A staging step in Git allows us to continue making changes to the working directory, and when you decide to interact with version control, you can flexibly record the changes in small commits.

Suppose you have edited three files (a.html, b.html, and c.html). After that, you need to commit everything, so that the changes to a.html and b.html belong together in a single commit. The changes to c.html, however, are not logically connected to the first two files and should be stored in a separate commit.

Theoretically, you can do the following:
```bash
git add a.html
git add b.html  
git commit -m "Changes for a and b"

git add c.html
git commit -m "Unrelated change to c"
```

By separating staging and committing, we can easily control what should be included in a commit and what should not.

## 1. Record changes

Now, enough about staging. Let’s transfer the changes to the repository.

When you previously saved the first version of hallo.html into the repository with `git commit`, we added a comment using the -m parameter. The commit command allows interactive editing of commit messages. Now we want to see how that works.

If you omit the -m parameter on the command line, Git will bring you into the editor of your choice from the following list (in order of priority):

- GIT_EDITOR environment variable  
- core.editor configuration setting  
- VISUAL environment variable  
- EDITOR environment variable  

I configured core.editor to Visual Studio Code:  
```bash
git config --global core.editor "code --wait"
```

Let’s commit now and check the status.

Command:  
```bash
git commit
```

In your editor you will see the following:

```bash
|  
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch main
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hallo.html
#  
```

Enter the comment “Added h1 tag” in the first line. Save the file and close the editor. You should see this...

Result:  
```bash
git commit
# hint: Waiting for your editor to close the file... 
# [main 41b3c46] Added h1 tag
# 1 files changed, 1 insertions(+), 1 deletions(-)
```

## 2. Check the status

Let’s check the status at the end.

Command:  
```bash
git status
```

Result: 
```bash 
$ git status
# On branch main
# nothing to commit (working directory clean)
```

The working directory is clean, we can continue working.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/05-level.md).