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

In this repo, you can find information about version control and git, walk throughs of git scenarios and exercises to practice with independently.

## Prerequisites:

Before following this content, we recommend you:

- Have some familiarity with the command line (our intro session is adequate).
- Install Visual Studios Code [(according to these steps for our scholars on Macs)](./vs-code-installation.md)

## Learning objectives:

- Articulate the advantages of using version control
- Initialise a git repository
- Explain the difference between working directory and staging area
- Stage changes made in a local repository
- Commit staged changes to a local repository
- Push a local repository to a remote repository on GitHub
- Clone someone else's repository off GitHub onto your local machine

## Exercise 1: Understanding version control and introducing git

> 🎯 **Success criterion:** notes on your understanding of the need for version control - please do come back and add to this later as your understanding of the capabilities of git increases.

Resources we recommend you use to increase your familiarity:

- Read [our introduction to version control](./version-control.md) and consider the further reading listed.
- Read [our brief introduction to git](./git.md).

It might be helpful for you to make notes of your understanding as you go along to reinforce your learning.

## Exercise 2: Setting up your machine

> 🎯 **Success criterion:** having git downloaded and setting up your name and email globally

If you have not used git on your Mac before then you will need to do some basic set up to get started. 

### Installing git:

- Open a terminal
- Run `git --version`
- This normally checks the version
- If you already have git installed it will tell you the version which is installed (I am using `git version 2.24.3 (Apple Git-128)` and so the discussions of the responses will refer to this) and so you can continue to the next section
- If you do not have git installed it will open up a dialog window. Follow through with it, accepting the terms and conditions. Git will download.
- Once the download has finished, run `git --version` again and you will see the version number. This confirms that the download was successful.

### Configuring your details for git:

Now we want to configure your name and email globally. These are the name and email which will be associated with the work which you have done (which will be associated with your git commits, a concept which we are going to learn more about). Setting them up globally means that these are the ones which will be used everywhere on your machine - they are not specific to the directory which you are in.

In the terminal, run these commands:

- `git config --global user.name "<your name>"`
- `git config --global user.email "<your email>"`

By convention, angle brackets show where to insert specific info. For example, if my name was João Bloggs, and my email address was `joao.bloggs@mydomain.com`, I would run:

```bash
git config --global user.name "João Bloggs"
git config --global user.email "joao.bloggs@mydomain.com"
```

To check the name and email being used at any time you can run:

- `git config --global user.name`
- `git config --global user.email`
  And the responses will be the name/email being used.

If you wish to change the name/email you are using in the future then the same commands can be used.

## Exercise 3: Walk through an example of initialising a repository and making commits

> 🎯 **Success criterion:** your own diagram of the working directory, staging area and repository, and a cheat sheet of the git commands you have used

Now you understand why we need version control, it's time to get started with using it yourself locally (on your own machine).

Follow [these steps](./initialise-and-commits.md) to initialise your own repository, commit changes to it and see a log of your commits. Along the way, we will introduce you to the concepts of what's in a working directory, staging area and the repository itself.

As you go through, we recommend:

- Making your own diagram of how the working directory, staging area and repository related
- Keeping a cheat sheet of the commands you use in the process of initialising a repository and committing to it.

### Extension: Continue independently

Now that we have walked through how to add files and how to make commits, please run through the process of adding to each file and committing your changes (you can make changes to both files in the same commit or in separate commits). Why not add your notes on your understanding of version control and make a new file to add your list of git commands which you have met so far?

I also recommend looking at your `README.md` file, these are in effect the cover page of your repository - it should explain what the repository is all about. We will discuss writing a good README in the future.

## Exercise 4: Walk through an example of pushing to a remote repository

> 🎯 **Success criterion:** see your repository on GitHub from another device

Now you know how to set up a local repository on your own machine and committed files to it, how do you back it up elsewhere? So if we want to protect against our computer breaking then we want to find a way to store this info off of our own laptops. We use a remote repository for this. We are going to host them on GitHub. GitHub is the most popular code hosting platform for software development, and the platform you will be using to see this at the moment!

If you have not already, then create an account: choose a username which is professionally appropriate as you can build a reptutation through your account. Make sure you choose a password which you can remember - we will need to use it again soon. Use the same email which you have configued your machine to associate with your commits - you can check this by running `git config --global user.email` in the terminal.

Continuing on from your work in Exercise 2 (Walk through an example of initialising a repository and making commits), follow [these steps](./push-to-remote.md) to create a remote repository and push you local repository up to it. It is now publicly available on the web. If you copy its url (`https://github.com/<your github username>/mark-induction--git-walk-through`), you can access it on your phone or other devices.

If you navigate to `https://github.com/<your github username>/mark-induction--git-walk-through/commits` then you will see a list of the commits you have made. If you select each one then you can see what changed in each commit. We can use this to work out who contributed each aspect (so who to go to for questions), when each change was made and what it was trying to achieve (by reading the related commit message). This will become very helpful as we use git with large applications.

If you navigate to `https://github.com/WeAreAcademy/mark-induction--git-walk-through` then you can compare your repository to my example from the walk through, feel free to also explore the commits by adding `/commits` onto the url.

## Exercise 5: Walk through an example of cloning someone else's repository

> 🎯 **Success criterion:** a copy of someone else's repository on your own machine

So far, you have created a local repository, committed to it and pushed your work up into the cloud on GitHub. We have already demonstrated that it is available from other devices, but how do they download a local copy of it?

Continuing on from your work in Exercise 3 (Walk through an example of pushing to a remote repository), follow [these steps](./clone-remote.md) to clone someone else's repository onto your machine. Encourage someone else to clone your repository onto their machine so that you can both see each other's.

## Exercise 6: Working with different file types

> 🎯 **Success criterion:** a GitHub repository including code which your pair has cloned and successfully ran

So far we have only included markdown files in our repositories, however we want to be able to use git for code as well. Let's practice further making repositories including code in them.

- Create a new folder inside your `Academy` directory
- Initialise a git repo here
- Create a new python file here (`helloworld.py`)
- Write a simple `Hello, world` script inside the file
- Practice running the script via the command `python3 helloworld.py`
- Make your initial commit
- Create a remote repository on GitHub
- Push your local up to the remote repository
- Observe how it is available online
- Make some changes and commit them: change the name so that the program greets your pair, add a relevant readme
- Regularly push your local commits to the remote repository
- Send the url to your partner, if they clone the repo then they should be able to run your prorgram (and be greeted!)
- Let's turn this repo into a collection of small challenges - add files for the code for several coding katas. If you have used code wars then this is the ideal opportunity to make a record of some of your solutions. If not, complete a kata or two now and then add the code to your repository.
- Remember to keep commiting regularly and pushing to the remote repository to keep it up to date.

## Exercise 7: Moving your CLI game to GitHub

> 🎯 **Success criterion:** adding a github repository with your CLI game in it

- Work with your pair in order to transfer your Command Line game project to GitHub.
- Clone it onto the other machine so that you both have a copy.
