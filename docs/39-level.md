# Submitting Changes

## Goal
- To learn how to submit changes to the remote repository.

Since a clean repository is normally shared on a network server, we need to send our changes to other repositories. First, create a change to send. Edit the README.md file and make a commit.

README.md:
```
This is the Hello World example from the Git workshop.

(Changed in the original and pushed to shared.)
```

Command:  
```bash
git checkout main
git add README.md
git commit -m "Added shared comment to readme"
```

Now send the change to the shared repository.

Command:  
```bash
git push shared main
```

The shared repository is the one that receives the changes we send. (Remember that we added it as a remote repository in the previous lesson.)

Result:  
```bash
$ git push shared main
# Enumerating objects: 5, done.
# Counting objects: 100% (5/5), done.
# Delta compression using up to 8 threads
# Compressing objects: 100% (3/3), done.
# Writing objects: 100% (3/3), 427 bytes | 427.00 KiB/s, done.
# Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
# To ../my-project.git
#    1f26579..4d3a273  main -> main
```

**Note:** We had to explicitly specify the main branch in order to submit the changes. It can be configured to do this automatically, but I always forget the command.

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git-Adventure directory and unlock the next level (docs/40-level.md).