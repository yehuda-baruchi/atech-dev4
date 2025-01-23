**Git Basic commands**
- Create new file then add,commit it and see the status of each steps

```
echo "my new file" > newfile.txt
ls
git status
git add newfile.txt
cat newfile.txt
git status
git commit -m "new file"
git status
```
- **Git mv** move or rename files
- **Git log** display the commit history
- **Git diff** see the differences between commits ​
```
git mv newfile.txt newfile01.txt
git status
git commit -m "rename"
git log
git log --graph --decorate
git log --oneline
git diff 61f2e9a 55b1459
```
- **Git reset** It's commonly used to undo changes

    - git reset HEAD             unstages the specified file(s) from the staging area, but keeps the changes in your work dir​
```
vi newfile01.txt
git status
git reset HEAD newfile01.txt
git status
git commit -m "noting to commit, since This command unstages the specified file(s) from the staging area, but keeps the changes in your working directory​"
git add newfile01.txt
git commit -m "now you can commit it after to add the file"
git status
```
  - git reset --soft HEAD~1    Undo Commit and Keep Changes
```
vi newfile01.txt
git log --oneline newfile01.txt
git status
git reset --soft HEAD~1
git log --oneline newfile01.txt       # undo commit, see the diff of commit before and after the reset soft command
cat newfile01.txt
git status
git add -A
git status
git commit -m "reset soft"
git status
gitk
gitk --all
git log --oneline newfile01.txt
git log --graph --pretty='%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --all
```
  - git reset --hard HEAD~1    Undo Commit and Discard Changes Completely
```
vi newfile01.txt
git log --oneline newfile01.txt
git status
git add -A
git commit -m "reset hard"
git status
git log --oneline newfile01.txt
cat newfile01.txt
git reset --hard HEAD~1           # undo commit and undo changes
git status
cat newfile01.txt
git log --oneline newfile01.txt
```
- **Git rm** remove files from the working directory and the index (staging area)​
  - git rm --cached [file] removes the file from the index but leaves it in the working directory​
  - git rm -f [file] - use rm –f If you want to remove files from both the repository and your file system
```
vi rmfile.txt
ls
git status
git add -A
git commit -m "rm cached"
git status
git rm --cached rmfile.txt         # rm from index but leave it in wd
git status
cat rmfile.txt
git add -A
git commit -m "rm cached"
git status
git rm -f rmfile.txt               # rm files from index and wd
git status
ls
```
