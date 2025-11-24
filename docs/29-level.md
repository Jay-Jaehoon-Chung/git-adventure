# Multiple Repositories

## Goal
- Learn how to create copies of repositories.

So far, we have worked with only one Git repository. However, Git is excellent for working with multiple repositories. These additional repositories can be stored locally or accessed through a network connection.

In the next section, we will create a new repo named **“cloned_my-project”**. We will discuss how to move changes from one repo to another and how to deal with conflicts when working with two repositories.

For now, we will work with local repositories (stored on your local drive). Most of the information in this section also applies when working with multiple repos shared over a network.

**NOTE:** We will make changes in both copies of our repositories. Pay attention to which repository you are in at each step of the next lessons.

## 1. Go to your working directory

Go into the working directory and clone your `my-project` repository.

Command:  
```bash
cd ..
git clone my-project cloned_my-project
```

Result:  
```bash
$ cd ..
$ git clone my-project cloned_my-project
# Cloning into 'cloned_my-project'...
# done.
```

You should now have two repos in your working directory: the original `my-project` repo and the cloned repository named `cloned_my-project`.

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/29-level.md).