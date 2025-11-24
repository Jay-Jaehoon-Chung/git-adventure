# Git Inside: Working Directly with Git Objects

## Goals
- Explore the structure of the object database.
- Use SHA1 hashes to navigate repository contents.

Let’s examine Git objects using a few tools.

## 1. Find the latest commit

Command:  
```bash
git hist --max-count=1
```

This command should find the most recent commit in the repository. The SHA1 hash will differ on your system, but you should see something like:

```bash
$ git hist --max-count=1
# * 6f888c2 2022-01-16 | Added index.html. (HEAD -> main) [Gregor Biswanger]
```

## 2. Display the latest commit
With the SHA1 hash from the commit above…

Command:  
```bash
git cat-file -t <hash>
git cat-file -p <hash>
```

I see…

Result:  
```bash
$ git cat-file -t 6f888c2
# commit
$ git cat-file -p 6f888c2
# tree 93f50a2de0f9f9ca5d40d3cd827688707560615b
# parent 4adf1a1d05f9a109cc9304ae3a73130d552c297b
# author Gregor Biswanger <gregor.biswanger@web-enliven.de> 1642364522 +0100
# committer Gregor Biswanger <gregor.biswanger@web-enliven.de> 1642364522 +0100
# 
# Added index.html.
```

**Note:** If you set aliases for `type` and `dump` as described in the Aliases lesson, you can use `git type` and `git dump` instead of typing these long commands.

This shows the commit object currently at the head of the main branch.

## 3. Search the Tree
We can display the tree referenced by the commit. This shows the top-level directory structure for that commit. Use the SHA1 hash from the *tree* line above.

Command:  
```bash
git cat-file -p <treehash>
```

Here is my tree…

Result:  
```bash
$ git cat-file -p 93f50a2
# 100644 blob 3fbf4a4e2f25d15c8e3fb452ed1f38736977890f    index.html
# 040000 tree 957e682bf8fe475a51286c22c05b5a3d66d8e893    lib
```

You can see the `index.html` file and the `lib` directory.

## 4. Display the lib directory

Command:  
```bash
git cat-file -p <libhash>
```

Here is my tree…

Result:  
```bash
$ git cat-file -p 957e682
# 100644 blob e1ee9cf3ff562fbd1db2c32c7fb0daf878776e38    hallo.html
```

That's the `hallo.html` file.

## 5. Display the hallo.html file

Command:  
```bash
git cat-file -p <hallohash>
```

Result:  
```bash
$ git cat-file -p e1ee9cf
# <!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
# <html>
#   <head>
#   </head>
#   <body>
#     <h1>Hello, World!</h1>
#   </body>
# </html>
```

There it is. Tree objects, commit objects, and blob objects are displayed directly from the Git repository. That’s all Git stores—trees, blobs, and commits.

## 6. Explore further
The Git repository can be explored manually. Try locating the original `hallo.html` file from the first commit using SHA1 references starting from the latest commit.

## Complete the level
Go to the next level using the `npm start` command inside the Git Adventure directory (docs/20-level.md).