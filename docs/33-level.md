# Fetching Changes

## Goal
- Learn how to pull changes from a remote repository.

Command:
```bash
cd ../cloned_my-project
git fetch
git hist --all
```

**NOTE:** We are now in the `cloned_my-project` repository.

Result:
```bash
$ git fetch
# remote: Enumerating objects: 5, done.
# remote: Counting objects: 100% (5/5), done.
# remote: Compressing objects: 100% (3/3), done.
# remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
# Unpacking objects: 100% (3/3), 373 bytes | 13.00 KiB/s, done.
# From C:/dev/git-adventure/my-project
#    0d4bc09..1f26579  main       -> origin/main

$ git hist --all
# * 1f26579 2022-01-18 | Changed README in original repo (origin/main, origin/HEAD) [Gregor Biswanger]
# * 0d4bc09 2022-01-16 | Updated index.html (HEAD -> main, origin/style) [Gregor Biswanger]
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

Right now, the repository contains all commits from the original repo; however, they are **not** integrated into the local branches of the cloned repository.

You will find the commit “Changed README in original repo” in the history.  
Notice that this commit contains both “origin/main” and “origin/HEAD”.

Now look at the commit “Updated index.html”.  
You will see that the local `main` branch still points exactly to this commit — not to the new commit we just fetched.

This tells us that the `git fetch` command retrieves new commits from the remote repo, but **does not merge them into the local branches**.

## 1. Check the README.md
We can see that the cloned README file has not changed.

Command:
```bash
code README.md
```

No changes, as we can see.

## Complete the level
Go directly to the next level with the `npm start` command inside the Git Adventure directory (docs/34-level.md).