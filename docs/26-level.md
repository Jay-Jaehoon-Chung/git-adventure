# Resolving Conflicts

## Goal
- Learn how to resolve merge conflicts.

## 1. Merge the main branch into style
Let’s return to the style branch and merge it with the new main branch.

Command:  
```bash
git checkout style
git merge main
```

Result:  
```bash
$ git checkout style
# Switched to branch 'style'
$ git merge main
# Auto-merging lib/hallo.html
# CONFLICT (content): Merge conflict in lib/hallo.html
# Automatic merge failed; fix conflicts and then commit the result.
```

If you open `lib/hallo.html`, you will see:

```html
<html>
  <head>
<<<<<<< HEAD
      <link type="text/css" rel="stylesheet" media="all" href="style.css" />
=======
      <!-- no style -->
>>>>>>> main
  </head>
  <body>
    <h1>Hello, World! Life is great!</h1>
  </body>
</html>
```

The first section is the version from **HEAD** (your current branch, style).  
The second section is the version from the **main** branch.

## 2. Resolve the conflict
You must resolve the conflict manually. Edit `lib/hallo.html` to produce the following result:

```html
<!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
<html>
  <head>
    <link type="text/css" rel="stylesheet" media="all" href="style.css" />
  </head>
  <body>
    <h1>Hello, World! Life is great!</h1>
  </body>
</html>
```

## 3. Commit the conflict resolution

Command:  
```bash
git add lib/hallo.html
git commit -m "Merged main fixed conflict."
```

Result:  
```bash
$ git add lib/hallo.html
$ git commit -m "Merged main fixed conflict."
# [style 0e4ed00] Merged main fixed conflict.
```

## 4. Advanced merging
Git does not include graphical merge tools, but it supports any third-party merge tool (for example, Visual Studio Code).

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/27-level.md).