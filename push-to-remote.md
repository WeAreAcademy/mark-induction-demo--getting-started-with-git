

### Happy path - working with a remote repo without branches (https):

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