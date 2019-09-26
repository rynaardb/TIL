# Git

## Basics

**Set username and email**

Globally (for every repository):

`git config --global user.name "Rynaard Burger"`
`git config --global user.email "ryno.burger@gmail.com"`

For a single repository:

`git config user.name "Rynaard Burger`
`git config user.email "ryno.burger@gmail.com`

*Omit the last part to print the current values i.e. git config user.email*

**Initialize a new repository**
`git init`

**Add a remote**

`git remote add origin git@github.com:rynaardb/munich-kvr-termin-bot.git`

**Get status**

`git status`

**Checking out a branch**

`git checkout BRANCH_NAME`

**Staging files**

`git add .` or `git add FILENAME`

**Commit**

`git commit -m "COMMIT_MESSAGE"`

`git commit --amend` modify most recent commit

`git reset --soft HEAD~1` undo last commit

`git commit --amend -m "New commit message"` ammend last commit message

**Tags**

`git tag` list all tags

`git tag -a 1.0 -m "version 1.0"` tag a commit

**Pushing**

`git push` or or `git push origin BRANCH_NAME`

**Fetching**

`git fetch` or or `git fetch origin BRANCH_NAME`

**Pulling**

`git pull` or `git pull origin BRANCH_NAME`

Pull from master on the main repo in when working with forks:

`git pull upstream BRANCH_NAME`

## Stashing

**Stash current changes**

`git stash`

**Pop the last stashed changes**

`git stash pop`

## Reset

**Hard reset to a specific commit**

`reset --hard COMMIT_ID`

Typically followed by a forced push:

`push --force origin BRANCH_NAME`

`git cherry-pick COMMIT_ID` cherry pick a specific commit

## Cherry Pick

`git cherry-pick hash_commit_A hash_commit_B` add some commits to the top of the current branch

## Misc

**Clean cache**

`git clean -dfx`

**Create a diff patch**

`git diff > myDiffPatch.patch`

`git diff tag1..tag2 > myDiffPatch.patch` (generates a patch between two tags)

`git apply --stat myDiffPatch.patch` (only shows the stats, does not apply the actual changes)

`git apply myDiffPatch.patch` apply a patch

`git grep "someString" ..` find something in the history
