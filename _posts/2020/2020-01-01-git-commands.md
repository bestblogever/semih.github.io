---
layout: post
title: "Git Commands"
date: 2020-01-01 18:31ly
author: semih
comments: true
categories: [git]
tags: [git, source control management, scm]
---
We have numerous sources and manage it using source control management(SCM) DevOps tools like Git, SubVersion, CVS, TFS, ClearCase, Mercurial. Git is a modern distributed version control system. I am going to tell you most useful Git commands and why we need to use those commands. I will explain each step with examples.


| Git Command Line Tools is consistent | | There are 3 states of Git. |
| ------------ |-----| ------------ |
| - Terminal on Mac/Linux  |  |  - Working directory |
| - Git Bash on Windows | | - Staging area (pre-commit holding area) |
|   |  | - Commit (git repository, history) |

![image](/assets/images/basic-git-workflow-lifecycle.png)

```shell
~ $ git version
   git version 2.17.2 (Apple Git-113)
```
git global user name and email configuration
```shell
~ $ git config --global user.name "github-username"
~ $ git config --global user.email "github-useremail"
~ $ git config --global --list
```
### Demo
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

Push it to the remote branch.
 ```shell
~ $ git remote add origin https://github.com/semih/github-demo.git
~ $ git push -u origin master
```
