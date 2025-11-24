# Navigating Branches

## Goals
- To learn how to navigate between repository branches.

Now your project has two branches:

Command:  
```bash
git hist --all
```

Result:
```bash
$ git hist --all
# * f810921 2022-01-16 | Updated index.html (HEAD -> style) [Gregor Biswanger]
# * 762149e 2022-01-16 | Hallo uses style.css [Gregor Biswanger]
# * 8f84751 2022-01-16 | Added css stylesheet [Gregor Biswanger]
# * 6f888c2 2022-01-16 | Added index.html. (main) [Gregor Biswanger]
# * 4adf1a1 2022-01-16 | Moved hallo.html to lib [Gregor Biswanger]
# * e9c95d3 2022-01-16 | Add an author/email comment [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

## 1. Switch to the main branch

To switch between branches, simply use the `git checkout` command.

Command:  
```bash
git checkout main
code lib/hallo.html
```

Result:  
```bash
$ git checkout main
# Switched to branch 'main'
$ code lib/hallo.html
# <!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
# <html>
#   <head>
#   </head>
#   <body>
#     <h1>Hello, World!</h1>
#   </body>
# </html>
```

Now we are on the **main branch**. You can confirm this because the `hallo.html` file does not use styles from `style.css`.

## 2. Switch back to the style branch

Command:  
```bash
git checkout style
code lib/hallo.html
```

Result:  
```bash
$ git checkout style
# Switched to branch 'style'
$ code lib/hallo.html
# <!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
# <html>
#   <head>
#       <link type="text/css" rel="stylesheet" media="all" href="style.css" />
#   </head>
#   <body>
#     <h1>Hello, World!</h1>
#   </body>
# </html>
```

We are now back on the **style branch**, which you can see because `hallo.html` loads the `style.css` stylesheet.

## Complete the level
Did you do everything correctly? Check using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/22-level.md).