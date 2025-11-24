# Merging from the Main Branch

## Goal
- We kept our style branch up to date with main (using rebase), but now let’s merge the style branch changes back into main.

## 1. Merge style into main

Command:  
```bash
git checkout main
git merge style
```

Result:  
```bash
$ git checkout main
# Switched to branch 'main'

$ git merge style
# Updating d99d725..0d4bc09
# Fast-forward
#  index.html     | 3 +++
#  lib/hallo.html | 1 +
#  lib/style.css  | 3 +++
#  3 files changed, 7 insertions(+)
#  create mode 100644 lib/style.css
```

Since the last main commit is directly behind the last style commit, Git can fast‑forward by simply moving the branch pointer forward so that it points to the same commit as the style branch.

Fast-forward merges do not create conflicts.

## 2. Review the logs

Command:  
```bash
git hist
```

Result:  
```bash
$ git hist
# * 0d4bc09 2022-01-16 | Updated index.html (HEAD -> main, style) [Gregor Biswanger]
# * 462cbb5 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# * 5374e23 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# * d99d725 2022-01-16 | Added README [Gregor Biswanger]
# * 6f888c2 2022-01-16 | Added index.html. [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

Now style and main are identical.

## Complete the level
Did you do everything correctly? Check it using `npm start` inside the Git Adventure directory and unlock the next level (docs/29-level.md).