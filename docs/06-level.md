# History

## Goal
- To learn how to display the history of the project.

Retrieving a list of the changes made is a function of the `git log` command.

Command:  
```bash
git log
```

You will see...

Result:  
```bash
commit 5a9e60b06695c5cf6b84087828f1afaef75032af (HEAD -> main)
Author: Gregor Biswanger <gregor.biswanger@web-enliven.de>
Date:   Sat Jan 15 17:40:52 2022 +0100

    Added HTML header

commit d9352d1c7ba8bd0eceaa3a1e23440a5d3672d344
Author: Gregor Biswanger <gregor.biswanger@web-enliven.de>
Date:   Sat Jan 15 17:39:29 2022 +0100

    Added standard HTML page tags

commit 41b3c462b40e2d882683b0a9408a603e67109489
Author: Gregor Biswanger <gregor.biswanger@web-enliven.de>
Date:   Sat Jan 15 12:58:02 2022 +0100

    Added h1 tag

commit b617603b19fb6ef196ac33f5192297490b65d463
Author: Gregor Biswanger <gregor.biswanger@web-enliven.de>
Date:   Fri Jan 14 22:14:01 2022 +0100

    First Commit
```

Here is a list of all four commits to the repository that we have been able to make so far.

## 1. One-line history

You have full control over what the log displays. I like the one-line format:

Command:  
```bash
git log --pretty=oneline
```

You will see...

Result:  
```bash
5a9e60b06695c5cf6b84087828f1afaef75032af (HEAD -> main) Added HTML header
d9352d1c7ba8bd0eceaa3a1e23440a5d3672d344 Added standard HTML page tags
41b3c462b40e2d882683b0a9408a603e67109489 Added h1 tag
b617603b19fb6ef196ac33f5192297490b65d463 First Commit
```

## 2. Controlling the display of entries

There are many options to choose which entries appear in the log. Play around with the following parameters:

```bash
git log --pretty=oneline --max-count=2
git log --pretty=oneline --since="5 minutes ago"
git log --pretty=oneline --until="5 minutes ago"
git log --pretty=oneline --author=<your name>
git log --pretty=oneline --all
```

## 3. Getting fancy

This is what I use to check the changes made within the last week. I will add `--author=Gregor` if I only want to see the changes I made.

```bash
git log --all --pretty=format:"%h %cd %s (%an)" --since="7 days ago"
```

## 4. The ultimate log format

Over time, I found the following log format most suitable.

Command:  
```bash
git log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
```

Result:
```bash
* 5a9e60b 2022-01-15 | Added HTML header (HEAD -> main) [Gregor Biswanger]
* d9352d1 2022-01-15 | Added standard HTML page tags [Gregor Biswanger]
* 41b3c46 2022-01-15 | Added h1 tag [Gregor Biswanger]
* b617603 2022-01-14 | First Commit [Gregor Biswanger]
```

Let’s look at it in detail:

- `--pretty="..."` defines the output format.  
- `%h` is the abbreviated commit hash  
- `%d` commit decorations (e.g., branch heads or tags)  
- `%ad` is the commit date  
- `%s` is the comment  
- `%an` is the author's name  
- `--graph` tells Git to display the commit tree in the form of an ASCII graph layout  
- `--date=short` keeps the date format short and nice  

Every time you want to see a log, you would have to type a lot. Luckily, in the next lesson we will learn more about Git aliases.

## Complete the level
Go directly to the next level with the command `npm start` inside the Git Adventure directory (docs/07-level.md).