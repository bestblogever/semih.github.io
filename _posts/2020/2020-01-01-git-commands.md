---
layout: post
title: "Git Commands"
date: 2020-01-02 02:38:19 Thursday
author: semih
comments: true
categories: [git]
tags: [git, source control management, scm]
---
We have numerous sources and manage it using source control management(SCM) DevOps tools like Git, SubVersion, CVS, TFS, ClearCase, Mercurial. Git is a modern distributed version control system. I am going to tell you most useful Git commands and why we need to use those commands. I will explain each step with examples.
[========]

| Git Command Line Tools is consistent | | There are 3 states of Git. |
| ------------ |-----| ------------ |
| - Terminal on Mac/Linux  |  |  - Working directory |
| - Git Bash on Windows | | - Staging area (pre-commit holding area) |
|   |  | - Commit (git repository, history) |

![image](/assets/images/basic-git-workflow-lifecycle.png)

```shell
~ $ git version
   git version 2.17.2
```
git global user name and email configuration
```shell
~ $ git config --global user.name "username"
~ $ git config --global user.email "email"
~ $ git config --global --list
```
### Demo App
Now let's make a demo app and execute the first commands in git. At first, create a repository in Github with the name of "github-repo". Then, clone this repository into your local workspace folder.

Clone the remote repository into your local folder.
```shell
~ $ git clone https://github.com/semih/github-demo.git
~ $ cd github-demo/
```
Add README.md file and commit it.
```shell
~ $ git init
~ $ git add README.md
~ $ git commit -m "first commit"
```

Push your files that you have added or modified into the remote branch.
```shell
~ $ git remote add origin https://github.com/semih/github-demo.git
~ $ git push -u origin master
```

We have created a file and wrote something into it. We will see the branch that we worked on it and we use the "git status" command to see if there are any changes between the working directory, the staging area, our local repository and remote repository. We have to use "git add <file>..." command to track.
```shell
~ $ echo "Test Git Quick Start Demo" >> start.txt
~ $ ls
.git		README.md	start.txt
~ $ cat start.txt
Test Git Quick Start Demo
~ $ git status
On branch master
Your branch is up to date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	start.txt
nothing added to commit but untracked files present (use "git add" to track)
```

After executing "git add <file>..." command, git tells us there is a new file in staging area which Git describes as "Changes to be commited". The file is in the staging area awaiting the commit.
```shell
~ $ git add start.txt 
~ $ git status
On branch master
Your branch is up to date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)
	new file:   start.txt
```