# Bare Repository

## Goal
- To learn how to create a bare repository.

A bare repository (a Git repository without a working directory) is typically needed for sharing.

## 1. Create a bare repository

Command:  
```bash
cd ..
git clone --bare my-project my-project.git
dir my-project.git
```

Result:  
```bash
$ cd ..
$ git clone --bare my-project my-project.git
# Cloning into bare repository 'my-project.git'...
# done.

$ dir my-project.git
# 18.01.2022  10:14    <DIR>          .
# 18.01.2022  10:14    <DIR>          ..
# 18.01.2022  10:14               193 config
# 18.01.2022  10:14                73 description
# 18.01.2022  10:14                21 HEAD
# 18.01.2022  10:14    <DIR>          hooks
# 18.01.2022  10:14    <DIR>          info
# 18.01.2022  10:14    <DIR>          objects
# 18.01.2022  10:14               274 packed-refs
# 18.01.2022  10:14    <DIR>          refs
```

Repositories that end in “.git” are typically bare. As you can see, there is no working directory in the `my-project.git` repository.  
It is essentially the same as the `.git` directory of a non-bare repository.

## Complete the level
Did you do everything correctly?  
Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/38-level.md).