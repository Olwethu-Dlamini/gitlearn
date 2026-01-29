mkdir grocery && cd grocery
git init
echo "<h1> Grocery</h1><ul><li>í½Ž Apples: $1.50</li><li>í½Œ Bananas: $0.75</li></ul>" > index.html
git add index.html
git commit -m "feat: launch produce section - live store open"
git checkout master
git branch -D develop               # deleted develop (was 669d9a3)
git log                             # showed only one commit on master

Connecting to remote (GitHub)

git remote add origin https://github.com/Olwethu-Dlamini/gitlearn.git
git remote -v
git status
git push origin master
git push -u origin master           # set upstream tracking

git checkout -b feature/add-bakery
git add .
git commit -m "feature: add bakery section "   # (nothing committed â€“ no changes staged)
git checkout develop                        # failed â€“ branch didn't exist yet

git checkout -b develop
git push -u origin develop
#Adding bakery items & merging to main
#(You added to index.html on develop or feature branch)
git push origin develop
git checkout master
git merge develop                           # fast-forward, added the 2 lines
git tag -a v1.0 -m "Bakery Section Opens"
git push origin master
git push origin v1.0

git branch -a
git status
git ls-remote --heads origin #check remote repo files
