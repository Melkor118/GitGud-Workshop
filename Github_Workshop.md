Git Gud with Git, Github and Gradescope
===

Before we begin
---


### CS 50
Today we will be using the cloud-based environment developed by Harvard Universities CS50 program. [code.cs50.io](code.cs50.io). This is an integrated development envirnoment (IDE) and is used explicitely in some courses, for instance Web and Database Computing. It can also be used regardless of your machine either directly in your browser or via [Visual Studio Code](https://code.visualstudio.com/).

Go to [code.cs50.io](code.cs50.io) and connect your Github account. You will need to authorise the application. Follow the prompts.

***A quick side note, I highly recommend enrolling and taking [CS50's Course](https://cs50.harvard.edu/college/2022/spring/) if you're just starting out and have some time on your hands***

Now that we have this set up lets move on.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Overview.png "Overview")

### What is git?
Git is a free and open source distributed version control system. What is version control? Essentially, it’s a system that allows you to record changes to files over time, thus, you can view specific versions of those files later on.

### Why Use Git?
Over time, Git has become an industry standard for development. Being able to snapshot your code at a specific time is incredibly helpful as your codebase grows and you have to reference previous versions of it.

### How It Works
With Git, you record local changes to your code using a command-line tool, called the “Git Shell” (you can use Git in other command-line tools — I’ll refer to Git Shell through the following sections). Command-line lets you enter commands to view, change, and manage files and folders in a simple terminal, instead of using a graphical user interface (GUI). If you have not used command-line before, don’t worry, once you get started, it is incredibly straightforward.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/git-1.png)

Essentially, when using Git, you make changes to your code files as you normally would during the development process. When you have completed a coding milestone, or want to snapshot certain changes, you add the files you changed to a staging area and then commit them to the version history of your project (repository) using Git. Below, you’ll learn about the Git commands you use for those steps.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/The_Basics.png)

### Terminal Commands
While using Git on the command line, chances are you will also use some basic terminal commands while going through your project and system files / folders, including:

**pwd** - check where you are in the current file system

**ls** - list files in the current directory (folder)

**cd** [directory-name] - moves to the given directory name or path

**mkdir** [directory-name] - makes a new directory with the given name

### Creating Repositories

There are two ways to initially start a Git Repository. The easiest method is via Github but we will get to that later. For now, lets see how to do this via Git.

Remember that Git is solely housed on your computer and is not yet a collaborative tool.

```Shell
$ git init MyFirstRepo -b main
```

This will initialise a blank repository with the branch name main.

```Shell
$ ls
MyFirstRepo
```

We now have folder called MyFirstRepo.

```Shell
$ cd MyFirstRepo
$ ls -la #List all (-a) with further information in a list (-l)
drwxr-xr-x  3 xxx  staff   96 16 Mar 17:19 .
drwxr-xr-x  3 xxx  staff   96 16 Mar 17:19 ..
drwxr-xr-x  9 xxx  staff  288 16 Mar 17:19 .git
```

We can see with the above commands that the MyFirstRepo folder contains a hidder (.) .git folder. This is how Git stores everything. This is outside the scope of the course but is an interesting thing to read up on. For now, just remember if you wish to remove the Git functionality from this folder, you can just remove this .git folder.

### Making Changes

Now that we have a Git repository we can use it to version control our local development.

Lets just create a quick README.md document.

```Shell
$ touch README.md
$ [insert your text editor cmd here] README.md #Yes, Vi, Vim, Emacs, Atom are all the greatest thing since sliced bread. I use VScode like a peasant
```

Write anything you'd like and save.

```Shell
$ git status
```
![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_Status.png)

We can now see that git has seen that we have added a file. This file is currently untracked which means that it is not version controlled right now. lets change that.

```Shell
$ git add * #will add everything from your current directory down, be careful with this.
$ git add *.cpp #will add everything from yoru current directory that is a .cpp file.
$ git add README.md #will add the README.md file as a tracked file.
```

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_Status-2.png)

Now it is being picked up as a tracked file and will be included in our first 'commit'.

This is known as a staged file, lets commit it to our repository so we can make further changes without worrying about our current work being lost.

```Shell
$ git commit -m "This is my first commit, i'm so gud"

```

```Shell
$ git log #show me the commit history
commit 5c285f3b22f8505c9384c5151f41ed967728fba5 (HEAD -> main)
Author: [Your details]
Date:   Wed Mar 16 17:46:08 2022 +1030

    This is my first commit, i\'m so gud
```

Using the above command we can see that the current commit is that large string of characters.

This is still all locally housed on your computer but is still version controlling your files.

### How it works

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_Status-3.png)

Now lets see how it works with Github

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Github.png)

### Overview

In essence, GitHub is a service that allows you to host your Git repositories online and collaborate with others on them. You can use GitHub through their web portal as well as the GitHub desktop GUI and the Git Shell.

As a service, GitHub is now used by 12 million developers and organizations, and has become a fairly popular standard for collaborating on projects and open-sourcing code.

### How it works

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Github-1.png)

With GitHub, you have the same local process of adding and committing files to an initialized Git repository on your computer. However, you can utilize GitHub to push your changes to GitHub’s hosting service. This allows other people to similarly work on the same project, pull your changes to their computers, and push their own changes to GitHub. Continue below to see the commands you can use to utilize Git with GitHub.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_Github.png)

### Creating and Copying Repositories

As we all know (I hope) Github is an open source hub of software. This means that the code on Github can be inspected openly and used (in most cases) freely. Always make sure you check their license before using someones code however.

As stated in the previous section you can also initialise a git repository from Github directly. There are two ways to do this.

#### Fork (cannot be done on the command line)

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Fork.png)

Forking a repository essentially copies that project to your online GitHub account. However, to work on that project on your local computer, you must clone the project.

#### Clone (can be done on the command line)

Cloning a project simply copies a Git repository with its version history, by its url, to your local computer from GitHub. From there, you can make and commit changes of your own to that repository. Any changes you commit and then push to GitHub (see below) are saved for your copy of that project.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/clone.png)

Lets try and connect our existing repository to Github so we can share how gud we are with the world.

First we need to ask Github to set aside space on their servers for our Git repo.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_New_Repo-1.png)

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_New_Repo-2.png)

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_New_Repo-3.png)

Now as shown in the last picture, we have a few options to get content into our new repo. lets connect our initial repo to Github using the 2nd snippet

```Shell
$ git remote add origin https://github.com/<username>/MyFirstRepo.git #create a remote location called origin at the following link to send my repository updates to
$ git push --set-upstream origin main #-u can be used instead of --set-upstream
```

The above will tell our local git repository to talk to the location we created on Github.

```Shell
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 254 bytes | 254.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/<username>/MyFirstRepo.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

```

We have now pushed our local git repo to Github.

![alt text](https://github.com/Melkor118/GitGud-Workshop/blob/main/images/Git_New_Repo-4.png)




