# Project 0_1: Introduction to Git and GitHub
This guide will walk you through what is git and GitHub and also how to use these tools

If you want to go above and beyond this guide, follow:

- [git-scm guide](https://git-scm.com/docs)
- [GitHub guide](https://docs.github.com/en)

## What is Git?
<img src="images\git.png" alt="drawing" width="200"/>

Git is a version control tool used for tracking file versions, changes, etc. You can use git to revert to previous changes, work on different versions of a file, compare files, etc. It is a program that you download and at the basic level has no user interface and is used from the command line. 

## Installing Git
Use this [link](https://git-scm.com/downloads) to download git. Note this will install the program only, it will not come with a graphical interface

## Git Basic Concepts
Think of Git as a file cabinet manager. You can ask git to take pictures of your work, git will then put these pictures in its file cabinet. Along with this picture, it will store data about when the picture was taken, where it was taken, etc.

You may refer back to those files, look at the timeline of those files, and revert back to one of these snapshots.

To start tracking your work, you need to create a ***Git Repository***. A Repository (repo) is a way to tell git that you want to track the changes in the folder. 

<img src="images\gitdemo.png" alt="drawing" width="400"/>

## Setting Up Git
For the first time after installing git, you will need to configure your git information. 

`git config --global user.name "Mike Wazowski"`

This command will set your user name on your git system.

`git config --global user.email mikewazowski@example.com`

This command will set the email which your local git will reference. 

## Basic Git Commands

`ls`

This command is called "list". It will list all the content of the current folder (also called directory) you are in

`cd`

This command is called "change directory". It will change the directory you are currently in to whatever you follow it up with.

- e.g. `cd Downloads`

### Git Status
`git status`

This will give you the status of your current git repository. It will tell you whether there have been changes, whether files have been staged, committed, etc.

### Git Init
`git init`

This will initialize the current folder you are in to a git repository and now you can start using git commands. 

### Git Stage
`git add .`

Think of staging a change as putting your work on a table/stage ready to get its snapshot taken. At this stage, the changes have not been committed yet. 

The `.` parameter will stage all changes you have made in the current folder. Alternatively, you can use the `*` parameter to stage ALL changes you have made. If you want to only stage the changes in one file, you can add the file's name after `git add` to specify that. 

### Git Unstage and Discard
`git restore file-name`

This will discard the changes in the specified file. 

`git restore --staged file-name`

This will unstage the specified file.

### Git Untrack
`git rm file-name`

This command will do the opposite of git add. It will untrack these files. You can use the same parameters as git add for this command (`*` and `.`).

### Git Commit
`git commit -m "insert commit message here"`

This command will only work if there is work that is staged. Running this will take a snap shot of your work AND store it inside of git's commit history. 

`git commit -a -m "insert commit message here"`

adding the `-a` parameter allows you to stage and commit in one command. 

Each commit will have a unique ID that you can refer to in order to identify it. The commit will also have its accompanying commit message along side it.

```
commit a770d5793bbbdb3b20a2a62d121ddebe2d06f215 (HEAD -> main, origin/main, origin/HEAD)
Author: Millennium Falcons <falcons3647@gmail.com>
Date:   Thu Apr 7 18:19:46 2022 -0700
    practice day 1
```

Here you can see the commit ID: `a770d5793bbbdb3b20a2a62d121ddebe2d06f215`

The commit message: `practice day 1`

The commit date and time: `Thu Apr 7 18:19:46 2022 -0700`

and more...

`git commit --amend`

This will allow you to amend your commit and edit your commit history. You can change commited files and your commit messages with this command. 


### Git Log
`git log`

This command will show you a log of everything commit that the repository you are currently in has. If the list is too long, the terminal will adjust and update as you press the up and down arrow key. To get out of git log, press `q` 

`git log --graph --oneline`

<img src="images\log.png" alt="drawing" width="400"/>

`git log` also includes options that you can activate. Some useful ones are the `--graph` and the `--oneline` options. This command will give you a visual display of your repositories history. You will be able to see commits, branches, etc.

### Git Branches
`git branch branch-name`

This command will create a git branch. 

<img src="images\branches.png" alt="drawing" width="400"/>

Branches in git are like a separate time line of your work. It will branch off of the commit you were on when you made the branch and all the work will be separate from the `Master` (also called `main`) branch it was on. This is useful because it allows multiple people work on the same testing different features. After testing, you can then merge the branch back to `Master`. 

`git branch`

This command will list all the branches the repo has. 

### Git Checkout
`git checkout branch-name`

Git checkout is a generic command used for checking out other entities in git. However, here you can use it to switch to a different branch. When you switch branches, the files in your folder will update to match the work in that branch. 

### Git Merge
`git merge branch-name`

This command will merge the branch mentioned to the `Master` branch, integrated all the changes together. 

However, if both the `Master` and the new branch changed the same file in different ways, a ***Merge Conflict*** may occur. Please refer to [this](https://www.youtube.com/watch?v=xNVM5UxlFSA&ab_channel=Ihatetomatoes) on how to solve merge conflicts


## What is GitHub

<img src="images\github.png" alt="drawing" width="200"/>

GitHub is basically a cloud service where you can upload the git repository on your own computer. 

With this, you can access your code and the code's history from any computer connected to the internet. This also allows you to collaborate with other people on the same project. 

## Getting Started
First make a GitHub account with [this](https://github.com/)

You also have the option to use GitHub with a user interface by downloading [this](https://desktop.github.com/). However, this guide will not be covering how to use GitHub Desktop. If you want to learn, use [this](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop).

## Basic GitHub Concepts

<img src="images\gitrepo.png" alt="drawing" width="400"/>

GitHub's website also has repos. These are what's called ***git remote repos***. These repos are hosted on GitHub's servers and you can upload your local git history and files to them through the git terminal or GitHub desktop. Since it is still a git repo, all the previous concepts of commits and history still apply. 

With remote repos, you can now download, clone, and contribute to a project that many people are working on at the same time.

## SSH
In order to use this remote repo, you must first let GitHub recognize that your computer corresponds to your account. 

<img src="images\ssh.jpg" alt="drawing" width="400"/>

This is done through a program called ***Secure Socket Shell**. This is an encryption program that will general key pairs so that you and GitHub can recognize each other and you can upload and download code to their servers.

To do this, follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## GitHub and Git Remote Key Terms
#### Cloning
```git clone git@github.com:my-repo.git```

Cloning means that you are copying and downloading a full version of the repository, including all of its git history, branches, etc.

This is different from downloading because downloading merely downloads the files only. 

#### Pushing
`git push`

Pushing means that you are taking all of your local files, git history, etc. to a remote repository. Thus, you can only use this command if the repo on your computer is connected to a remote repo.

#### Fetching
`git fetch`

Fetching will grab files and git histry from a remote repository. This will get you all the updated information on the repo if someone else has been working on the project. However, this will not merge these changes into your repo.

#### Pulling
`git pull`

Pulling combines fetching and merging. Essentially grabs the change and integrates them into your local repo.

## Creating and Pushing to a Remote Repo
Follow [this guide](https://www.digitalocean.com/community/tutorials/how-to-push-an-existing-project-to-github) to learn how to create and push code with the git terminal.

## Basic GitHub Collaboration Concepts
#### Issues

<img src="images\issues.png" alt="drawing" width="400"/>

Issues in GitHub allows you to manage your work and see what future tasks there are to be fixed and how your project can be improved. These issues have a specific issue number (#1). Issues can also have labels assigned to them. To create one, simple click ***new issue*** under issues (big green button).

`fixes #1`
The above commit message will close issue #1

`#1 is cool`
The above commit message will mention issue #1 and it will show up in the issue discussion thread.

[Read more about issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

#### Pull Requests

<img src="images\pull.png" alt="drawing" width="200"/>

Knowing about branches, pull requests are basically a way to ask the administrators of the repo to merge your modified branch into `Master`. 

To create a pull request, simply go to the ***pull request*** section of the GitHub repo. Then chose which branch you want to compare and merge to create your pull request.

If there are no merge conflicts (changing the same content different ways on the two branches) the admin can accept the pull request and merge your code into `Master`

[Read more about pull requests](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

## ***Final Notes***
Do not be conservative on git commits. Please commit any working changes you have. ***DO NOT*** make one commit for many changes. This will make reverting and debugging changes very hard since you cannot find where the code that broke the project could be hiding. 

Remember to regularly pull code to ensure you have the correct version and you aren't super far behind.

Try to avoid changing a lot of files at once in branches. This could lead to lengthy and troublesome merge conflicts. 

Lastly, please write good and descriptive commit messages :)

## ***Authors***
- [Team 3647, Edward Sun](https://github.com/EdwardoSunny)

















