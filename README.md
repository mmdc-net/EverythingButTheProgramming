![MMDC Logo](https://github.com/mmdc-net/EverythingButTheProgramming/blob/master/mmdc.png)
# Everything But The Programming
In this course, you will learn several valuable skills that programmers, developers and dev-ops use.  Much of it relates to Linux and Unix, but it all works for Windows and Mac users as well.
It's not a programming course--in fact, it's everything but.  
What I'd like to show you is all of the stuff that goes along with programming, the stuff that too often holds people back.
## Audience
This course requires more interest than experience.  That is, there really aren't any prerequisites, but this is for people who enjoy hacking away at computers and want to get some new skills.
It's also perfect for those who have been writing and deploying code, but are missing certain skills that are holding them back.
It's worth noting that all of the software used in this course is open source and free to use.
## Use Cases
How will what you learn here help you personally and professionally?
### Job Interviews
> "*Show me your GitHub.*"
Interviewers and prospective teams more and more want to see what you've done on GitHub--it's the demo reel for a programmer's career these days.  It's not only a great way to work, it's a great way to show off your abilities as a coder.  Even if you only contribute documentation and perhaps bug fixes to Open Source projects, it shows that you are proactive and detail-oriented.  
### Working With Others
Let's say you're a competent coder, developing in the latest and greatest framework technology, but you've always worked by yourself, storing all of your files on your laptop, until you FTP them up to the server to deploy.
When you get hired, you'll often be tossed into a team where you can't keep the company's whole codebase on a laptop that could get lost, stolen, or have a hard drive failure.
Even simple things like SSH'ing to a remote server to `tail -f` (or better, `less -F`! ) a log file can be quite embarrassing if you don't know how to do them when the time comes.
### YouTube
If you're going to keep current with the industry, you're going to have to dedicate a few hours a week or a month to self-study and there's no better place to start than YouTube.
The more of the supportive technologies taught in this course that you know, the better you can process what you're being shown in the video.  
## The Unix Filesystem
We're not going to cover every aspect of the Unix Filesystem, but it's important to have a good working knowledge of how to get around and where to stash your stuff.
We'll also take a look at file and directory permissions and learn why they are so important.
  [Intro to Unix Filesystems](https://github.com/mmdc-net/EverythingButTheProgramming/blob/master/filesystem.md)
## The Command Line
If you do everything you can to *avoid* the command line, you're not alone. The command line frightens a lot of computer professionals.  With just a little bit of understanding and a bit of instruction, you can put it to work for you, without the fear of screwing up your system.
We'll be using the BASH shell for Windows, Linux and OSX.  It's a good place to start, as it's become kind of a 'universal' shell.  Also, most of the examples online are Bash, so it simplifies looking stuff up.

## SSH Keys
SSH, the secure shell, is how you communicate securely on a computer system.  It's used to prove your identity to a remote system, as well as encrypt your traffic during any and all communications with that system.

## Editors and IDEs
To a programmer, the choice of a text editor is a very important and personal one.  Editors can be lean and fast, or feature-rich and heavy. We'll be looking at several cross-platform, freely-available editors.  

### Vi/Vim/Gvim
Vi (Pronounced "Vee-Eye," never "Vai" or "Six") is and editor first written in 1976 by Bill Joy.  It's lean, it's fast and some form of it is on every Unix-like system.

These days, Vim (Rhymes with "him." I know that doesn't make sense, given how vi is never pronounced as a word.) is what most people who use vi use.  

There are many versions and variants, but once you have learned the basics, you can use any of them. We'll be learning those basics, just a few skills to get you started, as well as where to go to learn more.

### The Atom Editor
The Atom editor is a "hackable text editor for the 21st Century," according to its developers. It's Open Source.  It's made by GitHub.  It's infinitely extensible using plugins.  
We'll install it as well as some of the most useful plugins.

Atom is also what's known as an IDE, or "Integrated Development Environment."  IDEs are used to work on whole projects, not just single files.  

### Visual Studio Code
Visual Studio Code, or just "Code" to its proponents, is a surprisingly good cross-platform editor and IDE.  It's from Microsoft, as you might have guessed by the name, but it's also Open Source and there are versions for Windows, Linux and OSX.

## Git
"Git is a free and open source distributed version control system designed to handle everythi
ng from small to very large projects with speed and efficiency. Git is easy to learn and has a tiny footprint with lightning fast performance."
Git runs on the three major operating systems we're dealing with here, so let's get it installed:

There are graphical tools for using Git, but it's best to master a few terminal commands first, to better understand what's happening.

  [Intro to Git](https://github.com/mmdc-net/EverythingButTheProgramming/blob/master/git.md)

## GitHub, Bitbucket and Gitlab
To use Git, you don't need to be working with others, but great things can happen when you do.  Using communities like GitHub, you'll get to experience what's called "Social Coding," where a distributed group of developers can work together on a project.
In this course, we will set up your GitHub account, fill in your profile and upload your encryption keys, as well as create your first repository.
[intro to GitHub
](https://github.com/mmdc-net/EverythingButTheProgramming/blob/master/github.md)
