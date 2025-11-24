# Aliases

## Goal
- To learn how to set up aliases and shortcuts for Git commands.

## 1. General aliases

For Windows users:  
```bash
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
git config --global alias.type "cat-file -t"
git config --global alias.dump "cat-file -p"
```

For Unix/Mac users:  
`git status`, `git add`, `git commit`, and `git checkout` are common commands, so it's a good idea to create shortcuts for them.

Add the following to the .gitconfig file in your $HOME directory:

```ini
[alias]
  co = checkout
  ci = commit
  st = status
  br = branch
  hist = log --pretty=format:"%h %ad | %s%d [%an]" --graph --date=short
  type = cat-file -t
  dump = cat-file -p
```

We have already talked about commit and status commands. In the previous lesson, we covered the `log` command, and we will learn about the `checkout` command very soon.

The most important thing you can learn from this lesson is that you can type `git st` anywhere you could type `git status`. The best part is that the `git hist` command helps you avoid typing the really long `log` command.

Go ahead and try using the new commands.

### Tip
There are some fun aliases in the community that you can adopt directly. For example, [Git in Bavarian](https://github.com/danielauener/git-auf-deutsch/blob/master/README-bayerisch.md). The `git init` command would then be `git ofanga`.

## 2. Define the hist alias in the .gitconfig file

For the most part, I will continue typing the full command in this guide. The only exception is that I will use the hist alias defined above when I need to look at the Git log. Make sure you have a hist alias in your .gitconfig file before continuing.

## 3. Type and Dump
We added a couple of aliases for commands we haven’t discussed yet. We will talk about the `git branch` command very soon, and the `git cat-file` command is useful for exploring Git.

## 4. Command aliases (optional)
If your shell supports aliases or shortcuts, you can add aliases at that level as well. I use:

```bash
alias gs="git status "
alias ga="git add "
alias gb="git branch "
alias gc="git commit "
alias gd="git diff "
alias gco="git checkout "
alias gk="gitk --all&"
alias gx="gitx --all"

alias got="git "
alias get="git "
```

The `gco` shortcut for `git checkout` is very useful, so I can type:

```bash
gco <branch>
```

to check out a specific branch.

I also often mistype `git` as `get` or `got`, so I created aliases for those as well.

## Complete the level
Go directly to the next level with the command `npm start` inside the Git Adventure directory (docs/08-level.md).