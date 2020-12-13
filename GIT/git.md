
### List existing remotes
```
$ git remote -v
origin  https://github.com/sho1oms/DEVOPS.git (fetch)
origin  https://github.com/sho1oms/DEVOPS.git (push)
```
### Use HTTPS

```
$ git remote set-url https://link/repo.git
```
### Use SSH

```
git remote set-url git@link/repo.git
```

## Branch management


### Force push to remote repo

git push -f
gut push --force

Not recommeneded way to follow.

### Identity merged branches

* list branches that have been merge into  branch
* Usefull for knowing that feature have been incorporated
* Usefull for cleanup after merging many features


$ git branch --merged
$ git branch --no-merged

fadsa