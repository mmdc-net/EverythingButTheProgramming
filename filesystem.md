# The Unix Filesystem
In the CommandLine module, we learned how to find our location using the terminal, but that is, of course, of limited use if we don't have a working knowledge of its structure. 
Unix systems, Linux systems and, to some extent the virtualized filesystems in Git Bash for Windows follow the [Filesystem Hierarchy Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard).
# The Root Directory
Every file, directory and device in a Unix filesystem exists somewhere under ` / `, the "root" directory.  This is the case, even when the filesystems are on a different physical disk or partition--they have a mount point somewhere under ` / `. 
> ## Root Confusion
> The word "root" is used in several contexts in a Unix-like system.  
> ### The Root Directory
The first context is used to refer to the root directory, under which all of the files exist.
> ### The Root User
> `root` is the user name or account that by default has access to all commands and files.
> Also known as the 'superuser' account, it is the account that is used for single-user mode.  You should never use the root account as your 'daily driver,' instead opting to use the `sudo` command to escalate your privileges temporarily.
> ### 'Slash Root'
> In the root directory is a directory called `/root` that is the root user's home directory.  When spoken, it is referred to as "Slash Root."
 On a typical Linux system, (For example, the one I am using right now,) the root directory contains the following directories:
 ```bash
  $ ls -Flag / | grep ^d 
  drwxr-xr-x  23 root  4096 Jul  3 06:54 ./
  drwxr-xr-x  23 root  4096 Jul  3 06:54 ../
  drwxr-xr-x   2 root  4096 Jul  9 17:09 bin/
  drwxr-xr-x   4 root  3072 Jul  9 17:10 boot/
  drwxr-xr-x  20 root  4240 Jul 11 09:31 dev/
  drwxr-xr-x 138 root 12288 Jul 12 06:41 etc/
  drwxr-xr-x  11 root  4096 Jul  9 14:41 home/
  drwxr-xr-x  24 root  4096 Jun 12 08:26 lib/
  drwxr-xr-x   2 root  4096 Feb 27 06:15 lib64/
  drwx------   2 root 16384 Feb 26 15:03 lost+found/
  drwxr-xr-x   3 root  4096 Feb 26 15:03 media/
  drwxr-xr-x   2 root  4096 Aug  1  2017 mnt/
  drwxr-xr-x   4 root  4096 Apr 11 23:15 opt/
  dr-xr-xr-x 242 root     0 Jul 11 09:31 proc/
  drwx------   8 root  4096 Jun 12 10:57 root/
  drwxr-xr-x  31 root  1200 Jul 15 11:02 run/
  drwxr-xr-x   2 root 12288 May 30 08:20 sbin/
  drwxr-xr-x   2 root  4096 Apr 21 22:52 snap/
  drwxr-xr-x   3 root  4096 May 21 18:07 srv/
  dr-xr-xr-x  13 root     0 Jul 11 09:42 sys/
  drwxrwxrwt  31 root 12288 Jul 15 11:02 tmp/
  drwxr-xr-x  10 root  4096 Feb 26 15:03 usr/
  drwxr-xr-x  16 root  4096 Apr 11 23:15 var/
```
### Dot and Dot-Dot
If you look at that list, there are a couple of strangely-named directories:
``` term
drwxr-xr-x  23 root  4096 Jul  3 06:54 ./ 
drwxr-xr-x  23 root  4096 Jul  3 06:54 ../ 
```
These are a couple of special directories that every directory contains.
#### Dot
The first one, ` ./ ` (referred to as 'dot',) is the current directory.  It's a useful shortcut for saying "here," when using the terminal. For example, you might want to copy your Vim configuration file  (` .vimrc `) from a server to the directory where you happen to be:
```bash
 $ scp example.com:/home/jim/.vimrc .
 .vimrc                                             100% 4401     4.3KB/s
```  
#### Dot Dot
The other special directory is ` ../ ` which is the parent directory, relative to the current directory. 
(In the case of the root directory, ` ../ ` and ` ./ ` are synonymous.)
Being able to use ` ../ ` in scripts to mean "one directory up" is essential for writing portable commands and scripts.
![Filesystem Hierarchy](https://github.com/mmdc-net/EverythingButTheProgramming/blob/master/Standard-unix-filesystem-hierarchy.svg)
