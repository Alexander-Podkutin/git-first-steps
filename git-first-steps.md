### Start

**git init** - Create git repository here

**git clone url** - Clone repository from specific URL(HTTPS or SSH)

**git add .** - Add all ustaged files to index

**git commit -m "Commit message"** - Create commit from staged files with specific message

**git commit -a -m "Commit message"** - Create commit from all unstaged  files with specific message

### Remote repo

**git push remoteName localBranchName** - Push commits to remote repo for example _origin_ from local branch for example _master_

**git pull remoteName localBranchName** - Pull changes from remote repo for example _origin_ to local branch for example _master_
	(use --rebase if you don't want merge commit, it change base of commits in your local repo to last from remote)

**git remote -v** - Show remote repos

**git remote set-url remoteName url** - Set(change) url for specific remote repo


