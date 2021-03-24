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

Lets assume you have a source code in your local folder.

You source code does not have any .git folder, means that this is not a github project
```
~/newfolder# ls -al

08:14 .
08:14 ..
08:14 install.sh
```
Initiate a gothub project by git init
```
~/newfolder# git init
Initialized empty Git repository in /root/newfolder/.git/
```
Check the git status;

```
~/newfolder# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        install.sh
nothing added to commit but untracked files present (use "git add" to track)
```
Add the files into the git project
```
~/newfolder# git add .
~/newfolder# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   install.sh
```
Perform the git commit
```
~/newfolder# git commit -m "my first commit, inline"
[master (root-commit) 39bf6a0] my first commit, inline
 1 file changed, 86 insertions(+)
 create mode 100755 install.sh
 
~/newfolder# git status
On branch master
nothing to commit, working tree clean
```

## Starting on Github by joining an existing Project
First one project over the github page, and from your profile go to the forked repro and clone the project to your local.

```
~/git# git clone https://github.com/gonjumixproject/iptv.git
```
Get into the file via "cd"

```
~/git# cd iptv/
```
Check the git files
```
~/git/iptv# ls -al

  4096 Mar 24 08:35 .
  4096 Mar 24 08:34 ..
  4096 Mar 24 08:35 .git
  4096 Mar 24 08:35 .github
   134 Mar 24 08:35 .gitignore
  4096 Mar 24 08:35 .readme
 20151 Mar 24 08:35 CONTRIBUTING.md
  1211 Mar 24 08:35 LICENSE
 60992 Mar 24 08:35 README.md
  4096 Mar 24 08:35 channels
  5495 Mar 24 08:35 index.m3u
  7620 Mar 24 08:35 package-lock.json
   407 Mar 24 08:35 package.json
  4096 Mar 24 08:35 scripts
  
```
Check git status;

```
/git/iptv# git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```


## Basic git workflow


The "git status" command, moving forward, will tell us the difference between the working directory, Git's staging area, the actual Git repository that is on the local system, as well as how that compares to the remote repository.
```
==================================== Local ================== // ================== Remote (GitHub Server)==================
Working Directory >> Staging Area >> Repository (.git folder) 
```


Create a new file, in your local, and then use git status; "nothing added to commit but untracked files present"
```
~/git/iptv# vi test.txt
~/git/iptv# git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.txt

nothing added to commit but untracked files present (use "git add" to track)
```
Use git add file to put the file into the staging area. When you used "git add" but did not committed any commit yet, the file will be in the staging area;
This file is not yet committed, but its something that git is tracking, and its awaiting the next commit.
```
~/git/iptv# git add test.txt

~/git/iptv# git status
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.txt
```
Git commit command returns "master" which is the current branch that it commits, and then "02451dcd" which is a SHA-1 which is a unique identifier for the commit. 
```
~/git/iptv# git commit -m "my first commit"
[master 02451dcd] my first commit
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
```
When you do a commit, everything in the staging area is committed, and added to the local repro.
```
~/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

So for now, a "git push" command needs to be performed to publish every file in our local workspace staging area to github remote server. 

But before that "git push" command, we will perform "git pull origin master". This will update our repro with any changes that may have happend on the remote repro down to our local repro, just to make sure we're up tp date before we do any pushes back up to our remote repro.

```
~/git/iptv# git pull origin master
From https://github.com/gonjumixproject/iptv
 * branch              master     -> FETCH_HEAD
Already up to date.
```

Now we will perform a "git push"

```
~/git/iptv# git push origin master
Username for 'https://github.com': gonjumixproject
Password for 'https://gonjumixproject@github.com':
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 297 bytes | 297.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/gonjumixproject/iptv.git
   c5913061..02451dcd  master -> master
```
Go back to your browser and check your github repro on the github page to make sure the file is there.

## Tracked file
Add new lines to your example test file;
```
:~/git/iptv# vi test.txt
```
Check the git status;
```
~/git/iptv# git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
You can shortly both add and commit in one line; 
```
:~/git/iptv# git commit -am "this is my second commit"
[master db1d5c1d] this is my second commit
 1 file changed, 1 insertion(+)

```
A tracked file is any file that Git is aware of and tracking actively. That would be any file that has already been committed into the Git repository,or any file that has been added to the Git index, or the Git staging area.

git ls-files will list all the tracked files.

```
~/git/iptv# git ls-files

```
## Editting file

When you modified a file, to you need to perform an add and commit to put that modified file into the staging area;

```
~/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test.txt

```

To put that into the staging area, you need to perform only "git add". If you want to add it into the local repro, you need to perform a commit. 

You can do the both via "git commit -am "

```
~/git/iptv# git commit -am "modifed another line"
[master c9a3a2da] modifed another line
 1 file changed, 1 insertion(+), 1 deletion(-)
```


## Recursive Add

Lets assume you added a recursive direcorty into your git repro. 

```
lvl1/
├── lvl1.txt
└── lvl2
    ├── lvl2.txt
    └── lvl3
        └── lvl13.txt
```

When you check the git status, you will only see the top directory for the new added files/folder.
```
~/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        lvl1/

nothing added to commit but untracked files present (use "git add" to track)
```
To track all those files recursively you need to perform perform below;

```
~/git/iptv# git add .
```
With the add command that file will be placed as staged.
```
~/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   lvl1/lvl1.txt
        new file:   lvl1/lvl2/lvl2.txt
        new file:   lvl1/lvl2/lvl3/lvl13.txt

```
You can perform a commit to put them into your repro. 
```
~/git/iptv# git commit -m "adding several files recursively"
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
## Backing out changes
## Renaming and Moving Files
## Deleting Files
## History
## Git Alias
## Ignoring unwanted files and folders
## Cleanup and back to origin

