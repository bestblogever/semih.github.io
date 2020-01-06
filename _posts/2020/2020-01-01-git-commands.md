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
&nbsp;

| Git Command Line Tools is consistent | | There are 3 states of Git. |
| ------------ |-----| ------------ |
| - Terminal on Mac/Linux  |  |  - Working directory |
| - Git Bash on Windows | | - Staging area (pre-commit holding area) |
|   |  | - Commit (git repository, history) |

&nbsp;
![Basic Git Workflow Life Cycle](/assets/images/basic-git-workflow-lifecycle.png)

### Configuration
If Git is installed in our pc, it tells us the version.
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
&nbsp;
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

We execute "git commit" command and check the status again. As a result, the new file has been moved from staging area into the local repository. Because of there are no other pending changes, Git marks the working directory as clean. But our file is not yet on Github.
```shell
~ $ git add .
~ $ git commit -m "git-commands"
[master 2cd0af0] git-commands
 1 file changed, 1 insertion(+)
 create mode 100644 start.txt
~ $ git status
On branch master
Your branch is up to date with 'origin/master'.
nothing to commit, working tree clean
```

There is one last step we need to do, and that is a push. We need to run "git push origin master" command. "origin" refers to the Github copy of our repository. "master" refers to branch name in the repository. If we did everything correctly, our new file should be on the Github copy of our repository.
```shell
~ $ git push origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 299 bytes | 299.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/semih/github-demo.git
   785389b..2cd0af0  master -> master
```
&nbsp;
### Basic Git Commands
- Starting a Project
	- Fresh (no source yet)
	- Existing source locally
	- Github project (fork and clone)
- Basic Workflow (add, commit, push, pull)
- Working with files (rename, move & delete)
- History and Aliases
- Ignoring Unwanted Files

Create a new project with "git init command
```shell
workspace $ git init fresh-project
Initialized empty Git repository in /Users/semihkirdinli/workspace/fresh-project/.git/
workspace $ ls
fresh-project
workspace $cd fresh-project/
fresh-project $ ls -al
total 0
drwxr-xr-x  3 semihkirdinli  staff   96  7 Oca 00:58 .
drwxr-xr-x  6 semihkirdinli  staff  192  7 Oca 00:58 ..
drwxr-xr-x  9 semihkirdinli  staff  288  7 Oca 00:58 .git
fresh-project $cd .git/
.git $ls
HEAD		description	info		refs
config		hooks		objects
```

Git status command tells us that we are on the master branch.
```shell
.git $ cd ..
fresh-project $ git status
On branch master
No commits yet
nothing to commit (create/copy files and use "git add" to track)
```

Git caught the untracked files:
```shell
fresh-project $ mate hipster.txt
fresh-project $ git status
On branch master
No commits yet
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	hipster.txt
nothing added to commit but untracked files present (use "git add" to track)
```

Changes to be committed means this new file "hipster.txt", is now in the Git staging area. We have a file that's waiting to be committed, but it's not committed yet.
```shell
fresh-project $ git add hipster.txt 
fresh-project $ git status
On branch master
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   hipster.txt
```

If we write only "git commit", our editor lists changes to be committed and i can type the commit message on the top lines of file and save it.
```shell
fresh-project $ git commit (file is opening here with our default text editor)
[master (root-commit) 2296291] Adding new file
 1 file changed, 1 insertion(+)
 create mode 100644 hipster.txt
fresh-project $ git status
 On branch master
 nothing to commit, working tree clean
fresh-project $
```



&nbsp;
Hope to see you in the next article...