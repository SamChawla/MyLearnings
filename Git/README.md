# Getting Started with Github

- [Getting Started with Github](#getting-started-with-github)
  - [What is Git and Github?](#what-is-git-and-github)
  - [Installing Git](#installing-git)
  - [Git Commands](#git-commands)
    - [Config Commands](#config-commands)
    - [Other Commands](#other-commands)
  - [Creating a new repository on github](#creating-a-new-repository-on-github)
    - [create a new repository on the command line](#create-a-new-repository-on-the-command-line)
    - [push an existing repository from the command line](#push-an-existing-repository-from-the-command-line)
  - [What are branches?](#what-are-branches)
  - [Working with Existing Projects](#working-with-existing-projects)
    - [Sync your forked repo with the main repo](#sync-your-forked-repo-with-the-main-repo)
  - [Squash using rebase](#squash-using-rebase)
  - [Merge v/s Rebase](#merge-vs-rebase)
  - [Cherry-Picking](#cherry-picking)
  - [Starring and Following](#starring-and-following)
  - [Common Queries](#common-queries)
  - [Things to Remember](#things-to-remember)
  - [References](#references)

***

## What is Git and Github?

- **GIT and Github** are not same.
- Git is a VCS or Version Control System which tracks code changes over a period of time whereas Github is a hosting platform service layered over GIT for tracking code changes but on cloud. Other hosting platforms are Gitlab, Bitbucket, AWS CodeCommit to name a few.

***

## Installing Git

You can download and install git using [git-scm](https://git-scm.com/downloads) for different OS

***

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
| `git add <filename>` | Stage all changes in `filename` for the next commit. (Use . to add all the files, `<filename> -p` to add file partially) | `git add sample.txt` |
| `git commit` | Commit the staged snapshot, open text editor for message (use `-m "message"` to add message)| `git commit -m "sample.txt file added"` |
| `git log` | Display the entire commit history using the default format (use `--oneline` to display commit history in single line)| `git log` |
| `git reset <commit>` | Move the current branch tip backward to `commit`, reset the staging area to match, but leave the working directory alone. | `git reset` |
| `git stash` | Stash the changes in a dirty working directory away (use `save` to save it with a name, `pop` to pop the last stash, `clear` to clear stash)| `git stash save "local settings"` | 
| `git branch` | List all of the branches in your repo. Add a `branch` argument to create a new branch with the name `branch`| `git branch` |
| `git checkout -b <branch>` | Create and check out a new branch named `branch`. Drop the -b flag to checkout an existing branch.| `git branch -b "git-notes"` | 
| `git merge <branch>` | Merge `branch` into the current branch| `git merge master` |

***

## Creating a new repository on github

  1. Go to [Github](http://github.com/) <br>
  ![Github Home Page](https://user-images.githubusercontent.com/7588716/187735346-20ea7590-35f6-4e20-b6a2-fa438c7bf88d.png)

  2. Click on New <br>
  ![New Icon](https://user-images.githubusercontent.com/7588716/187735900-efd97cc5-2fe9-46d8-ad2a-7a872a93ba5e.png)

  3. Provide a repository name and keep other details as default<br>
  ![Repo Name](https://user-images.githubusercontent.com/7588716/187737116-2a4ae1a9-21d2-40d5-9543-034f87c2a5dd.png)

  4. Your repo name would be like `https://github.com/<Username>/<RepoName>.git`

### create a new repository on the command line

  ```bash
  echo "# LearnersGuide" >> README.md
  git init
  git add README.md
  git commit -m "first commit"
  git branch -M master
  git remote add origin https://github.com/SamChawla/LearnersGuide.git
  git push -u origin master
  ```

### push an existing repository from the command line

  ```bash
  git remote add origin https://github.com/<Username>/<RepoName>.git
  git branch -M master
  git push -u origin master
  ```

***

## What are branches?

- Branches in Git are incredibly lightweight as well. They are simply pointers to a specific commit -- nothing more.
- Because there is no storage / memory overhead with making many branches, it's easier to logically divide up your work than have big beefy branches.
- Any new feature that we are working on or any bug fixes should be done on new branch and then they are merged to master once they are finalized and approved

***

## Working with Existing Projects

1. Fork Repo <br>
![Fork](https://user-images.githubusercontent.com/7588716/187745723-339b7d1a-b969-46bb-b538-b8769b4b5c73.png)

2. Clone repo and then Set original repo url as Upstream
`git remote add upstream https://github.com/<Username>/<RepoName>.git`

3. Check if it is added properly: `git remote -v` (Origin is your repo, upstream is where you forked from)

4. Do the changes in your repo, add commit, and push your changes.

5. You will see an option, once you push your changes `Compare and Pull Request`<br>
![PR](https://user-images.githubusercontent.com/7588716/187747418-0d19ac94-2276-4fd7-8fe6-8f383261a5e9.png)

6. Add Title, description and then click on `Create Pull Request`

### Sync your forked repo with the main repo

- Fetch all the changes using command: `git fetch --all --prune`
- Checkout main branch and reset it to main branch of upstream: `git reset --hard upstream/master`
- Push changes: `git push origin master`

***

## Squash using rebase

- copy the `commit_sha` and write `git rebase -i <commit_sha>` to interactivaely update it.
- An editor would open up, use `pick` or `s`(squash) as per your requirement, save and then add updated commit message.

***

## Merge v/s Rebase

- Git Merge is a technique that is used to include the changes from one branch to the other branch and keeps the logs of the branches intact.
- Git Rebase is similar to git merge, but the logs are modified after merge in this technique. Git rebase was introduced to overcome the limitation of merging, i.e., to make logs of repository history look linear.

 <p align="center">
  <img src="https://user-images.githubusercontent.com/7588716/187976379-979eba7a-0036-4e32-afee-4f4a15412dcc.png" height="300px" width="600px">
</p>

***

## Cherry-Picking

- It is used when you want to pick a commit from some other branch to your branch that could be a bug fix or anything else
  1. Copy the `<commit_sha>` that you want to cherry pick.
  2. checkout branch on which you want this commit.
  3. use `git cherry-pick <commit_sha>` to cherry pick that commit. If you want to change commit message, you can use `git cherry-pick --no-commit <commit_sha>` and then commit the message.

***

## Starring and Following

- **GITHUB IS A SOCIAL NETWORK FOR CODERS**
- You can **Star** the repositories you find interesting to come back to that repo later.
- You can also **Follow** the people on Github, if you want to track their progress and activities.

## Common Queries

- [How to revert to the previous commit?](https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit)
- [When to use rebase instead of merge?](https://stackoverflow.com/questions/804115/when-do-you-use-git-rebase-instead-of-git-merge)

***

## Things to Remember

- Whenever you do git reset to some other commit, you will need to force push using `git push origin <branch> -f`

***

## References

- [Complete Git and GitHub Tutorial by Kunal Kushwaha](https://youtu.be/apGV9Kg7ics)
- [Advanced Github Workshop](https://www.youtube.com/watch?v=38xZop53BFA)
- [Atlassian Git CheatSheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
- [Github Cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Learn Git Branching](https://learngitbranching.js.org/)
- [Writing conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Git Merge vs Rebase](https://www.edureka.co/blog/git-rebase-vs-merge/)
