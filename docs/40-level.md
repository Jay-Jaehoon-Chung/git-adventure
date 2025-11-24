# Pulling Shared Changes

## Goal
- Learn how to pull changes from the shared repository.

Quickly switch to the cloned repository and pull the changes that were just sent to the shared repository.

Command:
```bash
cd ..\cloned_my-project
```

**Note:** We are now in the `cloned_my-project` repository.

Continue with...

Command:
```bash
git remote add shared ../my-project.git
git branch --track shared main
git pull shared main
code README.md
```

## Complete the level
Did you do everything correctly?  
Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/41-level.md).