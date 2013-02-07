Git Notes
=================

`git add -n .` dry run is -n option

### exclude file:
.git/info/exclude

### removing added files:
`git rm --cached FILE` (don't forget the cached!)

## git workflow:

`git clone http://git.something.org/project/title.git` (checks out master branch)

`git add <FILES>` (use . for all, git add -n FILES for mock)

`git status`

`git commit -m "message text"` (local commit)

Make sure SSH is setup (add public key to the repo, private in local .ssh folder)

`git push REPOSITORY` (where REPOSITORY is either a remote URL or a name of a remote, which are specified in GIT/config, GIT/remotes, or GIT/branches)

generally we'll just want to push to origin... which is what is conventually the primary centralized repo (a github account for example)

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
