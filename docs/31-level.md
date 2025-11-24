# Remote branches

## Goal
- Learn more about local and remote branches.

Let’s take a look at the branches in our cloned repository.

Command:  
```bash
git branch
```

Result:  
```bash
$ git branch
# * main
```

As we can see, only the main branch is listed.  
Where is the style branch?  
`git branch` lists only the **local** branches by default.

## 1. List all remote branches

Try the following command to show all branches:

Command:  
```bash
git branch -a
```

Result:  
```bash
$ git branch -a
# * main
#   remotes/origin/HEAD -> origin/main
#   remotes/origin/main
#   remotes/origin/style
```

Git lists all branches from the original repository, but the remote branches are **not** treated as local ones.  
If we need our own local `style` branch, we must create it ourselves.

## Complete the level
Go directly to the next level using the `npm start` command inside the Git Adventure directory (docs/32-level.md).