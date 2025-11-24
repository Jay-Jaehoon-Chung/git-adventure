# Relocating as an Alternative to Merging

## Goal
- To learn the difference between relocating (rebase) and merging.

## 1. Resetting the style branch
Reset the style branch back to the commit before it was merged with main.

Command:  
```bash
git checkout style
git hist
```

Use the hash of the last commit before the merge:

Command:  
```bash
git reset --hard <hash>
```

## 2. Check the branch
Command:  
```bash
git hist --all
```

## 3. Resetting the main branch
Return the main branch to the commit before the conflicting change to prepare for a clean rebase.

Command:  
```bash
git checkout main
git hist
git reset --hard <hash>
git hist --all
```

## 4. Rebase
Move all commits from the style branch onto the updated main branch.

Command:  
```bash
git checkout style
git rebase main
git hist
```

## 5. Merging vs. Rebasing
- **Merge** keeps the full branching history.
- **Rebase** rewrites history for a cleaner, linear commit chain.
- Use **merge** for shared/public branches.
- Use **rebase** for private/local branches.

## Complete the level
Did you do everything correctly? Check using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/28-level.md).