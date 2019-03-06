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

**Get status**

`git status`

**Checking out a branch**

`git checkout BRANCH_NAME`

**Staging files**

`git add .` or `git add FILENAME`

**Commit**

`git commit -m "COMMIT_MESSAGE"`

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

## Misc

**Clean cache**

`git clean -dfx`
