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