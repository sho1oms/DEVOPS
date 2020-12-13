
## Configuration ssh keys git
Link:
https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


1. ssh-keygen -t rsa -b 4096 -C "piotrsobczak.wro@gmail.com
2. cat  ~/.ssh/id_rsa.pub
3. ssh-add ~/.ssh/id_rsa
4. eval $(ssh-agent -s)

Unable to git clone via ssh method.
1. Remove origin:
<p align="left">
  <img src="./screens/3.jpg" width="500" title="Problem solved">
  <p align="left">
  <img src="./screens/2.jpg" width="500" title="Problem solved">
</p>

Problem SOLVED:
<p align="left">
  <img src="./screens/1.jpg" width="500" title="Problem solved">
</p>


## BASIC commands

```
# New branch on origin
git push --set-upstream origin new-feature

```



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

### Delete local and remote branch

Delete branch LOCAL
```
# Delete branch - LOCAL
git branch -d new-feature

# Delete no merged branch - LOCAL
git branch -d new-feature
```

Delete branch - REMOTE

```
# Delete remote branch v1.7.0+
git push --delete origin new-feature

# Delete remote branch v2.8.0+
git push -d origin new-feature
```