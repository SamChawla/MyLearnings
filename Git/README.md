# Getting Started with Github

- [Getting Started with Github](#getting-started-with-github)
  - [What is Git and Github?](#what-is-git-and-github)
  - [Installing Git](#installing-git)
  - [Git Commands](#git-commands)
    - [Config Commands](#config-commands)
    - [Other Commands](#other-commands)
  - [Creating a new repository on github](#creating-a-new-repository-on-github)
  - [Common Queries](#common-queries)
  - [References](#references)

## What is Git and Github?

## Installing Git

You can download and install git using [git-scm](https://git-scm.com/downloads) for different OS

## Git Commands

### Config Commands

|      Command     |   Description   |    Example   |
|:------------------|:-----------------|:--------------|
| `git config --global user.name <name>`|Define the author name to be used for all commits by the current user (Remove global if you need to set only for the current repo)| `git config user.name "Sumit"`|
| `git config --global user.username <username>`|Define the author username to be used for all commits by the current user (Remove global if you need to set only for the current repo)| `git config user.username "SamChawla"`|
| `git config --global user.email <email>`|Define the author email to be used for all commits by the current user (Remove global if you need to set only for the current repo)| `git config user.email "er.sumit.s.chawla@gmail.com"`|

### Other Commands

|      Command     |   Description   |    Example   |
|:------------------|:-----------------|:--------------|
| `git init <directory>` | Create empty Git repo in specified directory, uses current directory if directory not passed | `git init` |
| `git status` | List staged, unstaged, and untracked files | `git status` |
| `git add <filename>` | Stage all changes in `filename` for the next commit. (Use . to add all the files) | `git add sample.txt` |
| `git commit` | Commit the staged snapshot, open text editor for message (use `-m "message"` to add message)| `git commit -m "sample.txt file added"` |
| `git log` | Display the entire commit history using the default format (use `--oneline` to display commit history in single line)| `git log` |
| `git reset <commit>` | Move the current branch tip backward to `commit`, reset the staging area to match, but leave the working directory alone. | `git reset` |
| `git stash` | Stash the changes in a dirty working directory away (use `save` to save it with a name, `pop` to pop the last stash, `clear` to clear stash)| `git stash save "local settings"` |  

## Creating a new repository on github

## Common Queries

- [How to revert to the previous commit?](https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit)

## References

- [Complete Git and GitHub Tutorial by Kunal Kushwaha](https://youtu.be/apGV9Kg7ics)
- [Atlassian Git CheatSheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
- [Learn Git Branching](https://learngitbranching.js.org/)
