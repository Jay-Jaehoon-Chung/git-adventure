# Adding a Tracking Branch

## Goal
- To learn how to add a local branch that tracks a remote branch.

Branches that begin with `remotes/origin` belong to the original repository. Note that it no longer has a style branch locally, but it knows that it existed in the original repository.

## 1. Add a local branch that tracks the remote branch

Command:  
```bash
git branch --track style origin/style
git branch
git hist --max-count=2
```

Result:  
```bash
$ git branch --track style origin/style
# Branch 'style' set up to track remote branch 'style' from 'origin'.

$ git branch
# * main
#   style

$ git hist --max-count=2
# * 1f26579 2022-01-18 | Changed README in original repo (HEAD -> main, origin/main, origin/HEAD) [Gregor Biswanger]
# * 0d4bc09 2022-01-16 | Updated index.html (origin/style, style) [Gregor Biswanger]
```

Now we can see the style branch in the branch list and the log.

## Complete the level
Did you do everything correctly?  
Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/37-level.md).