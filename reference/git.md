Git Notes
=================

## Basic Workflow

1. 'Git' a repo
    * Clone `git clone <REPO-URL>`
    * Checkout `git checkout`
    * Init `git init` (inside directory)

2. Make modifications
    * Add modifications to staging `git add <FILE>` or `git add .` (all)
    * Remove
        * Stage file removal `git rm <FILE>`
        * Remove from staging `git rm --cached <FILE>`
    * Moving `git mv <OLD> <NEW>`

3. Branching
    * View branches `git branch`
    * Create `git branch new_branch_name`
    * merging another branch with current branch `git merge another_branch`
    * Deleting a branch that's fully merged 'git branch -d branch_name'
    * Deleting a branch that's not ... getting rid of branch changes `git branch -D branch_name`

4. Commit
    * Commit with message `git commit -m 'Commit Message'`
    * Commit without staging `git commit -am 'Committing msg'` (Adds all untracked content to staging)

5. Check Status/Log
    * `git status`
    * `git diff` or `git diff --staged` View differences between untracked & staged, or staged and local
    * `git log` Check history (-p shows diff, -2 shows last two entries, --stat)
        * Options
            * -p shows diff
            * -2 shows last two entries
            * `--stat`
            * `--pretty=oneline`
                * also `--pretty=format:"%cd %s %cn"` (commiter date, subject and committer name)
            * `--graph`

6. Pushing/Syncing with another rep

    * `git push REPOSITORY` (where REPOSITORY is either a remote URL or a name of a remote, which are specified in GIT/config, GIT/remotes, or GIT/branches)

## Most Used options/commands

* `git add -n .` dry run is -n option

### Making changes in a submodule, committing it, and updating the main git repo

1. Make sure on proper branch `git branch` or change to master
2. Make modifications in submodule code (merge into master branch if forgot step 1)
3. Add and commit changes
4. `git push`
5. Got to main git repo
6. `git add /path/to/sub`
7. `git commit -m "Updated commit reference"`
8. `git push`

### Ignoring files

* .git/info/exclude
* .gitignore

## Pushing after a fresh init:

REMOTE:

* ssh into git (`ssh -T -p 443 git@github.com`)
* `mkdir my_project.git`
* `cd my_project.git`
* `git init --bare`
* `exit`

LOCAL:

* `git init`
* `git add *`
* `git commit -m 'initial commit'`
* `git remote add origin git@example.com:my_project.git`
* `git push -u origin master`


* `git remote` (show's what's configured as remote repos)
* `git remote show origin` (shows more info about a particular repo ... origin in this case)

## Misc

* `gitk` git ui visualizer
