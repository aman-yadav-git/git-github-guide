# git push command

## Push Your Folder & file to GitHub
 
**Run these commands from your home directory (~) so that the folder & file**
> Initialize an existing directory as a Git repository
``
git init 
``
> show modified files in working directory, staged for your next commit
```
git status
```
> add a file as it looks now to your next commit (stage)
```
git add (file or folder)
```
> unstage a file while retaining the changes in the working directory
```
git reset (file or folder)
```
> diff of what is changed but not staged
```
git diff
```
> diff of what is staged but not yet committed
```
git diff --staged
```
> commit your staged content as a new commit snapshot
```
git commit -m “[descriptive message]”
```
> list your branches. a * will appear next to the currently active branch
```
git branch
```
```
git branch -a
```
> switch to another branch and check it out into your working directory
```
git checkout [branch-name]
```
```
git checkout -b main origin/main 
```
> merge the specified branch’s history into the current one
```
git merge [branch]
```
> show all commits in the current branch’s history
```
git log
```
```
git log --oneline --all --graph
```
```
git log --oneline
```
> show the commits on branchA that are not on branchB
```
git log branchB..branchA
```
show the commits that changed the file even across renames
```
git log --follow [file]
```
> show any object in Git in human-readable format
```
git show
```
> delete the file from project and stage the removal for commit
```
git rm [file]
```
> change an existing file path and stage the move
```
git mv [existing-path] [new-path]
```
> show all commit logs with indication of any paths that moved 
```
git log --stat -M
```
> add a git URL as an alias
```
git remote add [alias] [url]
```
> fetch down all the branches from that Git remote
```
git fetch [alias]
```
> merge a remote branch into your current branch to bring it up to date
```
git merge [alias]/[branch]
```
> Transmit local branch commits to the remote repository branch
```
git push [alias] [branch]
```
```
git push origin main
```
> fetch and merge any commits from the tracking remote branch
```
git pull
```











