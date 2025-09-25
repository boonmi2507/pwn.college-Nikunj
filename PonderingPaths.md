# Pondering Paths 

## The Root
Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path"

### Solve
**Flag:** `pwn.college{I7DeBuBOfEuNb3mv0fcK7Vbhhk3.QX4cTO0wSOwkjNzEzW}`

Accessed the pwn directory using the /pwn command.

```bash
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{I7DeBuBOfEuNb3mv0fcK7Vbhhk3.QX4cTO0wSOwkjNzEzW}
hacker@paths~the-root:~$ 

```

### New Learnings
Learnt about absolute paths and relative paths.

### References 
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Program and absolute paths

Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag.

### Solve 
**Flag:** `pwn.college{Y8cfhmPyaFx66-0FehXmoi_qZkC.QX1QTN0wSOwkjNzEzW}`

Accessed the run directory which was in the challenge directory using the command /challenge/run.

```bash
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{Y8cfhmPyaFx66-0FehXmoi_qZkC.QX1QTN0wSOwkjNzEzW}
hacker@paths~program-and-absolute-paths:~$

```
### New Learnings
Learnt about what root directoriies are and how to access directories inside the root directories.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Position thy self 

The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

```
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$

```
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. 

### Solve 
**Flag:** `pwn.college{Yrvj5nr-3lKF18UocR_ovZYjtej.QX2QTN0wSOwkjNzEzW}`

Ran the /challenge/run command to get the correct dirctory, then changed the current directory and accessed the run directory in it.

```bash
hacker@paths~position-thy-self:/proc/142/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Yrvj5nr-3lKF18UocR_ovZYjtej.QX2QTN0wSOwkjNzEzW}
hacker@paths~position-thy-self:/proc/142/fd$

```
### New Learnings 
Learnt how to change directories.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Position elsewhere

The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

```
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$

```
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.

### Solve 
**Flag:** `pwn.college{8TMSUWpe2yURhuJvpAdLrTvyFKT.QX3QTN0wSOwkjNzEzW}`

Ran the /challenge/run command to get the correct dirctory, then changed the current directory and accessed the run directory in it.

```bash
hacker@paths~position-elsewhere:/proc/143/fd$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8TMSUWpe2yURhuJvpAdLrTvyFKT.QX3QTN0wSOwkjNzEzW}
hacker@paths~position-elsewhere:/proc/143/fd$

```

### New Learnings
Learnt how to change directories.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Position yet elsewhere

The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:

```
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$

```
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.

### Solve 
**Flag:** `pwn.college{QJvkJOwn0QHKfl5Zg0bOkyqvi06.QX4QTN0wSOwkjNzEzW}`

Ran the /challenge/run command to get the correct dirctory, then changed the current directory and accessed the run directory in it.

```bash

hacker@paths~position-yet-elsewhere:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{QJvkJOwn0QHKfl5Zg0bOkyqvi06.QX4QTN0wSOwkjNzEzW}
hacker@paths~position-yet-elsewhere:/$

```
### New Learnings
Learnt how to change directories.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## implicit relative paths, from /

Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

A relative path is any path that does not start at root (i.e., it does not start with /).
A relative path is interpreted relative to your current working directory (cwd).
Your cwd is the directory that your prompt is currently located at.
This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
If my cwd is /tmp, then a relative path to the file is a/b/my_file.
If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.
Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /.

### Solve 
**Flag:** `pwn.college{0aj-ycE3y4yW9-Rt52dPyZE0xuv.QX5QTN0wSOwkjNzEzW}`

Changed the direcotry to /, then ran the command for relative path.

```bash
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{0aj-ycE3y4yW9-Rt52dPyZE0xuv.QX5QTN0wSOwkjNzEzW}
hacker@paths~implicit-relative-paths-from-:/$

```

### New Learnings
Learnt about relative paths and changing directories.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Explicit relative paths, from /

Previously, your relative path was "naked": it directly specified the directory to descend into from the current directory. In this level, we're going to explore more explicit relative paths.

In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:

/challenge
/challenge/.
/challenge/./././././././././
/./././challenge/././
The following relative paths are also all identical to each other:

challenge
./challenge
./././challenge
challenge/.
Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

This challenge will get you using . in your relative paths.

### Solve
**Flag:** `pwn.college{UXWGu9FIx9DjXjGg8swwTj_3eYe.QXwUTN0wSOwkjNzEzW}`

Used the implicit entry . to run the relative path command.

```bash
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UXWGu9FIx9DjXjGg8swwTj_3eYe.QXwUTN0wSOwkjNzEzW}
hacker@paths~explicit-relative-paths-from-:/$

```
### New Learnings 
Learnt about two types of implicit entries and thier uses.

### Reference
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## Implicit relative path

In this level, we'll practice referring to paths using . a bit more. This challenge will need you to run it from the /challenge directory. Here, things get slightly tricky.

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. Consider the following:

```
hacker@dojo:~$ cd /challenge
hacker@dojo:/challenge$ run

```
This will not invoke /challenge/run. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities! As a result, the above commands will yield the following error:

```
bash: run: command not found

```
### Solve
**Flag:** `pwn.college{UUmQ8GLWEtm9jyecRvV7fvUVLlu.QXxUTN0wSOwkjNzEzW}`

changed the direcotry to /challenge and used implicit entry to access run directory.

```bash
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UUmQ8GLWEtm9jyecRvV7fvUVLlu.QXxUTN0wSOwkjNzEzW}
hacker@paths~implicit-relative-path:/challenge$

```
### New Learnings
Learnt about what "naked" paths are and use of implicit entries.

### References
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s


## home sweet home

Every user has a home directory, typically under /home in the filesystem. In the dojo, you are the hacker user, and your home directory is /home/hacker. The home directory is typically where users store most of their personal files. As you make your way through pwn.college, this is where you'll store most of your solutions.

Typically, your shell session will start with your home directory as your current working directory. Consider the initial prompt:

```
hacker@dojo:~$

```
The ~ in this prompt is the current working directory, with ~ being shorthand for /home/hacker. Bash provides and uses this shorthand because, again, most of your time will be spent in your home directory. Thus, whenever bash sees ~ provided as the start of an argument in a way consistent with a path, it will expand it to your home directory. Consider:

```
hacker@dojo:~$ echo LOOK: ~
LOOK: /home/hacker
hacker@dojo:~$ cd /
hacker@dojo:/$ cd ~
hacker@dojo:~$ cd ~/asdf
hacker@dojo:~/asdf$ cd ~/asdf
hacker@dojo:~/asdf$ cd ~
hacker@dojo:~$ cd /home/hacker/asdf
hacker@dojo:~/asdf$

```

Now it's your turn to play! In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline, with these constraints:

Your argument must be an absolute path.
The path must be inside your home directory.
Before expansion, your argument must be three characters or less.
Again, you must specify your path as an argument to /challenge/run as so:

```
hacker@dojo:~$ /challenge/run YOUR_PATH_HERE

```
### Solve
**Flag:** `pwn.college{sYE8upGKmJAB0GQinznASD4oT3T.QXzMDO0wSOwkjNzEzW}`

Used /challenge/run as command and ~/a as argument(here ~ is an absolute path). The shell expands ~/a to /home/hacker/a.

```bash
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{sYE8upGKmJAB0GQinznASD4oT3T.QXzMDO0wSOwkjNzEzW}

```
### New Learnings
Learnt how ~ expansion works and how shell precoesses arguments.

### Refrences
https://www.youtube.com/watch?v=b67Jq6IZ3U8&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=25s