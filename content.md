### What is the difference between push, pull, and fetch?

- `git push` - sent changes from a local branch to a remote repo
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch
- `git fetch` - get changes from a remote repo into your tracking branch

`git push` checks if there is a tracking branch for a remote repo connected to your local branch. 
If so, changes from the local branch and pushed to the remote branch. 
You can think of git push as "make the remote branch resemble my local branch". 
git push will fail if the remote branch has diverged from your local branch. If some commits in the remote branch are in your local branch, you should synchronize branches with git pull or git fetch and git merge.

Often `git push` and `git pull` are described as equivalent. This isn't entirely correct, since `git pull` does two things. 
`git pull` is a combination of `git fetch` immediately followed by `git merge`. 

`git fetch` again takes our current branch, and checks to see if there is a tracking branch. 
If so, it looks for changes in the remote branch, and pulls them into the tracking branch. 
Please note that git fetch does not update your local branch. 
To do that, you'll need to do `git merge origin/master` to merge those changes into your master branch.
git fetch is for users who wish to make sure they understand the changes they are merging into their branch before the merge happens.