# Further Information on the Structure

## Goal
- Add another file to our repository.

## 1. Adding index.html
Let’s add an index.html file to the repository. The following file is perfect for this purpose.

index.html  
```html
<html>
  <body>
    <iframe src="lib/hallo.html" width="200" height="200" />
  </body>
</html>
```

Add the file and make a commit.

```bash
git add index.html
git commit -m "Added index.html."
```

When you now open index.html, you should see part of the hello page in a small window.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/18-level.md).