# Inside Git: The .git Directory

## Goal
- To learn more about the Git directory structure.

## 1. The .git Directory
It’s time to do some exploring. Starting from the project’s root directory…

Command on Windows:  
```bash
dir .git
```

Command on Unix/Mac:  
```bash
ls -C .git
```

Result:  
```bash
$ dir .git
# Datenträger in Laufwerk C: ist Local Disk
# Volumeseriennummer: CC1D-XXXX
# 
# Verzeichnis von C:\..\git-adventure\my-project\.git
# 
# 16.01.2022  21:22                18 COMMIT_EDITMSG
# 14.01.2022  22:13               130 config
# 14.01.2022  22:13                73 description
# 14.01.2022  23:45                 0 FETCH_HEAD
# 16.01.2022  13:44                21 HEAD
# 14.01.2022  22:13    <DIR>          hooks
# 16.01.2022  21:22               253 index
# 14.01.2022  22:13    <DIR>          info
# 14.01.2022  22:14    <DIR>          logs
# 16.01.2022  21:22    <DIR>          objects
# 16.01.2022  20:36                41 ORIG_HEAD
# 16.01.2022  20:44                46 packed-refs
# 14.01.2022  22:13    <DIR>          refs
# 8 File(s), 582 Bytes
# 5 Dir(s), 383.015.170.048 Bytes free
```

This is a special folder where all the internal Git data lives. Let’s explore it.

## 2. Object Database

Command on Windows:  
```cmd
dir .git\objects
```

Command on Unix/Mac:  
```bash
ls -C .git/objects
```

Result:  
```cmd
$ dir .git\objects
...
16.01.2022  21:22    <DIR>          .
16.01.2022  21:22    <DIR>          ..
16.01.2022  20:10    <DIR>          07
15.01.2022  17:38    <DIR>          10
16.01.2022  21:13    <DIR>          25
16.01.2022  20:10    <DIR>          2a
...
```

You should see many folders with two‑character names. These are the first two characters of the SHA‑1 hash of Git objects.

## 3. Inspect object database entries

Command on Windows:  
```cmd
dir .git\objects\<dir>
```

Command on Unix/Mac:  
```bash
ls -C .git/objects/<dir>
```

Result:
```cmd
$ dir .git\objects\07
...
16.01.2022  20:10    <DIR>          .
16.01.2022  20:10    <DIR>          ..
16.01.2022  20:10               189 6f96982647f77ff8f55fcfca324bb0740c1991
...
```

Inside each folder, you should see files whose names are 38 characters long. These are Git’s stored objects—compressed and encoded. Their content can’t be viewed directly.

## 4. Configuration File

Command:  
```cmd
code .git/config
```

Result:
```ini
[core]
    repositoryformatversion = 0
    filemode = false
    bare = false
    logallrefupdates = true
    symlinks = false
    ignorecase = true
```

This configuration file is created for each individual project. Entries here override settings in your global `.gitconfig` file.

## 5. Branches and Tags

Command on Windows:  
```cmd
dir .git\refs
dir .git\refs\heads
dir .git\refs\tags
code .git/refs/tags/v1
```

Command on Unix/Mac:  
```bash
ls .git/refs
ls .git/refs/heads
ls .git/refs/tags
code .git/refs/tags/v1
```

Result:
```cmd
$ dir .git\refs
...
16.01.2022  21:22    <DIR>          heads
16.01.2022  20:44    <DIR>          tags
...

$ dir .git\refs\heads
...
16.01.2022  21:22                41 main
...

$ dir .git\refs\tags
...
16.01.2022  01:18                41 v1
16.01.2022  01:22                41 v1-beta
...

$ code .git/refs/tags/v1
Contents: 5a9e60b06695c5cf6b84087828f1afaef75032af
```

Each file in the tags folder corresponds to a tag created with `git tag`. The file contains the hash of the commit the tag refers to.

The `heads` directory works the same way, except it stores branch references. Right now, you only have one branch: `main`.

## 6. HEAD File

Command:
```cmd
code .git/HEAD
Contents: ref: refs/heads/main
```

This file contains a reference to the currently checked‑out branch. At the moment, it should be the main branch.

## Complete the level
Go directly to the next level with the command `npm start` inside the Git Adventure directory (docs/19-level.md).