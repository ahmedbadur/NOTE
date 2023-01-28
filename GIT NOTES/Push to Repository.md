# PUSH TO REPOSITORY

Firstly, we define name and email.

  ```
  $ git config --global user.name "username"
  $ git config --global user.email "username@domainmail.com"  
  ```
   
We create a file (New File) on Desktop. Then We create two files(AboutMe,Notes) for example. We start git.

```
$ git init
Initialized empty Git repository in D:/GIT/.git/
```

We check status.

```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        AboutMe/
        Notes/
nothing added to commit but untracked files present (use "git add" to track)
```


We add the files. If you want to just 1 file we write (git add filename)

```
$ git add .
```

We check status again. We will see the files waiting to be committed.

```
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   AboutMe/Introduction.txt
        new file:   Notes/GIT Notes/GIT-01.txt
```

We apply the commit process with an "explanatory text".

```
$ git commit -m "About Me and Notes commited"
[master (root-commit) 2b1eb51] About Me and Notes commited
 2 files changed, 9 insertions(+)
 create mode 100644 AboutMe/Introduction.txt
 create mode 100644 Notes/GIT Notes/GIT-01.txt
```

Then we check status. Must have been cleared.

```
$ git status
On branch master
nothing to commit, working tree clean
```

Now, We will push to Github so we create a repository in github. We copy html link. Example: https://github.com/ahmedbadur/GIT.git

```
$ git remote add repositoryname https://github.com/ahmedbadur/GIT.git
```

We should check.


```
$ git remote
repositoryname
```

We push to Repository.


```
$ git push -u repositoryname master
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (7/7), 548 bytes | 548.00 KiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/ahmedbadur/GIT.git
 * [new branch]      master -> master
branch 'master' set up to track 'Repo/master'.
```
**Push process has been completed.**
