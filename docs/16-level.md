# Moving Files

## Goal
- To learn how to move a file within the repository.

## 1. Move the file hallo.html into the lib directory
Now we create the structure in our repository. Let's move the page into the lib directory.

Command:  
```bash
mkdir lib
git mv hallo.html lib
git status
```

Result:
```bash
$ mkdir lib
$ git mv hallo.html lib
$ git status
# On branch main
# Changes to be committed:
#  (use "git restore --staged <file>..." to unstage)
#        renamed:    hallo.html -> lib/hallo.html
```

By moving files with Git, we inform Git of two things:

1. The `hallo.html` file was deleted.  
2. The `lib/hallo.html` file was created.

Both facts are immediately staged and ready for a commit. The Git status command reports that the file has been moved.

## 2. Another way to move files

A positive aspect of Git is that you don’t have to think about version control. What would happen if we used the operating system’s command line instead of the Git command to move files?

The following commands have the same result as those used above, but they require a little more work.

We can also do:
```bash
mkdir lib
mv hallo.html lib
git add lib/hallo.html
git rm hallo.html
```

## 3. Commit the new directory
Let’s record this move.

Command:  
```bash
git commit -m "Moved hallo.html to lib"
```

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/17-level.md).