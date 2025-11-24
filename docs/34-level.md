# Merging Fetched Changes

## Goal
- How to apply fetched changes to the current branch.

## 1. Merge the fetched changes into the local main branch

Command:  
```bash
git merge origin/main
```

Result:  
```bash
$ git merge origin/main
# Updating 0d4bc09..1f26579
# Fast-forward
#  README.md | 2 +-
#  1 file changed, 1 insertion(+), 1 deletion(-)
```

## 2. Check README.md again
Now we should see the changes.

Command:  
```bash
code README.md
```

## Complete the level
Did you do everything correctly?  
Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/35-level.md).