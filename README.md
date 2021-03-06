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
- [Comprasions](https://github.com/gonjumixproject/git_basic/blob/main/README.md#comprasions)
  * [Comparing working directory and staging area and git repro](https://github.com/gonjumixproject/git_basic/blob/main/README.md#comparing-working-directory-and-staging-area-and-git-repro)
  * [Comparing the commits](https://github.com/gonjumixproject/git_basic/blob/main/README.md#comparing-the-commits)
  * [Comparing between local and remote master branches](https://github.com/gonjumixproject/git_basic/blob/main/README.md#comparing-between-local-and-remote-master-branches)
- [Rebasing](https://github.com/gonjumixproject/git_basic#git-rebase)
  * [Simple Rebase Example](https://github.com/gonjumixproject/git_basic#create-rebase-conflict)
  * [Use Rebase over the Conflict / Abort the Rebase](https://github.com/gonjumixproject/git_basic#use-rebase-over-the-conflict--abort-the-rebase)
  

 


# Git Quick Start

Some basic commands for quick start

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

create a new file with vi
<pre>/git/git_basics# vi lesson_1_quickstart.txt </pre>

check the git status, add the file into the working dir, push the changes to github.
```
/git/git_basics# git status
/git/git_basics# git add lesson_1_quickstart.txt
/git/git_basics# git commit -m "Added first text file"
/git/git_basics# git push
or
/git/git_basics# git push origin master
```
# Git Basic Commands

## Starting a Project
Starting a github project without any source code 
Create an empty project via git init.
```
/git# git init fresh_start 
Initialized empty Git repository in /root/git/fresh_start/.git/
```
Get into the project folder. The folder seems empty but git files will be in it.
```
/git# cd fresh_start/

/git/fresh_start# ls

/git/fresh_start# ls -al
total 12
```
Check the status of the project
```
/git/fresh_start# git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
 Create a new file and check git status
```
/git/fresh_start# vi firstfile.txt
/git/fresh_start# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        firstfile.txt

nothing added to commit but untracked files present (use "git add" to track)

```
 Use git add command
```
/git/fresh_start# git add firstfile.txt
/git/fresh_start# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   firstfile.txt
```
> Use git commit command to fully add the file 
```
/git/fresh_start# git commit
[master (root-commit) d37c0c4] this is my first file
 1 file changed, 1 insertion(+)
 create mode 100644 firstfile.txt
 ```

## Adding Git to an existing Project

Lets assume you have a source code in your local folder.

You source code does not have any .git folder, means that this is not a github project
```
/newfolder# ls -al

08:14 .
08:14 ..
08:14 install.sh
```
Initiate a gothub project by git init
```
/newfolder# git init
Initialized empty Git repository in /root/newfolder/.git/
```
Check the git status;

```
/newfolder# git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        install.sh
nothing added to commit but untracked files present (use "git add" to track)
```
Add the files into the git project
```
/newfolder# git add .
/newfolder# git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   install.sh
```
Perform the git commit
```
/newfolder# git commit -m "my first commit, inline"
[master (root-commit) 39bf6a0] my first commit, inline
 1 file changed, 86 insertions(+)
 create mode 100755 install.sh
 
/newfolder# git status
On branch master
nothing to commit, working tree clean
```

## Starting on Github by joining an existing Project
First one project over the github page, and from your profile go to the forked repro and clone the project to your local.

```
/git# git clone https://github.com/gonjumixproject/iptv.git
```
Get into the file via "cd"

```
/git# cd iptv/
```
Check the git files
```
/git/iptv# ls -al

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
/git/iptv# vi test.txt
/git/iptv# git status
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
/git/iptv# git add test.txt

/git/iptv# git status
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.txt
```
Git commit command returns "master" which is the current branch that it commits, and then "02451dcd" which is a SHA-1 which is a unique identifier for the commit. 
```
/git/iptv# git commit -m "my first commit"
[master 02451dcd] my first commit
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
```
When you do a commit, everything in the staging area is committed, and added to the local repro.
```
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

So for now, a "git push" command needs to be performed to publish every file in our local workspace staging area to github remote server. 

But before that "git push" command, we will perform "git pull origin master". This will update our repro with any changes that may have happend on the remote repro down to our local repro, just to make sure we're up tp date before we do any pushes back up to our remote repro.

```
/git/iptv# git pull origin master
From https://github.com/gonjumixproject/iptv
 * branch              master     -> FETCH_HEAD
Already up to date.
```

Now we will perform a "git push"

```
/git/iptv# git push origin master
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
/git/iptv# vi test.txt
```
Check the git status;
```
/git/iptv# git status
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
/git/iptv# git commit -am "this is my second commit"
[master db1d5c1d] this is my second commit
 1 file changed, 1 insertion(+)

```
A tracked file is any file that Git is aware of and tracking actively. That would be any file that has already been committed into the Git repository,or any file that has been added to the Git index, or the Git staging area.

git ls-files will list all the tracked files.

```
/git/iptv# git ls-files

```
## Editting file

When you modified a file, to you need to perform an add and commit to put that modified file into the staging area;

```
/git/iptv# git status
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
/git/iptv# git commit -am "modifed another line"
[master c9a3a2da] modifed another line
 1 file changed, 1 insertion(+), 1 deletion(-)
```


## Recursive Add

Lets assume you added a recursive direcorty into your git repro. 

```
lvl1/
????????? lvl1.txt
????????? lvl2
    ????????? lvl2.txt
    ????????? lvl3
        ????????? lvl13.txt
```

When you check the git status, you will only see the top directory for the new added files/folder.
```
/git/iptv# git status
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
/git/iptv# git add .
```
With the add command that file will be placed as staged.
```
/git/iptv# git status
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
/git/iptv# git commit -m "adding several files recursively"
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
## Backing out changes

Lets add some new lines into the lvl1.txt file, and perform a git status;
```
/git/iptv/lvl1# git status
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   lvl1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
Lets put them into the staging area 
```
/git/iptv/lvl1# git status
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   lvl1.txt
```
But now you think that this file should not be committed yet, should be unstaged. You will be back to the "modified state"
```
/git/iptv/lvl1# git restore --staged lvl1.txt
/git/iptv/lvl1# git status;
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   lvl1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
You can also perform following command for the same;
```
/git/iptv/lvl1# git reset HEAD lvl1.txt
Unstaged changes after reset:
M       lvl1/lvl1.txt

/git/iptv/lvl1#  git status;
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   lvl1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
Once the file is unstaged, you can directly go back to the previous-unmodified file as below;

```
/git/iptv/lvl1# git status
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

```


## Renaming and Moving Files

With the "git mv" command you will be able to rename the file, and git will be staged that file but it will be not committed. So you can backuout the renaming.
```
/git/iptv/lvl1/lvl2/lvl3# git mv lvl13.txt lvl13_1.txt
/git/iptv/lvl1/lvl2/lvl3# ls -l
total 4
-rw-r--r-- 1 root root 18 Mar 24 10:00 lvl13_1.txt
git/iptv/lvl1/lvl2/lvl3# git status
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    lvl13.txt -> lvl13_1.txt
```

If I change the name of the file via using the bash "mv" command, git will get that operation as two operations.
```
/git/iptv/lvl1/lvl2# git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    lvl2.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        lvl2_1.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
-A will update any files renamed/moved or deleted.
```
/git/iptv/lvl1/lvl2# git add -A
/git/iptv/lvl1/lvl2# git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    lvl2.txt -> lvl2_1.txt
```
If i want to backout the git rename, then I will need to use the git mv command to directly change the name back to old name;
```
/git/iptv/lvl1/lvl2# git mv lvl2_1.txt 2.txt
/git/iptv/lvl1/lvl2# ls
2.txt  lvl3
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/iptv/lvl1/lvl2# git status
On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    lvl2_1.txt -> 2.txt
```

If i rename it back to old file name, git status will not detect any changes.
```
/git/iptv/lvl1/lvl2# git mv 2.txt lvl2_1.txt
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/iptv/lvl1/lvl2# git status
On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)
```
Move the file via git mv
```
/git/iptv/lvl1/lvl2# git mv lvl2_1.txt lvl3/
/git/iptv/lvl1/lvl2# git status
On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    lvl2_1.txt -> lvl3/lvl2_1.txt

/git/iptv/lvl1/lvl2# cd lvl3/
:/git/iptv/lvl1/lvl2/lvl3# git status
On branch master
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    ../lvl2_1.txt -> lvl2_1.txt

/git/iptv/lvl1/lvl2/lvl3# cd ../
/git/iptv/lvl1/lvl2# git commit -m "moving file"
[master 8cb12ab5] moving file
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename lvl1/lvl2/{ => lvl3}/lvl2_1.txt (100%)

nothing to commit, working tree clean
```

## Deleting Files

If you try to remove an untracked file via "git rm", git will not able to find. so you need to use "rm" for untracked files.
```
/git/iptv# vi test2.txt
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 8 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test2.txt

nothing added to commit but untracked files present (use "git add" to track)
/git/iptv# git rm test2.txt
fatal: pathspec 'test2.txt' did not match any files
```

List all the tracked files, and use "git rm" to remove a tracked file. The delete will be staged, but you need to perform a commit to make it permanent.
```
/git/iptv# git ls-files
..
/git/iptv# git rm test.txt
rm 'test.txt'
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 8 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    test.txt
/git/iptv# git commit -m 'deleting this file'

```
Backout the deletion : git restore command will unstaged the deletion, it will not restore the file to the file system. You need to perform "git checkout" command to do that.

```
/git/iptv# git add newfile
/git/iptv# git commit -m "a new fil"
/git/iptv# git rm newfile
rm 'newfile'
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    newfile

/git/iptv# git restore --staged newfile
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    newfile

no changes added to commit (use "git add" and/or "git commit -a")
/git/iptv#  git checkout -- newfile
```

If you remove a tracked file without using the "git rm" commands. You can backout the rm command like in the previous section. (git checkout)
```
/git/iptv# rm newfile
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    newfile

no changes added to commit (use "git add" and/or "git commit -a")
:/git/iptv# git add -A
```
## History

```
/git/iptv# git log
commit 1e999c1d120c35bb6cca253c60faee4dd6d38c52 (HEAD -> master)
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:29:48 2021 +0000

    a new fil
```

The commit line has been shortened;
```
/git/iptv# git log --abbrev-commit


commit 54645127
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:03:41 2021 +0000

    renaming the file
```

```
/git/iptv# git log --oneline --graph --decorate

* 1e999c1d (HEAD -> master) a new fil
* 4a98b1e8 deleting this file
* d165b73f mving the file back
* 8cb12ab5 moving file
* 15d001b2 renaming lvl2 file
* 54645127 renaming the file
* bf84c36b iadding several file rev<U+0080>kbcursivelyU+0080>??a:wq^M:wq^MU+0080>??a:q!
* c9a3a2da modifed another line
* 81d3ac9b modifed a line
* db1d5c1d this is my second commit
* 02451dcd (origin/master, origin/HEAD) my first commit
*   c5913061 Merge branch 'master' of https://github.com/iptv-org/iptv
|\
| * 2299ed59 [Bot] Format playlists
* | 9f1caa36 [Bot] Update README.md
```

Only specified commits;
```
/git/iptv# git log d165b73f...54645127
commit d165b73f81445c309af4b3c67eb9cc9a664eaf75
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:16:12 2021 +0000

    mving the file back

commit 8cb12ab55d7043defd497b014675070611156035
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:13:50 2021 +0000

    moving file

commit 15d001b24f6d4813d65033695b28bb1340a2dc33
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:08:44 2021 +0000
```

Date specified history;

```
:/git/iptv# git log --since="3 days ago"

commit bf84c36b1412c02b08fc4a8eb0d72ed6419e000b
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 09:40:50 2021 +0000

    iadding several file rev<U+0080>kbcursivelyU+0080>??a:wq^M:wq^MU+0080>??a:q!

commit c9a3a2da4c0ae320b14679f2ccecb144b7eac189
Author: gonjumixproject <gonjmixproject@gmail.com>
```
File specified history;

```
/git/iptv# git log -- newfile
commit 1e999c1d120c35bb6cca253c60faee4dd6d38c52 (HEAD -> master)
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:29:48 2021 +0000

    a new fil
```

Will show the latest file detailed histroy;
```
/git/iptv# git show
commit 1e999c1d120c35bb6cca253c60faee4dd6d38c52 (HEAD -> master)
Author: gonjumixproject <gonjmixproject@gmail.com>
Date:   Wed Mar 24 10:29:48 2021 +0000

    a new fil

diff --git a/newfile b/newfile
new file mode 100644
index 00000000..e69de29b
```
## Git Alias

Will create a shorter command as alias named "hist" for "log --all --graph --decorate --oneline" command;

```
 /git/iptv#git config --global alias.hist "log --all --graph --decorate --oneline"
 /git/iptv#git hist
 
 /git/iptv# vi /.gitconfig
 [alias]
        hist = log --all --graph --decorate --oneline
 ```
 
 
## Ignoring unwanted files and folders

Editting ".gitignore" file will be helpfull for that;
```
.gitignore
```

## Cleanup and back to origin

We have 10 commits ahead from the original thing;
```
/git/iptv# git status
On branch master
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```
Push the changes to the github
```
/git/iptv# git pull origin master
From https://github.com/gonjumixproject/iptv
 * branch              master     -> FETCH_HEAD
Already up to date.
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/iptv# git push origin master
Username for 'https://github.com': gonjumixproject
Password for 'https://gonjumixproject@github.com':
Enumerating objects: 39, done.
Counting objects: 100% (39/39), done.
Compressing objects: 100% (30/30), done.
Writing objects: 100% (37/37), 2.96 KiB | 433.00 KiB/s, done.
Total 37 (delta 11), reused 1 (delta 0)
remote: Resolving deltas: 100% (11/11), completed with 1 local object.
To https://github.com/gonjumixproject/iptv.git
  02451dcd..1e999c1d  master -> master
```


# Comprasions

## Comparing working directory and staging area and git repro
```
To add the changes into the staging area, you need to perform : Git Add 
To add the staging area docs into git repro in your local : Git Commit
To add the git repro to the git local server : Git Push
To get the latest updates from the git local server : Git Pull

To see the differences between the staging area (latest add command) and working space : ``` git diff or git difftool```
To see the differences between the git repro ( latest commit command) and working space :```  git diff HEAD or git difftool HEAD ``` 
To see the differences between the staging area ( latest add commad ) and git repro ( last commit) : ``` git diff --staged HEAD or git difftool --staged HEAD```
```
## Comparing the commits

You will need to get the commit ID and check the diff of them, you can also use git difftool

```
/git/git_basic# git log --oneline
7c6991a (HEAD -> main, origin/main, origin/HEAD) new changes
cc11bb2 new changes
d9ccce5 adding new sections
/git/git_basic# git diff 7c6991a cc11bb2

/git/git_basic#  git diff HEAD 24d9992

```

## Comparing between local and remote master branches

Master is your local repro under your comp
Origin/master is your remote repro in github server

```
git diff master origin/master
```

If you receive a fatal error, most probably thats because your branch name is not "master" but its something else instead. Follow below stackoverflow link for the solution.

```
https://stackoverflow.com/questions/45096755/fatal-ambiguous-argument-origin-unknown-revision-or-path-not-in-the-working
```

# Branching and Merging

## Branching basics

We were doing all the changes on "master" branch, which is not a good practice.
We should be doing is seperate our changes into brances, that makes more sense, to isolate our changes.

Check you current brach;
```
git status
```
List the existing branches;
```
/git/git_basic# git branch -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```

Create a new branch 
```
/git/git_basic# git branch mynewbranch
/git/git_basic# git branch -a
* main
  mynewbranch
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```
Switch to the newly createad branch

```
/git/git_basic# git checkout mynewbranch
M       README.md
Switched to branch 'mynewbranch'
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/git_basic# git branch -a
  main
* mynewbranch
  remotes/origin/HEAD -> origin/main
  remotes/origin/main

```
Check the history to see what happend;
```
/git/git_basic# git log --oneline --decorate
77dbf07 (HEAD -> mynewbranch, origin/main, origin/HEAD, main) Merge branch 'main' of https://github.com/gonjumixproject/git_basic into main :q!
```
Go back to your main branch;

```
/git/git_basic# git checkout main

M       README.md
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
```
Change your branch name;
```
/git/git_basic# git branch -m mynewbranch newbranch
/git/git_basic# git branch -a
* main
  newbranch
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```
Delete the branch;
```
/git/git_basic# git branch -d newbranch
```



## Branching && Merging && Fast Forward Merge

Create a new branch, and directly switch to that branch;
```
/git/git_basic# git checkout -b ReadmeEdits
Switched to a new branch 'ReadmeEdits'
/git/git_basic# git status
On branch ReadmeEdits
nothing to commit, working tree clean
```
We committed a change on ReadmeEdits branch, but we need that changes on master as well.

```
/git/git_basic# git commit -am "changing the file"
[ReadmeEdits 78d636a] changing the file
 1 file changed, 8 insertions(+), 2 deletions(-)
/git/git_basic# git log --oneline
78d636a (HEAD -> ReadmeEdits) changing the file
```

Before merging the changes, we wanna know the differences.

Switch to the main branch;
```
git checkout main
```
Check the differences;
```
git difftoll main ReadmeEdits
```
Perform git merge;

```
 git merge
```
Delete the branch;

```
git branch -d ReadmeEdits
```

Disable fast forward;

```
git merge xx --no-ff
```

## Conflict Merge and Resolution
Do a change on the one branch
Make similar kind of change on the main branch
Try to merge, and observe the conflict
Updating the file from realwork

Create new branch and switch:
```
/git/git_basic# git checkout -b realwork
Switched to a new branch 'realwork'
```
Make some changes on the Readmifile.Commit the changes.
```
/git/git_basic# vi README.md
/git/git_basic# git commit -am "Making changes on readme file"
```
Jump into the main branch and make similar changes on Readme file, and commit the changes.

```
/git/git_basic# git checkout main
/git/git_basic# vi README.md
/git/git_basic# git add README.md
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/git_basic# git commit -m  "changes on readme pls"
[main 69a2a97] changes on readme pls
 1 file changed, 1 insertion(+)
root@ubuntu-s-1vcpu-1gb-fra1-01:/git/git_basic# git log --oneline --graph --decorate --all
```

Try to merge the changes, observe the conflict
```
/git/git_basic# git merge realwork
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```
Remove the conflicts via "mergetool"
```
/git/git_basic# git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff
Merging:
README.md

Normal merge conflict for 'README.md':
  {local}: modified file
  {remote}: modified file
Hit return to start merge resolution tool (vimdiff):
4 files to edit
/git/git_basic# vi README.md
/git/git_basic# git commit -am "Conflict cleared"
```

# Git Rebase

added a new branch, and switched to that branch
```
/home/git_basic# git checkout -b myfeature
Switched to a new branch 'myfeature'
```
add a new file from that branch and commit changes etc.

```
/home/git_basic# vi humans.txt
/home/git_basic# git add humans.txt
/home/git_basic# git commit -am "hello hello"
[myfeature eef5758] hello hello
 1 file changed, 1 insertion(+)
 create mode 100644 humans.txt
```
switch to the main, add some changes to the readme,commit changes

```
/home/git_basic# git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
/home/git_basic# vi README.md
/home/git_basic# git commit -am 'added new linew'
[main 6331ce9] added new linew
 1 file changed, 1 insertion(+), 1 deletion(-)
/home/git_basic#

```
Go back to myfeature branch, and check the changes, the changes on the main is not imported to this branch;
Rebase with the main to get the changes
```
/home/git_basic# git commit -am 'new lines for branding added'
[main 3bff579] new lines for branding added
 1 file changed, 30 insertions(+)
/home/git_basic# git checkout myfeature
Switched to branch 'myfeature'
/home/git_basic# git rebase main
First, rewinding head to replay your work on top of it...
Applying: hello hello
/home/git_basic# git log --oneline --decorate --all --graph
```

## Create Rebase Conflict

<<<<<<< HEAD
add changes on the readme file by main branch and commit changes, and then switch to the new branch;
```
/home/git_basic# git checkout main
M       README.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)
/home/git_basic# vi README.md
/home/git_basic# git commit -am "new lines aded"
[main a6651fa] new lines aded
 1 file changed, 14 insertions(+), 2 deletions(-)
/home/git_basic# git checkout -b bigtrouble
Switched to a new branch 'bigtrouble'
```
add changes into the Readme file from 'bigtrouble' branch, commit changes and then switch back to the main branch;

```
/home/git_basic# vi README.md
/home/git_basic# git commit -am "adding some new things"
[bigtrouble afca7fa] adding some new things
 1 file changed, 4 insertions(+)
/home/git_basic# git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 7 commits.
  (use "git push" to publish your local commits)
/home/git_basic# vi README.md
/home/git_basic# git commit -am "new things"
[main f8de016] new things
 1 file changed, 2 insertions(+)
/home/git_basic# git status
On branch main
Your branch is ahead of 'origin/main' by 8 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

## Use Rebase over the Conflict / Abort the Rebase

Switch back to the "bigtrouble" branch
Check the diff between "bigtrouble" and "main" via difftoll
Try to rebase
Rebase abort

```
/home/git_basic# git difftool main bigtrouble

This message is displayed because 'diff.tool' is not configured.
See 'git difftool --tool-help' or 'git help config' for more details.
'git difftool' will now attempt to use one of the following tools:
kompare emerge vimdiff

Viewing (1/1): 'README.md'
Launch 'vimdiff' [Y/n]? Y
2 files to edit
/home/git_basic# git rebase main
First, rewinding head to replay your work on top of it...
Applying: adding some new things
Using index info to reconstruct a base tree...
M       README.md
.git/rebase-apply/patch:12: new blank line at EOF.
+
warning: 1 line adds whitespace errors.
Falling back to patching base and 3-way merge...
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
error: Failed to merge in the changes.
Patch failed at 0001 adding some new things
hint: Use 'git am --show-current-patch' to see the failed patch
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".


/home/git_basic# git rebase --abort

```
use git mergetool to solve the conflict and continue with rebase continue to solve the conflict;

```

/home/git_basic# git mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff
Merging:
README.md

Normal merge conflict for 'README.md':
  {local}: modified file
  {remote}: modified file
Hit return to start merge resolution tool (vimdiff):
4 files to edit
/home/git_basic# vi README.md
/home/git_basic# git rebase --continue
Applying: adding some new things
``` 

trying to rebase with github


# Stashing



Stash command is used for working process changes. 

Lets say you added a line into a folder, but its not complete yet and you will continue later.

## Stash basic examples

You will use "git stash" to continue with other changes before committing it since its not done yet.

```
/home/git_basic# git stash
Saved working directory and index state WIP on main: a16ee69 Update README.md
/home/git_basic# git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

```

Perform "git stash apply" to apply the changes or continue

```
/home/git_basic# git stash apply
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
/home/git_basic# git commit -am 'changes added'
```

## Stashing untracked files and using pop

git stash will only stash the modified files, and not stash the untracked files as in new created files. 
To stash the new created files;


```

/home/git_basic# git stash -u
Saved working directory and index state WIP on main: 584b860 Stashing added
/home/git_basic# git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
/home/git_basic# vi README.md
home/git_basic# git stash list
stash@{0}: WIP on main: 584b860 Stashing added
```

we basicly use 'git stash apply' and 'git stash drop' for the latest stashed file.
we can direcly use 'git pop' instead of that two commands;

```
/home/git_basic# git stash pop

```
