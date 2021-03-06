### Start

**git init** - Create git repository here

**git clone url** - Clone repository from specific URL(HTTPS or SSH)

**git add .** - Add all unstaged files to index

**git commit -m "Commit message"** - Create commit from staged files with specific message

**git commit -a -m "Commit message"** - Create commit from all unstaged  files with specific message

### Remote repo

**git push remoteName localBranchName** - Push commits to remote repo for example _origin_ from local branch for example _master_

**git pull remoteName localBranchName** - Pull changes from remote repo for example _origin_ to local branch for example _master_
	(use --rebase if you don't want merge commit, it change base of commits in your local repo to last from remote)

**git remote -v** - Show remote repos

**git remote set-url remoteName url** - Set(change) url for specific remote repo

### Undo changes

**git checkout -- .** - Remove all unstaged changes(checkout to last commit)

**git clean -fd** - Remove all untracked files and directories(use -n to see what would be removed)

**git reset HEAD** - Remove current branch staged changes and create unstaged changes(--hard remove unstaged changes too)

**git reset HEAD~1** - Remove last commit and checkout HEAD to previous commit or specific commit if you write id of commit

**git revert -n idOfCommit** - Revert changes of specific commit and not creating commit of it revert(_-n_)

### History

**git log -3 --pretty=short --stat** - Show history of three last commits in short view(Commit hashcode, Author, message) 

**git log --pretty=format:'%Cgreen %h %Creset %an %ai %Cgreen %s'** - Some custom format of log output

**git log -1 -p** - Show last commit with diff

**git log --since="date" --after="date"** - Show range of history, date may be like "_11/01/2016_" or "_2 weeks ago_"

### Diff

**git diff --cached** - Changes between index(staged) and last commit

**git diff HEAD** - Changes in working tree(unstaged) and last commit 

**git diff HEAD^ HEAD** - Show diff of commit before last commit and last commit

**git diff master branchName** - Changes between master and branch. _Right-side_ is result of compare

**git diff --name-status** - Show only file names and status of diff

### Branches

**git checkout -b branchName** - Create branch and switch to that branch

**git checkout branchName** - Switch to specific branchName

**git branch -a** - Show all branches(local nad remotes)

**git log --all --decorate --oneline** - Show all commits from all local branches in oneline view

**git branch -d branchName** - Delete specific branchName

### Merge

**git merge branchName** - Merge current branch with branchName

**git mergetool** - Open merge tool if merge done with conflict
	Config of kdiff3 merge tool:
	Add to _~/.gitconfig_

    [merge]
        tool = kdiff3

        [mergetool "kdiff3"]
            path = C:/Program Files/KDiff3/kdiff3.exe
            keepBackup = false
            trustExitCode = false

### Stash

**git stash** - Add all unstaged and staged changes to stash stack(after this, you can push or pull or merge, without adding your stashed changes to commit)

**git apply** - Apply recent stash from stack(all files will be unstaged)

### Aliases

**git config --global alias.plo 'pull origin'** - Add alias of _pull origin_ to global config, another way is edit _~/.gitconfig_:

    [alias]
            pso = push origin
            ploreb = pull --rebase origin
            st = status
            lg = log --pretty=format:'%Cgreen %h %Creset %an %ai %Cgreen %s'
	    chkmst = checkout master
	    df-lt = diff HEAD~1 HEAD
