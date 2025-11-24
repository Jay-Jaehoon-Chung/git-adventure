# Merging

## Goal
- Learn how to merge two different branches into one.

## 1. Merge branches
When merging, changes from two branches are combined into one. Let's go back to the style branch and merge it with main.

Command:  
```bash
git checkout style
git merge main
git hist --all
```

Result:  
```bash
$ git checkout style
# Switched to branch 'style'
$ git merge main
# Merge made by the 'recursive' strategy.
#  README.md | 1 +
#  1 file changed, 1 insertion(+)
#  create mode 100644 README.md
$ git hist --all
# *   deb31a1 2022-01-16 | Merge branch 'main' into style (HEAD -> style) [Gregor Biswanger]
# |\
# | * d99d725 2022-01-16 | Added README (main) [Gregor Biswanger]
# * | f810921 2022-01-16 | Updated index.html [Gregor Biswanger]
# * | 762149e 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# * | 8f84751 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# |/
# * 6f888c2 2022-01-16 | Added index.html. [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

By regularly merging the main branch into the style branch, you can incorporate all changes or modifications made on main to maintain compatibility with the style changes.

However, the commit graph becomes messy. Later, we will look at rebasing as an alternative to merging.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/25-level.md).