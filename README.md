

## What is version control?

Imagine you are collaborating with your univeristy group on a project. Before google drive/docs/sheets, how would you have collated everyone's contributions together?

It would not be unusual to end up in a scenario where you're unsure of what's in each version, like this:

![image-20210114172220493](/Users/esmehotstonmoore/Library/Application Support/typora-user-images/image-20210114172220493.png)

In scenarios like this, several people are editting several copies of one original document resulting in duplicates. This can happen if people are working at the same time or asynchronously off of old copies.  To check everything makes sense together (and definitely before submitting), someone would have had to go through and combine the edits together. This is difficult because they may not know which is the most recent copy of each paragraph. Information often gets lost or does not fit together properly. 

These challenges are not dissimilar to those which software teams face when collaborating in a code base:

- How do you incorporate each others' edits into your own copy?
- How can you all make edits at the same time?
- How do you know that you are on the most recent version?
- How do you revert back to a previous version if you make a mistake?
- If you find a bug, how can you work out which version it first appeared in?
- How can you tell who contributed each part?

Version control systems therefore aim to solve these challenges. They provide a way for teams to work on projects together, combine their edits into a single up to date version and provide a way to navigate through all the previous edits. Version control is not unique to software: it can be used for books, research papers, data sets or anything which either changes over time or are written by groups.

Let's consider your Prework game projects for a concrete example of how version control can help. Some pairs found themselves copying the code each time to save an old version which could be referred back to if they broke the current copy - version control allows you to easily access old copies. Some pairs experienced the issue that different individuals couldn't edit the game simultaneously - version control provides an easy way to collaborate on separate copies and then combine your changes together again.

### Optional further reading

For more information about version control generally, look at [Atlassian's page](https://www.atlassian.com/git/tutorials/what-is-version-control). A more technical discussion of types of verison control system [can be found in the git documentation](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) for those with a deeper interest.

## What is git?

Git is a distributed version control system. Instead of saving a snapshot of the repository at that moment in time, it saves a full mirror of the repository on every team member's machine, including the full history of it. This means that if any singular machine were to have a problem, any of the others could be used to restore the database and its history. 

Git is free and open source. 

Software developers use version control both at work and for personal projects, and git is the most popular system to do this with by far. 

### How do git and GitHub compare?

Git is the tool used to control file versions.

GitHub is the platform used to host the git repositores.



## Git walk throughs

### Learning objectives:

- To walk through the happy path of initialising a git repository and making commits
- To walk through the happy path of pushing your local repository to a remote repository on github
- To walk through the happy path of cloning someone else's repository
- To learn the commands: git init, git add, git commit, git log, git status, git push, git clone
- To understand the concept of files moving between your working directory, staging area and repository
- To get more familiar with how GitHub can be used to share code between devices



### Happy path - initialising a repo and making commits:

Use the finder to create a folder in `Academy`. Call this folder `git-demo`.

Open Visual Studios code. Under `Start`, choose the option `Open a folder`. Open the folder called `git-demo`. In this folder, `create a file`. Call the file `README.md` and click away. Leave this file empty for now. The file extension `.md` denotes that it is a markdown file, this is similar to a text file. 

Outside of VS Code, open a terminal window.

Navigate to open the `git-demo` directory (using `cd`).

Now, we want to set up a clean git repository. We want to initialise our current directory (i.e. where we are now) as a git repository so we do not pass the command any arguments. Run `git init` (Note: If we wanted to specify a different directory to be the git respitory then we would use an argument to do that,`git init <directory>.`)

Look at the response: `Initialized empty Git repository in /Users/esmehotstonmoore/Build/Academy/git-demo/.git/
fatal: your current branch 'master' does not have any commits yet`

Understanding the response: 

	- We have successfully initialised an empty git repository, the address shows us that it is in `git-demo` - the directory where we ran the command from. This command was ran at the project level as you do not want to have multiple git repositories inside of one another.
	- It shows that it has created a `.git` folder. The `.` shows that it is hidden so if you run `ls` you will not see it (`ls` shows `README.md` as the only file). Run `ls -a` to show all files/folders including hidden ones. This shows `.git` (and some other which you can ignore).
	- Ignore the word fatal.
	- It tells us which branch we are currently on: `master` (commonly called `main` ). We will discuss branches later.
	- It tells us we have not yet made any commits, which means we have not yet taken any snapshots.

Let's check the status of all our files. Run `git status`:

- It tells you the branch you are on: `master`
- It tells you that you do not have any commits yet (you have stored no snapshots)
- It tells you that you have two untracked files (`README.md` and `.DS_Store` which is to do with Mac folder systems ). 

Untracked files are files which are not currently staged by git - if you were to take a snapshot now then they would not be included. You cannot take a snapshot if there are no staged files. 

We add files to the staging area using `git add <file/directory>` . Let's now stage both of these files:

- `git add README.md`
- `git add .DS_Store`

We should check the status to see which files are staged: run `git status`:

- It tells you the branch you are on: `master`
- It tells you that you do not have any commits yet (you have stored no snapshots)
- It tells you that you have two changes to be committed (`README.md` and `.DS_Store` ) which means they are both in the staging area. It also tells you that each of these is a new file.

Now our files are ready to take our first snapshot, or to make our first commit. The command for this is `git commit -m "<commit message">`. The flag `-m` shows that we will add a message, and the message itself must be in speech marks. Let's make a commit and call it `"initial commit"`. We do this by running `git commit -m "initial commit"`:

- It lists the branch, commit hash and commit message
- It states that 2 files were changed (we know that these are `README.md` and `.DS_Store`)
- It also states there are 0 insertions/deletions: this is the accumulative lines of code in the files and they are in effect empty so it is zero.
- It states that it created each of `README.md` and `.DS_Store`

Now if we check the status again, `git status`, we get:

```On branch master```

```nothing to commit, working tree clean```

So:

- We are still on the same branch, master
- The working tree is clean. This means that no changes have been made since the last commit.

Now, let's make a change to a file: open `README.md` and add the text `Here is something to read` and then save that file. When you save then the changes are stored in the working directory, but git does not yet know about this.

Let's check the status via `git status`:

```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Let's analyse this output:

- It tells you the branch you are on: `master`
- It tells you that you have modified `README.md` (i.e. you have made changes within that file).
- It tells you that that change is not `staged` i.e. it is only in the working directory, and has not yet been added to the staging area.
- Therefore there are no changes add to the commit (i.e. the staging area is empty).
- It tells you the commands which you would need to add a file to the staging area, or to discard the changes you have made to `README.md` since the last commit (this would undo your saved changes).

Let's check exactly what the changes have been since the last commit - run `git diff`. 

The main points to take out of this response are:

- The differences occur in `README.md`
- The plus shows a line has been added, and the text on that line (`Here is something to read`) is also shown.

We always check the diff before adding files to the staging area (or making a commit) in order to make sure they are changes we want to include. At later points we will split work into several commits and demo a way to check the diff in VS Code.

We are happy that we want to stage that change to `README.md`, and so let's add it to the staging area. Use `git add README.md`. 

Now, if you run `git status` again:

- It tells you the branch you are on: `master`
- It tells you that there are `changes to be committed` - these are the changes in the staging area. 
- It tells you that `README.md` has been modified. We know that that is the line of text which we added to it. 

Once happy, we can now take a snapshot. That means we will commit the changes which are in the staging area i.e. `README.md`. We do this by running `git commit -m "Added something to read to the README"`.

If you like, you can check the status again (`git status`) and you will see that the working tree is clean as we just committed our only change.

Let's go through the process of editing a file, staging it and committing it again. Please add a second line of text to `README.md`  and commit it with a relevant message.

(If unsure then follow these steps: open the file in VS code and add text, check git status in the terminal, add the file to the staging area, check the status, commit the change.)

Now, how do I see a list of all the commits I have made? Run `git log`. If you have followed the above steps, you should see **three commits** listed. For each commit you can see:

- The commit hash - In simple terms, this is a long string which is used to uniquely identify each commit. More on this later.
- The author - This tells you who made the commit (name and email)
- The date and time - This is the date and time at which the commit was made
- The commit message - Commit messages should be written to describe the changes which they include.

Later, we will learn ways to explore what's in previous commits and this will allow us to revert to previous versions and work from there. 





### Happy path - working with a remote repo without branches (https):

So if we want to protect against our computer breaking then we want to find a way to store this info off of our own laptops. We use a remote repository for this. We are going to host them on GitHub. 

If you have not already then create an account: choose a username which is professionally appropriate as you can build a reptutation through your account.

Create a new repository on GitHub:

- Click the new button next to the word `repositories`
- Don't use a template
- Name your repository `git-demo`
- Make your repo public so that you can see each others'
- Do not tick any of the options for a readme, git ignore file or licence. We will come back to the git ignore file later.

Choose `https` and then copy the url given (it will begin `https://github.com/...`)

Go back to your terminal and run `git remote` to see any remote repositories. There is no response, meaning you have not yet set any remote repo to be upstream of yours.

Let's set the github repo we just created up and call it origin by running `git remote add origin <https url of your repo>` including the url which you just copied off of gitHub. 

Run `git remote` again to check the remote repositories set up and you will see that `origin` has now been added (this refers to the gitHub repo which you just told it to call that).

Later we will push to the upstream repo using `git push` however if you run it here it will tell you that there is no upstream branch configured to your current branch. 

Therefore, let's set the upstream branch using `git push --set-upstream origin master`. This means we are both pushing and setting the upstream branch to be a branch on the remote repo (origin) and that that branch will also be called `master`

Open your repo on github and you can now see both files `.DS_Store` and `README.md`. It shows a single branch `master`, to include the otehr branch we must also push it to the remote repo. Therefore check it out locally, set the upstream up and push it. 

As we go forwards, everytime we make commits locally on any branch we should push them up to the remote repository. 



### Happy path - cloning someone else's remote repo:

Open a new terminal window.

Navigate to your Academy folder.

Open GitHub in chrome and navigate to `<Hello world repo url>`

Click the green `Code` button and copy the https url. 

Run `git clone <https url>` in the terminal.

Now run `ls`.

You will see that a folder has been created with a copy of the remote repository inside.

`cd` into the <name of hello world repo> and run it.

You have succeafully cloned the repo!



### Independant exercises

- Moving code from repl.it to GitHub and cloning someone else's:
  - Create a new folder
  - Initialise a git repo here
  - Put your code off repl.it into a .py file in it
  - Write a relevant readme in markdown
  - Make a commit with both files
  - Make a remote repo
  - Push your local changes to the remote repo. 
  - Send the url to your pair. 
  - Clone theirs and run it locally on your machine.

- Adding Command Line Game to GitHub:
  - Work with your pair in order to transfer your Command Line game project to GitHub. 
  - Clone it onto the other machine so that you both have a copy. 













## Future sessions: - need work



Happy path - branching locally:

Git branches allow for independant lines of development. Read the description of the thought process behind them [by Atlassian](https://www.atlassian.com/git/tutorials/using-branches), read upto and including the first paragraph of `how it works` (or watch in video if preferred). 

Now let's run through the process of creating another branch; here our feature will be recording the git commands.

If you run `git branch` then it lists all the branches in your repository. At the moment, you will see the only branch is `master` and the star denotes that you are on master.

To create a second branch called `first-commands`, run `git branch first-commands`. 

Run `git branch` to see the list of branches again. Now you can see that the new branch `first-commands` has been created but that you are still on `master`. 

Checkout the branch `first-commands` using `git checkout first-commands`.

Now when you run `git branch` you will see that you are on the new branch. 

Using VS Code, add a file `Commands.md` listing the git commands you have used so far and a memory jog for each one and save it. 

Commit this to the branch you are on (`first-commands`). Now if this was something more risky, then we would know that `master` branch was continuing unharmed and so any way we break this would not affect it. 

If we want to explore `master` then we can check it out using`git checkout master`. Git log on each branch in order to compare the commits on each: `master` has not been affected by the additional commit added to the branch `first-commands`. 





Happy path - working with a remote repo (ssh):

So if we want to protect against our computer breaking then we want to find a way to store this info off of our own laptops. We use a remote repository for this. We are going to host them on GitHub. 

If you have not already then create an account: choose a username which is professionally appropriate as you can build a reptutation through your account.

Create a new repository on GitHub:

- Click the new button next to the word `repositories`
- Don't use a template
- Name your repository `git-demo`
- Make your repo public so that you can see each others
- Do not tick any of the options for a readme, git ignore file or licence. We will come back to the git ignore file later.

Choose `ssh` and then copy the url given (it will begin `git@github.com...`)

Go back to your terminal and run `git remote` to see any remote repositories. There is no response, meaning you have not yet set any remote repo to be upstream of yours.

Let's set the github repo we just created up and call it origin by running `git remote add origin <ssh url of your repo>` including the url which you just copied off of gitHub. 

Run `git remote` again to check the remote repositories set up and you will see that `origin` has now been added (this refers to the gitHub repo which you just told it to call that).

Checkout your `master` branch locally.

Later we will push to the upstream repo using `git push` however if you run it here it will tell you that there is no upstream branch configured to your current branch. 

Therefore, let's set the upstream branch using `git push --set-upstream origin master`. This means we are both pushing and setting the upstream branch to be a branch on the remote repo (origin) and that that branch will also be called `master`

If this is the first time you have used `ssh` then permission will be denied as you need to set up a key so that github can identify your laptop safely. Then follow the steps provided by GitHub [here](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and then try again.

Open your repo on github and you can now see both files `.DS_Store` and `README.md`. It shows a single branch `master`, to include the otehr branch we must also push it to the remote repo. Therefore check it out locally, set the upstream up and push it. 

As we go forwards, everytime we make commits locally on any branch we should push them up to the rmeote repository. 







Look into with new laptop: 

git config

add diagrams for working directory, staging area, 

Dont add as a second line - too complicated for markdown 🤔 

