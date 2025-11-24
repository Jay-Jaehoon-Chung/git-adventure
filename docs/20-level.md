# Create a Branch

## Goal
- Learn how to create a local branch in the repository.

It is time to make our Hello World more expressive. Since this may take some time, it is best to move these changes into a new branch to isolate them from changes on the main branch.

## 1. Create a branch
Let’s call our new branch "style".

Command:  
```bash
git checkout -b style
git status
```

**Note:** `git checkout -b <branch name>` is a shortcut for  
`git branch <branch name>` followed by `git checkout <branch name>`.

Notice that the `git status` command reports that you are now on the style branch.

## 2. Add the style.css file

Command:  
```bash
code lib/style.css
```

style.css:  
```css
h1 {
  color: red;
}
```

Command:  
```bash
git add lib/style.css
git commit -m "Added css stylesheet"
```

## 3. Modify the main page

Update the `hallo.html` file to load the style.css file.

hallo.html:  
```html
<!-- Author: Gregor Biswanger (gregor.biswanger@web-enliven.de) -->
<html>
  <head>
      <link type="text/css" rel="stylesheet" media="all" href="style.css" />
  </head>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
```

Command:  
```bash
git add lib/hallo.html
git commit -m "Hallo uses style.css"
```

## 4. Update index.html
Update the `index.html` file to load the style.css file.

index.html:  
```html
<html>
  <head>
    <link type="text/css" rel="stylesheet" media="all" href="lib/style.css" />
  </head>
  <body>
    <iframe src="lib/hallo.html" width="200" height="200" />
  </body>
</html>
```

Command:  
```bash
git add index.html
git commit -m "Updated index.html"
```

## Complete the level
Did you do everything correctly? Check it using the `npm start` command inside the Git Adventure directory and unlock the next level (docs/21-level.md).