# Walk through an example of cloning someone else's repository

Open a new terminal window.

Navigate to your Academy folder.

Open GitHub in chrome and navigate to `https://github.com/<your pairs github username>/mark-induction--git-walk-through`

Click the green `Code` button and copy the https url.

Run `git clone <https url> <new directory name>` in the terminal. The argument for the directory name is optional but we will need to include one here as their repository has the same name as ours and you cannot clone a repository into a directory which already contains a repository of the same name. I would recommend using `mark-induction--git-walk-through--<your pairs github username>` as the new directory's name for clarity.

Now run `ls`.

You will see that a folder has been created of the name you gave, with a copy of the remote repository inside.

`cd` into the sub-directory.

You have successfully cloned the repo!

Now you can look at the `git log`:

- The repository should show similar commits to what you did yourself
- This shows that when you clone a repository you clone the entire git history and not only the current versions of files.

Feel free to also explore the files via VS Code.
