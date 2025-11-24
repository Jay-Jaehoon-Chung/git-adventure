# Discard Local Changes (before staging)

## Goal
- Learn how to discard changes in your working directory.

## 1. Checking out the main branch
Make sure you are on the latest commit in the main branch before starting.

Command:  
```bash
git checkout main
```

## 2. Modify the hallo.html file
Sometimes you modify a file in your local working directory and want to simply discard the changes. The `checkout` command helps with this.

Modify the `hallo.html` with an unwanted comment.

```html
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <!-- This is a bad comment.  We want to revert it. -->
  </body>
</html>
```

## 3. Check the status
First check the status of the working directory.

Command:  
```bash
git status
```

Result:  
```bash
$ git status
# On branch main
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#   modified:   hallo.html
#
# no changes added to commit (use "git add" and/or "git commit -a")
```

We see that the `hallo.html` file has been changed but is not staged yet.

## 4. Revert the changes in the working directory
Use the `checkout` command to check out the current version of the `hallo.html` file from the repository.

Command:  
```bash
git checkout hallo.html
git status
code hallo.html
```

Result:
```bash
$ git checkout hallo.html
$ git status
# On branch main
# nothing to commit (working directory clean)
```

The status command shows that there are no unstaged changes in the working directory. And our “bad comment” is no longer in the file.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/11-level.md).