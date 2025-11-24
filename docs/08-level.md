# Retrieving Older Versions

## Goal
- To learn how you can check out a previous snapshot into the working directory.

Going back in history is very easy. The `checkout` command can copy any snapshot from the repo into the working directory.

## 1. Getting hashes for previous versions

Command:  
```bash
git hist
```

**Note:** In Level 7 we added `hist` as an alias.

Result:  
```bash
* 5a9e60b 2022-01-15 | Added HTML header (HEAD -> main) [Gregor Biswanger]
* d9352d1 2022-01-15 | Added standard HTML page tags [Gregor Biswanger]
* 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
* b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

Check the output and find the hash for the first commit. You will find it in the last line. Use the code (the first 7 characters are enough) in the following command. Then check the contents of the `hallo.html` file.

Command:  
```bash
git checkout <hash>
code hallo.html
```

**Note:** Many commands depend on hash values in the repository. Because my hash values differ from yours, replace the corresponding hash value for your repository every time you see `<hash>` or `<treehash>` in the command.

You will see...

Result:  
```bash
$ git checkout b617603
# Note: switching to 'b617603'.
# 
# You are in 'detached HEAD' state. You can look around, make experimental
# changes and commit them, and you can discard any commits you make in this
# state without impacting any branches by switching back to a branch.
# 
# If you want to create a new branch to retain commits you create, you may
# do so (now or later) by using -c with the switch command. Example:
# 
#   git switch -c <new-branch-name>
# 
# Or undo this operation with:
# 
#   git switch -
# 
# Turn off this advice by setting config variable advice.detachedHead to false
# 
# HEAD is now at b617603 First Commit
```

The output of the `checkout` command explains the situation completely. Older Git versions will complain that you are not on a local branch. But you don’t need to worry about that now.

Note that the contents of the `hallo.html` file are the default contents without HTML code.

## 2. Return to the latest version on the main branch

Command:  
```bash
git checkout main
code hallo.html
```

You will see...

Result:  
```bash
$ git checkout main
Previous HEAD position was b617603 First Commit
Switched to branch 'main'
```

“main” is the name of the standard branch. By checking out a branch by name, you go to its latest version.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/09-level.md).