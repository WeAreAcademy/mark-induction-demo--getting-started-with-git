











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







