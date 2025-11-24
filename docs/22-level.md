# Changes on the Main Branch

## Goal
- To learn how to work with multiple branches that have different (sometimes conflicting) changes.

While you were editing the style branch, someone decided to change the main branch. They added a README file.

## 1. Create README.md file on the main branch

Command:  
```bash
git checkout main
echo This is the Hello World example from the git tutorial. > README.md
git add README.md
git commit -m "Added README"
```

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/23-level.md).