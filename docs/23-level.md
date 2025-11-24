# Viewing the Different Branches

## Goal
- Learn how to display the different branches in the repository.

## 1. Show current branches
Now we have a repository with two different branches. To display branches and their differences, use the log command as follows.

Command:  
```bash
git hist --all
```

Result:  
```bash
$ git hist --all
# * d99d725 2022-01-16 | Added README (HEAD -> main) [Gregor Biswanger]
# | * f810921 2022-01-16 | Updated index.html (style) [Gregor Biswanger]
# | * 762149e 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# | * 8f84751 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# |/
# * 6f888c2 2022-01-16 | Added index.html. [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

We can see `--graph` from `git hist` in action. Adding the `--graph` option to `git log` constructs a commit tree using simple ASCII characters. We see both branches (style and main) and that the current branch main is at HEAD. The added index.html branch comes before both branches.

The `--all` flag ensures that we see all branches. By default, only the current branch is displayed.

## Complete the level
Go directly to the next level with the command `npm start` inside the Git Adventure directory (docs/24-level.md).