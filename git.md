### Initialize GIT
```
git config --global user.name "Mohamad El Bayat"
git config --global user.email mbayat@outlook.com
git config --global init.default branch main
```
### Add GIT to Project
```
cd myProject
git init
```
### Basic Commands
```
git status
git add index.php
git add .
git rm --cached index.php
git commit -m "First Commit"
```
### Branches
```
git branch
git branch testing
git switch testing
```
Merge
```
git switch master
git merge -m "Merge testing branch changes" testing
```
### Reset
```
git reset --hard origin/master
```