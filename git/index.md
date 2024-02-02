# Git cheatsheet


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

## Table of Contents
- [Configuration](#Configuration)
- [Aliases](#Aliases)
- [Create or clone repository](#Create-or-clone-repository)
- [Make changes](#Make-changes)
- [File operations](#File-operations)
- [Branches](#Branches)
- [Recovery](#Recovery)
- [Save fragments](#Save-fragments)
- [Synchronization](#Synchronization)
- [Submodules](#Submodules)
- [Other](#Other)



### Configuration
* Set default user name for commits for all repositories ```git config --global user.name "Jan Elznic"```
* Set default email for commits for all repositories ```git config --global user.email "jan@elznic.com"```
* Enables helpful colorization of command line output ```git config --global color.ui auto```
* Set user name for commits for specific repository ```git config user.name "Jan Elznic"```
* Set email for commits for specific repository ```git config user.email "jan.elznic@elzasoft.com"```


### Aliases
* Checkout ```git config --global alias.co checkout```
* Branch ```git config --global alias.br branch```
* Commit ```git config --global alias.ci commit```
* Status ```git config --global alias.st status```
* Unstage the file ```git config --global alias.unstage 'reset HEAD --'```
* Show last head ```git config --global alias.last 'log -1 HEAD'```


### Create or clone repository
* Clone repository to local computer ```git clone git@github.com:janelznic/cheatsheets.git```
* Create a new local repository ```git init project-name```


### Make changes
* Lists all new or modified files to be commited ```git status```
* Shows file differences not yet staged ```git diff```
* Snapshots the file in preparation for versioning ```git add index.js```
* Shows file differences between staging and the last file version ```git diff --staged```
* Unstages the file (but preserve its contents) ```git reset class.router.php```
* Commit (records file snapshots permanently in version history) ``` git commit -m "Commit message"```


### File operations
* Deletes the file from the working directory and stages the deletion ```git rm UserDetailComponent.tsx```
* Removes the file from version control but preserves the file locally ```git rm --cached debug.log```
* Changes the file name and prepares it for commit ```git mv [file-original] [file-renamed]```


### Branches
* Lists all branches in the current repository with last commits ```git branch -av```
* Show the current working branch with last commit ```git branch -v```
* Create a new branch ```git branch new-branch```
* Create a new branch and switch it ```git branch -m develop```
* Switch to the specified branch and update the working directory ```git checkout test```
* Combine the specified branch’s history into the current branch ```git merge hotfix/vulnerability-header```
* Delete a branch ```git branch -d feature/merged-branch```


### Recovery
* Undoes all commits afer commit, preserving changes locally ```git reset --soft 72fb9fc0d1d7fc0ce61d1a3378dac932cbdb2e33```
* :warning: Discards all history and changes back to the specified commit ```git reset --hard 72fb9fc0d1d7fc0ce61d1a3378dac932cbdb2e33```
* Make a list of the commits which are about to be rebased ```git rebase -i HEAD~1```
* Restart the rebasing process after having resolved a merge conflict ```git rebase --continue```
* Abort the rebase operation and reset HEAD to the original branch ```git rebase --abort```


### Save fragments
* Temporarily stores all modified tracked files ```git stash```
* Restores the most recently stashed files ```git stash pop```
* Lists all stashed changesets ```git stash list```
* Discards the most recently stashed changeset ```git stash drop```


### Synchronization
* Downloads all history from the repository bookmark ```git fetch upstream```
* Combines bookmark’s branch into current local branch ```git merge upstream/master```
* Uploads all local branch commits to GitHub ```git push origin develop```
* Downloads bookmark history and incorporates changes ```git pull```
* Setting up upstream to local repository ```git remote add upstream git@github.com:janelznic/insights-frontend-components.git```
* Show related remote repositories ```git remote -v```
* Rebase local repository with changes from remote repository ```git pull upstream/master --rebase```
* Rebase local repository with changes from specific remote repository ```git pull --rebase git@github.com:RedHatInsights/vulnerability-ui.git```


### Submodules
* Init submodules ```git submodule init```
* Checkout submodules ```git submodule update```
* Switch to the branch ```git submodule set-branch master```
* Create a module in host repo ```git submodule add git@github.com:easyadmin-system/easyadmin-frontend.git```
* Status ```git submodule status```


### Other
* Lists all ignored files in this project ```git ls-files --other --ignored --exclude-standard```
