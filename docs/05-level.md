# The States

## Goal
- Understand that Git works with states, not with the files.

Most version control systems work with files. You add the file to source control and the system tracks the changes from that moment on.

Git focuses on the states of a file, not the file itself. A `git add file` command does not instruct Git to add the file to the repository, but to record the current state of the file so it can be committed later.

We will try to explore the difference in this lesson.

## 1. First change: Adding HTML tags
Modify the “Hello, World” page so that it contains the standard HTML tags `<html>` and `<body>`.

hallo.html:  
```html
<html>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

## 2. Add change
Now add this change to Git staging.

Command:  
```console
git add hallo.html
```

## 3. Second change: Add the HTML header
Now add the HTML header section (`<head>`) to the “Hello, World” page.

hallo.html:  
```html
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

## 4. Check the current status

Command:  
```bash
git status
```  

You will see...

Result:  
```bash
$ git status  
# On branch main  
# Changes to be committed:  
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hallo.html
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be ommitted)
#   (use "git checkout -- <file>..." to discard changes in orking directory)
#
#   modified:   hallo.html
#
```

Please note that `hallo.html` is listed twice in the status. The first change (adding standard tags) is staged and ready for a commit. The second change (adding HTML headers) is not staged. If you were to commit now, the headers would not be stored in the repository.

Let’s check.

## 5. Commit
Commit the staged changes (standard tags) and check the status again.

Command:  
```bash
git commit -m "Added standard HTML page tags"  
git status  
```

You will see...

Result:  
```bash
$ git commit -m "Added standard HTML page tags"
[master 8c32287] Added standard HTML page tags  
 1 files changed, 3 insertions(+), 1 deletions(-)

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

The status indicates that `hallo.html` has unstaged changes but is no longer in the staging area.

## 6. Add the second change

Add the second change to the staging area and then run git status.

Commands:  
```bash
git add .
git status
```

**Note:** The current directory (‘.’) is our file to add. This is the most convenient way to add all changes in the current directory and its folders. But since it adds everything, it's a good idea to check the status before adding to ensure you are not adding a file you shouldn’t.

I wanted you to see the `add .` trick, and we will later add more explicit files.

You will see...

Result:  
```bash
$ git status
# On branch main
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   modified:   hallo.html
#
```

The second change has been staged and is ready for a commit.

## 7. Commit the second change

Command:  
```bash
git commit -m "Added HTML header"
```

## Complete the level
Did you do everything correctly? Check it with the command `npm start` inside the Git Adventure directory and unlock the next level (docs/06-level.md).