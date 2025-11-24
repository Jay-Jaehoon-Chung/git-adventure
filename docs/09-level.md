# Tagging

## Goal
- To learn how to tag commits for future reference.

Let’s call the current version of the Hello World program version 1 (v1).

## 1. Create a tag for the first version

Command:  
```bash
git tag v1
```

Now the current version of the page is labeled v1.

## 2. Tags for earlier versions
Let’s tag the version before the current one with the name `v1-beta`. First, we check out the previous version. Instead of looking up the hash, we use the notation `^`, which means **“the parent of v1.”**

If the notation `v1^` causes problems, try using `v1~1` to refer to the same version. This notation means **“the first version before v1.”**

Command:  
```bash
git checkout v1^
code hallo.html
```

Result:  
```bash
$ git checkout v1^
More? ~1
# Note: switching to 'v1~1'.
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
# HEAD is now at d9352d1 Added standard HTML page tags
```

This is the version with the tags `<html>` and `<body>`, but without `<head>`. Let’s assume this is the v1-beta version.

Command:  
```bash
git tag v1-beta
```

## 3. Checking out using the tag name
Now try checking out between the two tagged versions.

Command:  
```bash
git checkout v1
git checkout v1-beta
```

Result:  
```bash
$ git checkout v1
# Previous HEAD position was d9352d1 Added standard HTML page tags
# HEAD is now at 5a9e60b Added HTML header
$ git checkout v1-beta
# Previous HEAD position was 5a9e60b Added HTML header
# HEAD is now at d9352d1 Added standard HTML page tags
```

## 4. Viewing tags with the tag command
You can show the available tags with the `git tag` command.

Command:  
```bash
git tag
```

Result:  
```bash
$ git tag
# v1
# v1-beta
```

## 5. Viewing tags in the history
You can also search the log for tags.

Command:  
```bash
git hist main --all
```

Result:  
```bash
* 5a9e60b 2022-01-15 | Added HTML header (tag: v1, main) [Gregor Biswanger]
* d9352d1 2022-01-15 | Added standard HTML page tags (HEAD, tag: v1-beta) [Gregor Biswanger]
* 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
* b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

You can see tags (`v1` and `v1-beta`) along with the name of the branch (main) in the log. The HEAD points to the commit you checked out (currently v1-beta).

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/10-level.md).