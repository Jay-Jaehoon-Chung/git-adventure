# Changing Commits

## Goal
- To learn how to modify an existing commit.

## 1. Modify the webpage and commit it
Add an author comment to the page.

```html
<!-- Author: Gregor Biswanger -->
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

Command:  
```bash
git add hallo.html
git commit -m "Add an author comment"
```

## 2. Oops... The email address is required
After making a commit, you realize that every good comment should include the author’s email address. Edit the Hello page to provide an email.

```html
<!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
<html>
  <head>
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

## 3. Modify the previous commit
We do not want to create another commit just to add the email address. Let’s modify the previous commit and add the email address.

Command:  
```bash
git add hallo.html
git commit --amend -m "Add an author/email comment"
```

Result:  
```bash
$ git add hallo.html
$ git commit --amend -m "Add an author/email comment"
# [main e9c95d3] Add an author/email comment
#  Date: Sun Jan 16 20:57:50 2022 +0100
#  1 file changed, 1 insertion(+)
```

## 4. View history

Command:  
```bash
git hist
```

Result:  
```bash
$ git hist
# * e9c95d3 2022-01-16 | Add an author/email comment (HEAD -> main) [Gregor Biswanger]
# * 5a9e60b 2022-01-15 | Added HTML header (tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

The new “Author/Email” commit replaces the original “Author” commit. The same effect could be achieved by resetting the last commit on the branch and committing the new changes again.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/16-level.md).