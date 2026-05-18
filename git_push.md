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
> switch to another branch and check it out into your working directory
```
git checkout [branch-name]
```
> merge the specified branch’s history into the current one
```
git merge [branch]
```
> show all commits in the current branch’s history
```
git log
```

