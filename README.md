- [Git Quick Start](https://github.com/gonjumixproject/git_basic/blob/main/README.md#git-quick-start )
  * [How to set global user-pass values ](https://github.com/gonjumixproject/git_basic/blob/main/README.md#how-to-set-global-user-pass-values)
  * [How to clone a githup repro ](https://github.com/gonjumixproject/git_basic/blob/main/README.md#how-to-clone-a-githup-repro)
  * [How to set global user-pass values ](https://github.com/gonjumixproject/git_basic/blob/main/README.md#how-to-add-a-new-file-into-the-remote-github-repro)
- [Git Basic Commands](https://github.com/gonjumixproject/git_basic/blob/main/README.md#git-basic-commands)
  * [Starting a Project](https://github.com/gonjumixproject/git_basic/blob/main/README.md#starting-a-project)
  * [Adding Git to an existing Project](https://github.com/gonjumixproject/git_basic/blob/main/README.md#starting-a-project)
  * [Starting on Github by joining an existing Project](https//github.com/gonjumixproject/git_basic/blob/main/README.md#starting-a-project)
  * [Basic Git Workflow](https://github.com/gonjumixproject/git_basic/blob/main/README.md#basic-git-workflow)
  * [Tracked file](https://github.com/gonjumixproject/git_basic/blob/main/README.md#tracked-file)
  * [Editting file](https://github.com/gonjumixproject/git_basic/blob/main/README.md#editting-file)
  * [Recursive Add](https://github.com/gonjumixproject/git_basic/blob/main/README.md#recursive-add)
  * [Backing out changes](https://github.com/gonjumixproject/git_basic/blob/main/README.md#backing-out-changes)
  * [Renaming and Moving Files](https://github.com/gonjumixproject/git_basic/blob/main/README.md#renaming-and-moving-files)
  * [Deleting Files](https://github.com/gonjumixproject/git_basic/blob/main/README.md#deleting-files)
  * [History](https://github.com/gonjumixproject/git_basic/blob/main/README.md#history)
  * [Git Alias](https://github.com/gonjumixproject/git_basic/blob/main/README.md#git-alias)
  * [Ignoring unwanted files and folders](https://github.com/gonjumixproject/git_basic/blob/main/README.md#ignoring-unwanted-files-and-folders)
  * [Cleanup and back to origin](https://github.com/gonjumixproject/git_basic/blob/main/README.md#cleanup-and-back-to-origin)
  * 


# Git Quick Start

> Somae basic commands for quick start

## How to set global user-pass values
```
git config --global user.name "yourusername"
git config --global user.email "yourmail"
git config --global --list
```
## How to clone a githup repro
```
git clone https://github.com/gonjumixproject/git_basics.git
```
## How to add a new file into the remote github repro

```
/git/git_basics#vi lesson_1_quickstart.txt
/git/git_basics# git status
/git/git_basics#git add lesson_1_quickstart.txt
/git/git_basics#git commit -m "Added first text file"
/git/git_basics# git push
or
/git/git_basics# git push origin master
```

# Git Basic Commands

## Starting a Project
> Starting a github project without any source code 
> Create an empty project via git init.
```
/git# git init fresh_start
Initialized empty Git repository in /root/git/fresh_start/.git/
```
> Get into the project folder. The folder seems empty but git files will be in it.
```
~/git# cd fresh_start/
~/git/fresh_start# ls
~/git/fresh_start# ls -al
total 12
```
> Check the status of the project
```
~/git/fresh_start# git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
> Create a new file and check git status
```
~/git/fresh_start# vi firstfile.txt
~/git/fresh_start# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        firstfile.txt

nothing added to commit but untracked files present (use "git add" to track)

```
> Use git add command
```
~/git/fresh_start# git add firstfile.txt
~/git/fresh_start# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   firstfile.txt
```
> Use git commit command to fully add the file 
```
~/git/fresh_start# git commit
[master (root-commit) d37c0c4] this is my first file
 1 file changed, 1 insertion(+)
 create mode 100644 firstfile.txt
 ```

## Adding Git to an existing Project

Lets assume you have a source code in your local folder
```
~/newfolder# ls -al

08:14 .
08:14 ..
08:14 install.sh

~/newfolder# git init
Initialized empty Git repository in /root/newfolder/.git/

~/newfolder# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        install.sh
nothing added to commit but untracked files present (use "git add" to track)

~/newfolder# git add .
~/newfolder# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   install.sh

~/newfolder# git commit -m "my first commit, inline"
[master (root-commit) 39bf6a0] my first commit, inline
 1 file changed, 86 insertions(+)
 create mode 100755 install.sh
 
~/newfolder# git status
On branch master
nothing to commit, working tree clean


```

## Starting on Github by joining an existing Project
## Basic git workflow
## Tracked file
## Editting file
## Recursive Add
## Backing out changes
## Renaming and Moving Files
## Deleting Files
## History
## Git Alias
## Ignoring unwanted files and folders
## Cleanup and back to origin

