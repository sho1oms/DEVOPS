
## Configuration ssh keys git

https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


1. ssh-keygen -t rsa -b 4096 -C "piotrsobczak.wro@gmail.com
2. cat  ~/.ssh/id_rsa.pub
3. ssh-add ~/.ssh/id_rsa
4. eval $(ssh-agent -s)

Problem SOLVED:
<p align="left">
  <img src="./screens/1.JPG" width="500" title="Problem solved">
</p>

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