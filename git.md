# Git

Git is available for Linux, Mac and Windows.  

## Installation
(The following installation instructions are from GitHub user [@derheurst's Gist ](https://gist.github.com/derhuerst/1b15ff4652a867391f03))

[Install Git on Windows](https://github.com/mmdc-net/curriculum/blob/master/git-install-windows.md)

[Install Git on Mac](https://github.com/mmdc-net/curriculum/blob/master/git-install-mac.md)

[Install Git on Linux](https://github.com/mmdc-net/curriculum/blob/master/git-install-linux.md)

# Creating a Local Repository
Turning a directory into a repo is a very simple process.  Using your terminal, or Git Bash on Windows, cd to your project's directory:
````
    mkdir ~/myProject        # This will create a dir called "myProject" in your home directory
                             # ( ~/ is a shortcut for your home directory)
    cd ~/myProject           # "cd" is "Change Directory"
    git init                 # Initialize a new git repo.
                             # You should see the following output:
# Initialized empty Git repository in C:/Users/User/myProject/.git/
````
This has created a hidden directory called `.git` in your directory. You can see the contents of `.git` using the '`ls -Flag`' command:
````
User@x230Len171025 MINGW64 ~/myProject (master)
$ ls -Flag .git/
total 11
drwxr-xr-x 1 197121   0 Jul  1 12:28 ./
drwxr-xr-x 1 197121   0 Jul  1 12:28 ../
-rw-r--r-- 1 197121 130 Jul  1 12:28 config
-rw-r--r-- 1 197121  73 Jul  1 12:28 description
-rw-r--r-- 1 197121  23 Jul  1 12:28 HEAD
drwxr-xr-x 1 197121   0 Jul  1 12:28 hooks/
drwxr-xr-x 1 197121   0 Jul  1 12:28 info/
drwxr-xr-x 1 197121   0 Jul  1 12:28 objects/
drwxr-xr-x 1 197121   0 Jul  1 12:28 refs/

````
Generally, we don't mess with the files in the .git directory, with the exception of one:
The file `config` can be edited to change certain characteristics of the repo. (More on this later.)
You also have the option of creating a `.gitinore` that lists files that you do not want tracked. This file is generally kept in the top-level directory of your repo.
## Adding files to your Repository
let's add some files for our project.  To start with, we'll add a simple Markdown file called "README.md" and echo some text into it:
````
    touch README.md
    echo "# myProject" >> README.md
    echo "This is the README.md for myProject" >> README.md
````
*("README.md" is kind of a special file, if you decide to share your repo on GitHub.  By default, the contents of README.md are displayed when viewing the repo's home page.)*
## Git Status
Now that we have a file in the repo, let's run `git status` to see what the status of the repo is:
````
$ git status
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)

    README.md

nothing added to commit but untracked files present (use "git add" to track)
````
As you can see, we need to add our README to git, so that git knows to track its status:
````
$ git add README.md
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory.
````
(The warning relates to line endings.  Since Windows and Unix use different characters to denote the end of a line, Git is smart enough to seamlessly convert back and forth.)
Now that we've added the file to Git, we need to commit the file and add a message saying what was done to the file:
```term
$ git commit -m "Initial commit.  Starting with README.md"
[master (root-commit) 06e798e] Initial commit.  Starting with README.md
 1 file changed, 2 insertions(+)
 create mode 100644 README.md
````
Now let's run `git status` again:
```term
User@x230Len171025 MINGW64 ~/myProject (master)
$ git status
On branch master
nothing to commit, working tree clean
```
## Edit, Commit, Repeat
Now that our file is in Git and up-to-date, let's modify it. (I'm going to use `echo` again, but you can use your favorite editor.)
````
echo "## Purpose" >> README.md
echo "This is a practice file for learning Git." >> README.md
````
`git status` command shows us:
````
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
````
### What's the Diff?
If we want to see how what we have differs from what is in the committed version, we can use `git diff`:
```
$ git diff
diff --git a/README.md b/README.md
index 5136266..2ba40d5 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1,4 @@
 # myProject
 This is the README.md for myProject
+## Purpose
+This is a practice file for learning Git.

```
At the bottom of that block, you see the file's contents, with the added lines signified with a leading "+".  
(Learning to read a diff is probably outside the scope of this course, but I wanted to let you know that Git supports it.)

When you're working on a project, you tend to work on more than one file at a time, so when it comes time to add and commit, we don't have to explicitly add each changed file.  Let's add all of the files in the project:
```
$ git add -A
# warning: LF will be replaced by CRLF in README.md.
# The file will have its original line endings in your working directory.
```
Looks good.  Let's commit it and add a meaningful commit message:
```
$git commit  -m "Modified README.md, adding file's purpose"
[master c833bd8] Modified README.md, adding file's purpose
 Date: Sun Jul 1 19:00:46 2018 -0400
 1 file changed, 2 insertions(+)
```
## Going Back in time
Sometimes, no matter how careful we are, we need to undo our commits and revert to an earlier state of the project.  Fortunately, Git makes this very, very do-able, though given its precision, it's not the most intuitive process.  Let's list off our changes:
```
$ git reflog
c833bd8 (HEAD -> master) HEAD@{5}: commit: Modified README.md, adding file's purpose
06e798e HEAD@{7}: commit (initial): Initial commit. Starting with README.md
```
That first code on each line is the "SHA" or hash, a unique code for each commit.  That's what we use to tell Git what version we want to revert to.  Let's say we want to go back to the first commit.  We have a couple options.  The first is to go back, but keep the modifications we made to README.md.  The second is to do a hard reset and bring the files to their previous state.
Let's go back to the state it was in at the first commit:
```
$ git reset --hard 06e798e
HEAD is now at 06e798e Initial commit.  Starting with README.md
```
Use `cat` to show the contents of README.md:
```
$ cat README.md
# myProject
This is the README.md for myProject
```
We're now back where we were at the first commit.  We can even jump forward in time, to a later commit:
```
$ git reset --hard c833bd8
HEAD is now at c833bd8 Modified README.md, adding file's purpose
```
Again use `cat` to show the contents of README.md:
```
$ cat README.md
# myProject
This is the README.md for myProject
## Purpose
This is a practice file for learning Git.
```
There's no way I could cover every use case for undoing and re-doing stuff with Git, so let me just give you a [page to bookmark](https://blog.github.com/2015-06-08-how-to-undo-almost-anything-with-git/).
## Don't Skimp on your Commit Messages!
As you can see, the better your commit messages, the easier it is to navigate through time.  Don't be lazy!
If you take a look at a huge project, like [Linux itself](https://github.com/torvalds/linux), you will see lots of commits.  761,169 commits, as I type this, the [last made about an hour ago by Linus Torvalds himself](https://github.com/torvalds/linux/commit/021c91791a5e7e85c567452f1be3e4c2c6cb6063).  Imagine trying to navigate more than 3/4 of a million commits, if the messages say things like "Fixed some stuff."
