### What is the difference between push, pull, and fetch?

- `git push` sends changes from your local branch to a remote repo
- `git pull` retrieves changes from a remote repo into your tracking branch and merges them into your local branch
- `git fetch` retrieves changes from a remote repo into your tracking branch

`git push` checks if there is a tracking branch for a remote repo connected to your local branch. 
If so, changes from the local branch are pushed to the remote branch. 
You can think of git push as "make the remote branch resemble my local branch". 
git push will fail if the remote branch has diverged from your local branch. If some commits in the remote branch are missing from your local branch, you should synchronize branches with git pull or git fetch and git merge.

`git pull` and `git fetch` are sometimes described as equivalent. This isn't entirely correct, since `git pull` does two things; 
`git pull` is a combination of `git fetch` immediately followed by `git merge`. 

`git fetch` again takes your current branch, and checks to see if there is a tracking branch. 
If so, it looks for changes in the remote branch, and pulls them into the tracking branch. 
Please note that git fetch does not update your local branch. You will need to use `git merge origin/master` to merge those changes into your master branch.
git fetch is for users who want to make sure they understand the changes they are merging into their branch before the merge happens.