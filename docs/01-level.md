# Creating a Project

## Goals
To learn how to create a Git repository from scratch and check the status.

## 1. Create a “Hello World!” webpage
Start with an empty working directory. Create the directory named “my-project” in the root of the Git Adventure directory. Then create a hallo.html file inside it with the following content: `Hallo Welt!`.

Commands:  
```bash
mkdir my-project
cd my-project 
code hallo.html
```

hallo.html content:  
```html
Hallo Welt!
```

## 2. Create a repository
So you have a directory that contains a file. Run the `git init` command to create a Git repo from this directory.

Command:  
```bash
git init
```

Result:  
```bash
$ git init
# Initialized empty Git repository in ../git-adventure/my-project/.git/
```

## 3. Add the webpage to the repository
Now let’s add the webpage to the repository.

Command:  
```bash
git add hallo.html
git commit -m "First Commit"
```

You will see...

Result:  
```bash
$ git add hallo.html
$ git commit -m "First Commit"
# [main (root-commit) 911e8c9] First Commit
# 1 files changed, 1 insertions(+), 0 deletions(-)
# create mode 100644 hallo.html
```

## 4. Check the status of the repository
Use the `git status` command to check the current status of the repository.

Command:  
```bash
git status
```

You will see...

Result:  
```bash
$ git status  
# On branch main  
# nothing to commit (working directory clean)`
```

The command checks the status and reports that there is nothing to commit, which means that the repository stores the current state of the working directory and there are no changes to record.

We will use the `git status` command to monitor the status of both the working directory and the repository.

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/02-level.md).