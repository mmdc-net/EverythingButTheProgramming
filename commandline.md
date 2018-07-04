# The Command Line
Somewhere around 1969, someone decided to replace the printer on their teletype computer terminal (known as a TTY,) with a cathode ray tube, giving birth to the "Glass TTY," perhaps the first truly modern computer interface.
With the Unix kernel came some of the first modern command line interpreters, or "shells." In 1971, Ken Thompson created "sh," also known as the "Thompson Shell."
In 1979, Stephen Bourne created the "Bourne Shell," which was generally replaced with the "Bourne again Shell," or "bash" in 1988.  Bash is still the most commonly-used shell, thirty years later,
Shells are how you interact with the part of your operating system that talks to the hardware.  In your shell, you can run commands, inspect processes, write scripts and use character-mode programs.
It's also the most efficient and powerful way of interacting with your computer.
In your shell, programs are generally written to adhere to certain principles, summarized by Peter H. Salus in A Quarter-Century of Unix (1994):

    Write programs that do one thing and do it well.
    Write programs to work together.
    Write programs to handle text streams, because that is a universal interface.

Unix-like programs take text as input and give text as output wherever possible.  They don't require extraneous interaction by default, as this would limit their usability in scripts.
They work with *pipes*. What are pipes? Pipes (Implemented with the character "|",) connect commands and programs and even let you string together lots of them, to create powerful ad-hoc programs known as *one-liners*.
## Getting Started
Open your terminal.  
In Linux, start with the default terminal.  It might be `gnome-terminal ` or `mate-terminal`, but it will probably be under 'Accessories' or 'System Tools' in the OS's menu system.
On a Mac, it's in "Applications/Utilities".
In Windows, you should download "[Git Bash](https://git-scm.com/download/win)" and install it using the default options. (Windows' built-in command interpreters, `cmd.exe` and PowerShell, are not good alternatives--you really need Git Bash.)
Your terminal prompt promamly looks something like this:
`jim@host:~$ ` - That's your username and host (computer's) name the current directory, (`~` is shorthand for the current user's home directory,) as well as a dollar sign (`$`) prompt. This prompt means that the shell is ready to accept your typed commands.
In Bash, the shell, or command interpreter, the core commands are given the shortest names that still avoid ambiguity.  This dates from the days when disks were small and networks slow, but it works well for users now, with a little bit of memorization.
## pwd - where am I?
To see where you happen to be in the filesystem, you type `pwd` and hit enter.  On my system, this gives me:
```
jim@blinky:~$ pwd
/home/jim
```  
`pwd` stands for "Print Working Directory," though I have it memorized as "Present Working Directory."  Either works, so memorize it with whatever mnemonic that works for you.
## Show me the files: `ls`
`ls` is another one like that--officially, I believe it stands for "List Files," but years ago, I was told to remember it as standing for "Let's See."   Let's see what's in the current directory:
```
jim@blinky:~$ ls
bin      Documents  Music     projects  snap       Videos
Desktop  Downloads  Pictures  Public    Templates  VirtualBox VMs
jim@blinky:~$
```
That shows us the filenames, but doesn't tell us much about the files.  It also doesn't show us hidden files. (In Linux, the shell hides filenames that begin with a dot. ".")  
To show more information, we start adding "option switches" to `ls`.  To show all the files, add `-a` to make it `ls -a`:
```
jim@blinky:~$ ls -a
.              Downloads      .ssh
..             .gconf         .sudo_as_admin_successful
.atom          .gnome2        Templates
.bash_history  .ICEauthority  Videos
.bash_logout   .local         .viminfo
.bashrc        .mozilla       VirtualBox VMs
bin            Music          .Xauthority
.byobu         .oh-my-zsh     .xsession-errors
.cache         Pictures       .xsession-errors.old
.config        .pki           .zcompdump
.dbus          .profile       .zcompdump-Dellephant-5.1.1
Desktop        projects       .zsh_history
.dmrc          Public         .zshrc
Documents      snap
jim@blinky:~$
```
See all of those "dot" files that  we didn't see before?  Still, we don't know what kind of files they are.  Rather than go through all of the options we can add, I'm going to give you one easy-to-remember option set that tells you most everything about the files:
`ls -a -l -g -F`
Wait, that's not very easy to remember, is it?  Well, we can combine all of those options into:
`ls -Flag`
It is not the word "Flag," just a convenient way to remember those options.  Here's what it gives us:
```
jim@blinky:~$ ls -Flag
total 244
drwxr-xr-x 26 jim   4096 Jul  2 22:47 ./
drwxr-xr-x  5 root  4096 Apr 30 19:56 ../
drwxrwxr-x  8 jim   4096 Jul  2 21:21 .atom/
-rw-------  1 jim   1002 Jul  2 22:47 .bash_history
-rw-r--r--  1 jim    220 Apr 30 12:02 .bash_logout
-rw-r--r--  1 jim   3848 Jul  2 18:21 .bashrc
drwxrwxr-x  3 jim   4096 Jul  2 20:35 bin/
drwxrwxr-x  3 jim   4096 Jul  2 18:20 .byobu/
drwx------ 15 jim   4096 Jul  2 22:22 .cache/
drwxr-xr-x 21 jim   4096 Jul  2 22:31 .config/
drwx------  3 jim   4096 Apr 30 12:58 .dbus/
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Desktop/
-rw-r--r--  1 jim     23 Apr 30 12:58 .dmrc
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Documents/
drwxr-xr-x  2 jim   4096 Jul  2 22:07 Downloads/
drwx------  2 jim   4096 Jul  2 19:59 .gconf/
drwx------  3 jim   4096 Apr 30 19:52 .gnome2/
-rw-------  1 jim   1038 Jul  2 19:48 .ICEauthority
drwx------  3 jim   4096 Apr 30 12:58 .local/
drwx------  5 jim   4096 Apr 30 20:06 .mozilla/
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Music/
drwxr-xr-x 11 jim   4096 Jul  2 21:20 .oh-my-zsh/
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Pictures/
drwx------  3 jim   4096 Jul  2 20:00 .pki/
-rw-r--r--  1 jim    655 Apr 30 12:02 .profile
drwxrwxr-x  4 jim   4096 Jul  2 21:19 projects/
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Public/
drwxr-xr-x  3 jim   4096 Jul  2 20:45 snap/
drwx------  2 jim   4096 Apr 30 21:21 .ssh/
-rw-r--r--  1 jim      0 Apr 30 17:02 .sudo_as_admin_successful
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Templates/
drwxr-xr-x  2 jim   4096 Apr 30 12:58 Videos/
-rw-------  1 jim   2997 Jul  2 19:08 .viminfo
drwxr-xr-x  2 jim   4096 Jul  2 22:33 VirtualBox VMs/
-rw-------  1 jim    118 Jul  2 19:48 .Xauthority
-rw-------  1 jim   9319 Jul  2 22:29 .xsession-errors
-rw-------  1 jim   5414 Jul  2 19:47 .xsession-errors.old
-rw-r--r--  1 jim  39533 Jul  2 21:20 .zcompdump
-rw-r--r--  1 jim  39679 Jul  2 21:20 .zcompdump-Dellephant-5.1.1
-rw-------  1 jim    306 Jul  2 22:27 .zsh_history
-rw-r--r--  1 jim   3134 Jul  2 21:20 .zshrc
jim@blinky:~$
```
You can also add the name of a file or directory to the command:
```
jim@blinky:~$ ls -Flag ~/.ssh/
total 176
drwx------  2 jim  4096 Jul  2 23:11 ./
drwxr-xr-x 26 jim  4096 Jul  2 22:47 ../
-rw-------  1 jim   243 Apr 30 21:21 authorized_keys
-rw-------  1 jim   642 Apr 30 21:21 config
-rw-------  1 jim  1766 Apr 30 21:21 github_rsa.bak
-rw-------  1 jim   883 Apr 30 21:21 id_rsa
-rw-------  1 jim   243 Apr 30 21:21 id_rsa.pub
-rw-r--r--  1 jim 70857 Apr 30 21:21 known_hosts
jim@blinky:~$
```
Try it out.  `ls` doesn't change anything about the filesystem, it simply lists what it can, so it's safe to play around with.
## Change Directories with `cd`
`cd` stands for "change directory."  So, to cd to your system's temp directory, simply type:`cd /tmp`
To quickly go to your home directory, type `cd` by itself.
  ### A Note on Directory Shortcuts
  The operating System has a few special ways to work with directories that are worth looking at now.  To illustrate, let's create a new, empty directory and show what's in it:
  ```
  jim@blinky:~$ mkdir foo                      # Create a directory
  jim@blinky:~$ cd foo                         # Move to it
  jim@blinky:~/foo$ ls -Flag                   # Show all files in detail
  total 8                                      # blocks (disregard for now)
  drwxr-xr-x  2 jim 4096 Jul  3 08:14 ./       # ./ is the current dir
  drwxr-xr-x 28 jim 4096 Jul  3 08:14 ../      # ../ is the parent dir
  jim@blinky:~/foo$
  ```
  (In the example above, any characters after the `# ` is a comment and is ignored by the shell.)
  As you can see, there are a couple of pseudo files listed, `./` and `../` that refer to the present directory and the parent directory, respectively. They might seem confusing at first, but they are quite convenient, especially when writing scripts.
  The other directory shortcuts to know about are `/` and `~/`.
  `~/` is the current user's home directory.
  `/` is the system's 'root,' or top-level directory. (`/` is the top level, regardless of what disks or partitions may be mounted, which may not be obvious if you're coming from MSDOS.)
### Using . and .. and /
Using `cd`, you will frequently use `../` to jump up a directory, or even several: ` cd ../../../`
You can jump up a directory and then down a different path:
```
jim@blinky:~/projects/express-crash-course/node_modules/thunky$ pwd
/home/jim/projects/express-crash-course/node_modules/thunky
jim@blinky:~/projects/express-crash-course/node_modules/thunky$ cd ../../views/partials/
jim@blinky:~/projects/express-crash-course/views/partials$ pwd
/home/jim/projects/express-crash-course/views/partials
jim@blinky:~/projects/express-crash-course/views/partials$
```
As you can see, by using `cd ../../views/partials/` I was able to go up two directories and down two others.  Very handy.
Using `./` for the current directory is equally handy.  Let's say you have a file in `/tmp` that you want to copy to the current directory.  This is easy, using `.`:
`jim@blinky:~/foo$ cp /tmp/foofile .`
As you can see in the above example, I referred to the temp directory as `/tmp` to show that I mean the one in the top level.  Without the slash, bash would try to find it in the current directory:
```
jim@blinky:~/foo$ ls tmp
ls: cannot access 'tmp': No such file or directory
```
That's no good.  Let's add a slash:
```
jim@blinky:~/foo$ ls /tmp
Atom Crashes            npm-24389-306fddb6  npm-25648-6f8e9b78        ssh-VEqfObRxjsIn
atom-_ghd1Q4JZcYM.sock  npm-25174-374deba0  npm-25735-6693d870        systemd-private-9fb1262ffc4543cfb0a7521d2ebea6c2-rtkit-daemon.service-GBmPyU
foofile                 npm-25424-c91c7ea8  npm-25958-f48a95f8        vboxdrv-Module.symvers
hsperfdata_root         npm-25506-00d378fb  npm-26005-8669fc9d
mozilla_jim0            npm-25581-851a2066  snap.1000_discord_BBdum6
```
> Unix (and Linux and OS X's BSD subsystem and even Windows' Git Bash) rae case-sensitive and picky about things like slashes.  Don't let it intimidate you!
