# Making Changes

## Goals
To learn how to monitor the state of the working directory.

## 1. Modify the “Hello World!” page
Let’s add some HTML tags to our greeting. Change the file content to:

```html
<h1>Hello, World!</h1>
```

## 2. Checking the status
Check the status of the working directory.

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
#   (use "git checkout -- <file>..." to discard changes in working irectory)
#
#   modified:   hallo.html
#
# no changes added to commit (use "git add" and/or "git commit -a")
```

The first important point here is that Git knows the file hallo.html has been changed, but these changes have not yet been added to the repository.

Another important point is that the status message gives hints about what to do next. If you want to add these changes to the repository, use the `git add` command. To undo the changes, use `git checkout`.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/03-level.md).