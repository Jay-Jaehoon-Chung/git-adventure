# Removing the oops Tag

## Goal
- Removing the oops tag (cleanup)

## 1. Removing the oops tag
The oops tag has fulfilled its purpose. Let's remove this tag and allow the garbage collector to delete the referenced commit.

Command:  
```bash
git tag -d oops
git hist --all
```

Result:
```bash
$ git tag -d oops
# Deleted tag 'oops' (was 744ff5f)

$ git hist --all
# * 5a9e60b 2022-01-15 | Added HTML header (HEAD -> main, tag: v1) [Gregor Biswanger]
# * d9352d1 2022-01-15 | Added standard HTML page tags (tag: v1-beta) [Gregor Biswanger]
# * 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
# * b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

The oops tag no longer appears in the repository.

## Complete the level
Did you do everything correctly? Check it with the `npm start` command inside the Git Adventure directory and unlock the next level (docs/15-level.md).