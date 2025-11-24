# Canceling Commits

## Goal
- How to undo commits from the local repository.

## 1. Canceling commits
Sometimes you realize that the new commits are wrong and you want to cancel them. There are several ways to solve the problem, and we will use the safest one.

To cancel the commit, we create a new commit and revert the unwanted changes.

## 2. Edit the file and make a commit
Replace `hallo.html` with the following content:

```html
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <!-- This is an unwanted but committed change -->
  </body>
</html>
```

Command:  
```bash
git add hallo.html
git commit -m "Oops, we didn't want this commit"
```

## 3. Make a commit that discards previous changes
To cancel the commit, we need to create a commit that deletes the changes saved by an unwanted commit.

Command:  
```bash
git revert HEAD
```

Go to the editor, where you can edit the default commit message or leave it unchanged. Save and close the file.

You will see...

Result:  
```bash
$ git revert HEAD --no-edit
# [main 45fa96b] Revert "Oops, we didn't want this commit"
# 1 files changed, 1 insertions(+), 1 deletions(-)
```

Since we canceled the last commit, we can use `HEAD` as the argument for the cancellation. We can revert any commit in the history by referencing its hash value.

**Note:** The `--no-edit` parameter can be ignored. It was only necessary to generate the output data without opening the editor.

## 4. Check the log
Checking the log shows the unwanted reverts and commits in our repository.

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

This technique can be applied to any commit (although conflicts may occur). It can even be used safely in public branches of remote repositories.

## Complete the level
Did you do everything correctly? Check it with the command `npm start` inside the Git Adventure directory and unlock the next level (docs/13-level.md).