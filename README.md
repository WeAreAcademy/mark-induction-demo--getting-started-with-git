

---
module: induction

level: 1

methods:
  - pair
  - solo

tags:
  - wip

---



# Getting started with Git

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a>

> This is part of Academy's [technical curriculum for **The Mark**](https://github.com/WeAreAcademy/curriculum-mark). All parts of that curriculum, including this project, are licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License</a>.



You have learned how to use the terminal to make commands and navigate through your directories. Now let's move on git, the software developer's answer to version control, which we will begin by using through the command line.

In this repo, you can find information about version control and git, walk throughs of git scenarios and exercises to practice with.



## Prerequisites:

Before following this content, we recommend you:

- Have some familiarity with the command line



## Learning objectives:

- Understand the advantages of using version control
- Initialise a git repository
- Understand the concept of files moving between your working directory, staging area and repository
- Commit files and code
- Share directories between devices or individuals using git (push to a remote repository and clone from someone else's)



## Exercise 1: Understanding version control and introducing git

> 🎯 **Success criterion:** notes on your understanding of the need for version control - please do come back and add to this later as your understanding of the capabilities of git increases.

Resources we recommend you use to increase your familiarity:

- Read [our introduction to version control](./version-control.md) and consider the further reading listed.
- Read [our brief introduction to git](./git.md).

It might be helpful for you to make notes of your understanding as you go along to reinforce your learning.



## Exercise 2: Walk through an example of initialising a repository and making commits

> 🎯 **Success criterion:** your own diagram of the working directory, staging area and repository, and a cheat sheet of the git commands you have used

Now you understand why we need version control, it's time to get started with using it yourself locally (on your own machine).

Follow [these steps](./initialise-and-commits.md) to initialise your own repository, commit changes to it and see a log of your commits. Along the way, we will introduce you to the concepts of what's in a working directory, staging area and the repository itself. 

As you go through, we recommend:

- Making your own diagram of how the working directory, staging area and repository related
- Keeping a cheat sheet of the commands you use in the process of initialising a repository and committing to it.



## Exercise 3: Walk through an example of pushing to a remote repository

> 🎯 **Success criterion:** see your repository on GitHub from another device

Now you know how to set up a local repository on your own machine and committed files to it, how do you back it up elsewhere? So if we want to protect against our computer breaking then we want to find a way to store this info off of our own laptops. We use a remote repository for this. We are going to host them on GitHub. GitHub is the most popular code hosting platform for software development, and the platform you will be using to see this at the moment!

If you have not already, then create an account: choose a username which is professionally appropriate as you can build a reptutation through your account. Make sure you choose a password which you can remember - we will need to use it again soon.

Continuing on from your work in Exercise 2 (Walk through an example of initialising a repository and making commits), follow [these steps](./push-to-remote.md) to create a remote repository and push you local repository up to it. It is now publicly available on the web. If you copy its url, you can access it on your phone or other devices.



## Exercise 5: Walk through an example of cloning someone else's repository

> 🎯 **Success criterion:** a copy of someone else's repository on your own machine

So far, you have created a local repositry, committed to it and pushed your work up into the cloud on GitHub. We have already demonstrated that it is available from other devices, but how do they download a local copy of it?

Continuing on from your work in Exercise 3 (Walk through an example of pushing to a remote repository), follow [these steps](./clone-remote.md) to clone someone else's repository onto your machine. Encourage someone else to clone your repository onto their machine so that you can both see each other's. 



## Exercise 6: Working with multiple files TODO

> 🎯 **Success criterion:** blah

Moving code from repl.it to GitHub and cloning someone else's:

- Create a new folder
- Initialise a git repo here
- Put your code off repl.it into a .py file in it
- Write a relevant readme in markdown
- Make a commit with both files
- Make a remote repo
- Push your local changes to the remote repo. 
- Send the url to your pair. 
- Clone theirs and run it locally on your machine.

## Exercise 7: Moving your CLI game to GitHub TODO

> 🎯 **Success criterion:** blah

- Work with your pair in order to transfer your Command Line game project to GitHub. 
- Clone it onto the other machine so that you both have a copy. 