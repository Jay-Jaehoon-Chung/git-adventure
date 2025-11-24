# Inspect the Cloned Repository

## Goal
Find information about branches in the remote repositories.

## 1. Viewing the cloned repository
Let’s take a look at our cloned repository.

Command:  
```bash
cd cloned_my-project
dir
```

Result:  
```bash
$ cd cloned_my-project
$ dir
# ...
# 17.01.2022  21:38    <DIR>          .
# 17.01.2022  21:38    <DIR>          ..
# 17.01.2022  21:38               199 index.html
# 17.01.2022  21:38    <DIR>          lib
# 17.01.2022  21:38                57 README.md
# ...
```

You see a list of all files in the top level of the original repository (README, index.html and lib).

## 2. The history of the cloned repository

Command:  
```bash
git hist --all
```

Result:  
```bash
$ git hist --all
# * 0d4bc09 2022-01-16 | Updated index.html (HEAD -> main, origin/style, origin/main, origin/HEAD) [Gregor Biswanger]
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

You see a list of all commits in the new repository, which matches the original repository.  
The only difference should be in the branch names.

## 3. Remote branches
You will find a main branch (HEAD) and some strange names in the history (origin/main, origin/style and origin/HEAD).  
But what exactly is **origin**?

Command:  
```bash
git remote
```

Result:  
```bash
$ git remote
# origin
```

We see that the cloned repository knows the default name of the remote repository.  
To get more information about the origin:

Command:  
```bash
git remote show origin
```

Result:  
```bash
$ git remote show origin
# * remote origin
#   Fetch URL: C:/dev/git-adventure/my-project
#   Push  URL: C:/dev/git-adventure/my-project
#   HEAD branch: main
#   Remote branches:
#     main  tracked
#     style tracked
#   Local branch configured for 'git pull':
#     main merges with remote main
#   Local ref configured for 'git push':
#     main pushes to main (up to date)
```

We can see that the “origin” of the remote repository is the original `my-project` repo.  
Remote repositories are normally stored on another computer or a central server,  
but as we see, they can also point to a repository on the same machine.

The name **origin** is not special, but it is conventionally used for the primary centralized repository (if one exists).

## Complete the level
Go directly to the next level using the `npm start` command inside the Git Adventure directory (docs/31-level.md).