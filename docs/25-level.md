# Creating a Conflict

## Goal
- Create a conflict of changes on the main branch.

## 1. Return to main and create conflicts
Return to the main branch and make the following changes:

Command:  
```bash
git checkout main
```

lib/hallo.html:
```html
<!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
<html>
  <head>
      <!-- no style -->
  </head>
  <body>
    <h1>Hello, World! Life is great!</h1>
  </body>
</html>
```

Command:  
```bash
git add lib/hallo.html
git commit -m "Life is great!"
```

(**Warning:** Make sure you use single quotes to avoid issues with bash and the exclamation mark.)

## 2. View branches

Command:  
```bash
git hist --all
```

Result:  
```bash
$ git hist --all
# * 080ed40 2022-01-16 | Life is great! (HEAD -> main) [Gregor Biswanger]
# | *   deb31a1 2022-01-16 | Merge branch 'main' into style (style) [Gregor Biswanger]
# | |\
# | |/
# |/|
# * | d99d725 2022-01-16 | Added README [Gregor Biswanger]
# | * f810921 2022-01-16 | Updated index.html [Gregor Biswanger]
# | * 762149e 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# | * 8f84751 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# |/
# * 6f888c2 2022-01-16 | Added index.html. [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# :...skipping...
# * 080ed40 2022-01-16 | Life is great! (HEAD -> main) [Gregor Biswanger]
# | *   deb31a1 2022-01-16 | Merge branch 'main' into style (style) [Gregor Biswanger]
# | |\
# | |/
# |/|
# * | d99d725 2022-01-16 | Added README [Gregor Biswanger]
# | * f810921 2022-01-16 | Updated index.html [Gregor Biswanger]
# | * 762149e 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# | * 8f84751 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# |/
# * 6f888c2 2022-01-16 | Added index.html. [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

After the added README commit, the main branch was merged into the style branch, but there is an additional main commit that has not been merged back into the style branch.

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/26-level.md).