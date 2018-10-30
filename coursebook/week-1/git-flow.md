# Git Flow:

## Doing some work

- `git pull origin master` - get the most up to date version of master
- `git checkout -b my-branch` - make and checkout to a new branch
- \**make changes\**
- `git add [FILES CHANGED]`
- `git commit -m "my commit message here, relates #10"` - commit changes
- `git push origin my-branch` - this pushes the branch up to the remote

## When ready to make a PR

- `git checkout master`
- `git pull origin master` get newest version of master
- `git checkout my-branch`
- `git merge master` merge my branch with master *locally*
- \**solve merge conflicts in editor\**
- `git push origin my-branch` - this pushes the branch up to the remote
- Go to Github, and open PR
- Wait for team mates to Review :tada: 
