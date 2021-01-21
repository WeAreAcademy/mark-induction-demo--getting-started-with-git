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

