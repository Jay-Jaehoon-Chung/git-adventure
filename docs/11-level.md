# Canceling Staged Changes (before committing)

## Goal
- Learn how to undo staged changes.

## 1. Edit the file and make changes
Make changes to the `hallo.html` file in the form of an unwanted comment.

```html
<html>
  <head>
    <!-- This is an unwanted but staged comment -->
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

Stage the modified file.

Command:  
```bash
git add hallo.html
```

## 2. Check the status
Check the status of the unwanted changes.

Command:  
```bash
git status
```

Result:  
```bash
$ git status
# On branch main
# Changes to be committed:
#   (use "git restore --staged <file>..." to unstage)
#         modified:   hallo.html
```

The status shows that the change has been staged and is ready to be committed.

## 3. Reset the staging area
Fortunately, the displayed status tells us exactly what to do to undo staged changes.

Command:  
```bash
git restore --staged hallo.html
```

## 4. Switch to the commit version

Command:  
```bash
git checkout hallo.html
git status
```

Result:
```bash
$ git checkout hallo.html
# Updated 1 path from the index

$ git status
# On branch main
# nothing to commit (working directory clean)
```

Our working directory is clean again.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/12-level.md).