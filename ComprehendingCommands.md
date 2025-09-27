# Comprehending Commands

## cat ot the pet, but the command
One of the most critical Linux commands is cat. cat is most often used for reading out files, like so:

```
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
One of the most critical Linux commands is `cat`.
`cat` is most often used for reading out files, like so:

```
cat will concatenate (hence the name) multiple files if provided multiple arguments. For example:

```
hacker@dojo:~$ cat myfile
This is my file!
hacker@dojo:~$ cat yourfile
This is your file!
hacker@dojo:~$ cat myfile yourfile
This is my file!
This is your file!
hacker@dojo:~$ cat myfile yourfile myfile
This is my file!
This is your file!
This is my file!

```

### Solve
**Flag:** `pwn.college{UXneQw-l5Bj1l49j0yz-mdBVqqz.QXxcTN0wSOwkjNzEzW}`

Used the cat command to read the flag file.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{UXneQw-l5Bj1l49j0yz-mdBVqqz.QXxcTN0wSOwkjNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$

```

### New Learnings
Learnt how to use cat command to read files.

### References 


## catting absolute paths


In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths:

```
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
In the last level, you did `cat flag` to read the flag out of your home directory!
You can, of course, specify `cat`'s arguments as absolute paths:
...

```
In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.

### Solve
**Flag:** `pwn.college{IY7D3i0tC0kG9YBOa_6o2_SRoD0.QX5ETO0wSOwkjNzEzW}`

Used cat command to read the absolute path /flag.

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{IY7D3i0tC0kG9YBOa_6o2_SRoD0.QX5ETO0wSOwkjNzEzW}
hacker@commands~catting-absolute-paths:~$

```
### New Learnings
Learnt to use cat command to read absolute paths.

### References


## more catting practice

You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.

### Solve
**Flag:** `pwn.college{k6ZdHh2tqXZyqVeFTzLcmzl4DQP.QXwITO0wSOwkjNzEzW}`

Since, it was not allowed to cd directly into the path to access the flag. I used the cat command to read the aboslute path.

```bash
hacker@commands~more-catting-practice:~$ cat /usr/share/iptables/flag
pwn.college{k6ZdHh2tqXZyqVeFTzLcmzl4DQP.QXwITO0wSOwkjNzEzW}
hacker@commands~more-catting-practice:~$

```
### New Learnings 
Learnt new method to read files using cat.

### References


## grepping for a needle in a haystack

Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need! We'll learn it in this challenge.

There are many ways to grep, and we'll learn one way here:

```
hacker@dojo:~$ grep SEARCH_STRING /path/to/file

```
nvoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag!

### Solve 
**Flag:** `pwn.college{06PAK6W5ivMAljeaSAHf22hUj53.QX3EDO0wSOwkjNzEzW}`

Used grep to search for specific keyword for the flag in the path /challenge/data.txt

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{06PAK6W5ivMAljeaSAHf22hUj53.QX3EDO0wSOwkjNzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ 

```
### New Learnings
Learnt about how to use grap command to search for specific keywords.

### References 


## Comparing Files

When looking for changes between similar files, eyeballing them might not be the most efficient approach! This is where the diff command becomes invaluable.

diff compares two files line by line and shows you exactly what's different between them. For example:

```
hacker@dojo:~$ cat file1
hello
world
hacker@dojo:~$ cat file2
hello
universe
hacker@dojo:~$ diff file1 file2
2c2
< world
---
> universe

```
The output tells us that line 2 changed (2c2), with world in the first file (<) being replaced by universe in the second file (>).

Sometimes, when new lines are added, you'll see something like:

```
hacker@dojo:~$ cat old
pwn
hacker@dojo:~$ cat new
pwn
college
hacker@dojo:~$ diff old new
1a2
> college

```
This tells us that after line 1 in the first file, the second file has an additional line (1a2 means "after line 1 of file1, add line 2 of file2").

Now for your challenge! There are two files in /challenge:

/challenge/decoys_only.txt contains 100 fake flags
/challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag
Use diff to find what's different between these files and get your flag!

### Solve 
**Flag:** `pwn.college{cdbkHnP1FiOmcwxUmsBwsl1Dnry.01MwMDOxwSOwkjNzEzW}`

Used the diff command to compare between two files which added the the 45th line of the 2nd file after the 44th line of 1st file.

```bash

hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
44a45
> pwn.college{cdbkHnP1FiOmcwxUmsBwsl1Dnry.01MwMDOxwSOwkjNzEzW}
hacker@commands~comparing-files:~$ 

```
### New Learnings 
Learnt about diff command to compare between two files and how it is used to add the extra element from one file to another.

### References


## Listing Files

So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:

```
hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$

```
### Solve 
**Flag:** `pwn.college{cZDVMFGWkihEJtY4scB176eagEC.QX4IDO0wSOwkjNzEzW}`

Listed the files in /challenge which gave the renamed name for the run file, then executed acommand to find flag in the renamed file.

```bash
hacker@commands~listing-files:~$ /challenge/27339-renamed-run-27959
Yahaha, you found me! Here is your flag:
pwn.college{cZDVMFGWkihEJtY4scB176eagEC.QX4IDO0wSOwkjNzEzW}
hacker@commands~listing-files:~$ 

```

### New Learnings
Learnt about listing files inside a directory using the ls command.

### References


## Touching Files

Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:

```
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$

```
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

### Solve
**Flag:** `pwn.college{0DaFYsMGZGZlkQeGmYflcRXqiHk.QXwMDO0wSOwkjNzEzW}`

Created two new files using the touch command.

```bash

hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{0DaFYsMGZGZlkQeGmYflcRXqiHk.QXwMDO0wSOwkjNzEzW}
hacker@commands~touching-files:~$

```
### New Learnings
Learnt to use the touch command to create files in the existing directory.

### References


## Removing files

Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!

In Linux, you remove files with the rm command, as so:

```
hacker@dojo:~$ touch PWN
hacker@dojo:~$ touch COLLEGE
hacker@dojo:~$ ls
COLLEGE     PWN
hacker@dojo:~$ rm PWN
hacker@dojo:~$ ls
COLLEGE
hacker@dojo:~$

```
### Solve
**Flag:** `pwn.college{sJoEk6eFJshkruN7tg53_ppARPj.QX2kDM1wSOwkjNzEzW}`

Used the touch command to create a new file, then deleted it using the rm command.

```bash

hacker@commands~removing-files:~$ touch delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{sJoEk6eFJshkruN7tg53_ppARPj.QX2kDM1wSOwkjNzEzW}
hacker@commands~removing-files:~$

```
### New Learnings
Learnt about how to remove files from a directory.

### References


## moving files

You can also move files around with the mv command. The usage is simple:

```
hacker@dojo:~$ ls
my-file
hacker@dojo:~$ cat my-file
PWN!
hacker@dojo:~$ mv my-file your-file
hacker@dojo:~$ ls
your-file
hacker@dojo:~$ cat your-file
PWN!
hacker@dojo:~$

```

This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.

### Solve 
**Flag:** `pwn.college{0XNhJ9DK-mIn4MhW6rdr-wn5c1D.0VOxEzNxwSOwkjNzEzW}`

Used the mv command to move one file to another directory.

```bash

hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0XNhJ9DK-mIn4MhW6rdr-wn5c1D.0VOxEzNxwSOwkjNzEzW}

hacker@commands~moving-files:~$ 

```
### New Learnings
Learnt to use mv command to move a file from one directory to another.

### References


## hidden files

Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:

```
hacker@dojo:~$ touch pwn
hacker@dojo:~$ touch .college
hacker@dojo:~$ ls
pwn
hacker@dojo:~$ ls -a
.college	pwn
hacker@dojo:~$

```
Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.

### Solve
**Flag:** `pwn.college{866_XzgVLr19gBum494Vhf4bIqM.QXwUDO0wSOwkjNzEzW}`

Used the ls -a command to list the hidden files inside the / directory and found the flag file. Then read the file using the cat command.

```bash

hacker@commands~hidden-files:/$ ls -a
.  ..  .dockerenv  .flag-19943831310458  bin  boot  challenge  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~hidden-files:/$ cat .flag-19943831310458
pwn.college{866_XzgVLr19gBum494Vhf4bIqM.QXwUDO0wSOwkjNzEzW}
hacker@commands~hidden-files:/$ 

```
### New Learnings
Learnt to use ls to find hidden files.

### References


## An Epic Filesystem Quest

With your knowledge of cd, ls, and cat, we're ready to play a little game!

We'll start it out in /. Normally:

```
hacker@dojo:~$ cd /
hacker@dojo:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  dev        flag  lib   lib64  media   opt  root  sbin  sys  usr

```
That's a lot of contents! One day, you will be quite familiar with them, but already, you might recognize the flag file and the challenge directory.

In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

Your first clue is in /. Head on over there.
Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
cat that file to read the clue!
Depending on what the clue says, head on over to the next directory (or don't!).
Follow the clues to the flag!

### Solve
**Flag:** `pwn.college{sK_f2tz_scHkrKAGRZkGYE9vzcF.QX5IDO0wSOwkjNzEzW}`

Used the cd and ls commands to navigate through directories and used the cat command to read the files
and find clues for the next step.

```bash
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.  ..  .dockerenv  README  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat README
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/accessibility/braille

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/linux/linux-5.4/drivers/accessibility/braille
Connected!                                                                        
hacker@commands~an-epic-filesystem-quest:~$ cd /
\hacker@commands~an-epic-filesystem-quest:/$ ls -a
.  ..  .dockerenv  README  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat README
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/accessibility/braille

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/linux/linux-5.4/drivers/accessibility/braille
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ ls -a
.  ..  Makefile  POINTER  braille_console.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ cat POINTER
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/arch/arm

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ cd /opt/linux/linux-5.4/arch/arm
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm$ ls -a
.              configs       mach-asm9260   mach-digicolor   mach-hisi        mach-meson     mach-nspire     mach-rda       mach-socfpga   mach-ux500      oprofile        vfp
..             crypto        mach-aspeed    mach-dove        mach-imx         mach-milbeaut  mach-omap1      mach-realview  mach-spear     mach-versatile  plat-omap       xen
.SNIPPET       include       mach-at91      mach-ebsa110     mach-integrator  mach-mmp       mach-omap2      mach-rockchip  mach-sti       mach-vexpress   plat-orion
Kconfig        kernel        mach-axxia     mach-efm32       mach-iop32x      mach-moxart    mach-orion5x    mach-rpc       mach-stm32     mach-vt8500     plat-pxa
Kconfig-nommu  kvm           mach-bcm       mach-ep93xx      mach-ixp4xx      mach-mv78xx0   mach-oxnas      mach-s3c24xx   mach-sunxi     mach-zx         plat-samsung
Connected!                                                                        
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.  ..  .dockerenv  README  bin  boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat README
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/accessibility/braille

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/linux/linux-5.4/drivers/accessibility/braille
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ ls -a
.  ..  Makefile  POINTER  braille_console.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ cat POINTER
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/arch/arm

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/accessibility/braille$ cd /opt/linux/linux-5.4/arch/arm
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm$ ls -a
.              configs       mach-asm9260   mach-digicolor   mach-hisi        mach-meson     mach-nspire     mach-rda       mach-socfpga   mach-ux500      oprofile        vfp
..             crypto        mach-aspeed    mach-dove        mach-imx         mach-milbeaut  mach-omap1      mach-realview  mach-spear     mach-versatile  plat-omap       xen
.SNIPPET       include       mach-at91      mach-ebsa110     mach-integrator  mach-mmp       mach-omap2      mach-rockchip  mach-sti       mach-vexpress   plat-orion
Kconfig        kernel        mach-axxia     mach-efm32       mach-iop32x      mach-moxart    mach-orion5x    mach-rpc       mach-stm32     mach-vt8500     plat-pxa
Kconfig-nommu  kvm           mach-bcm       mach-ep93xx      mach-ixp4xx      mach-mv78xx0   mach-oxnas      mach-s3c24xx   mach-sunxi     mach-zx         plat-samsung
Kconfig.debug  lib           mach-berlin    mach-exynos      mach-keystone    mach-mvebu     mach-picoxcell  mach-s3c64xx   mach-tango     mach-zynq       plat-versatile
Makefile       mach-actions  mach-clps711x  mach-footbridge  mach-lpc18xx     mach-mxs       mach-prima2     mach-s5pv210   mach-tegra     mm              probes
boot           mach-alpine   mach-cns3xxx   mach-gemini      mach-lpc32xx     mach-nomadik   mach-pxa        mach-sa1100    mach-u300      net             tools
common         mach-artpec   mach-davinci   mach-highbank    mach-mediatek    mach-npcm      mach-qcom       mach-shmobile  mach-uniphier  nwfpe           vdso
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm$ cat .SNIPPET
Great sleuthing!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Pagella/Size4
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/arm$ cd /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Pagella/Size4
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Pagella/Size4$ ls -a
.  ..  ALERT  Regular
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Pagella/Size4$ cat ALERT
Congratulations, you found the clue!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Gyre-Pagella/Size4$ cd /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ ls -a
.  ..  MESSAGE  N.pl  Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ cat MESSAGE
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/arch/powerpc/math-emu

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ ls /opt/linux/linux-5.4/arch/powerpc/math-emu
Makefile         fadd.c   fcmpu.c   fdiv.c   fmadds.c  fmsubs.c  fnabs.c   fnmadds.c  fre.c   frsqrte.c   fsqrt.c   fsubs.c  math.c      mffs.c    mtfsf.c   stfiwx.c
SPOILER-TRAPPED  fadds.c  fctiw.c   fdivs.c  fmr.c     fmul.c    fneg.c    fnmsub.c   fres.c  frsqrtes.c  fsqrts.c  lfd.c    math_efp.c  mtfsb0.c  mtfsfi.c  stfs.c
fabs.c           fcmpo.c  fctiwz.c  fmadd.c  fmsub.c   fmuls.c   fnmadd.c  fnmsubs.c  frsp.c  fsel.c      fsub.c    lfs.c    mcrfs.c     mtfsb1.c  stfd.c    udivmodti4.c
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ cat /opt/linux/linux-5.4/arch/powerpc/math-emu/SPOILER-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd64

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ cd /usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd6
bash: cd: /usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd6: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/NFKDQC$ cd /usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd64
hacker@commands~an-epic-filesystem-quest:/usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd64$ ls -a
.  ..  TEASER  jre
hacker@commands~an-epic-filesystem-quest:/usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd64$ cat TEASER
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/drivers/net/ethernet/dec

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/gdb/auto-load/usr/lib/jvm/java-17-openjdk-amd64$ cd /opt/linux/linux-5.4/drivers/net/ethernet/dec
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/dec$ ls -a
.  ..  .DOSSIER  .built-in.a.cmd  Kconfig  Makefile  built-in.a  tulip
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/dec$ cat .DOSSIER
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/pickleshare-0.7.5.dist-info

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/dec$ cd /usr/local/lib/python3.8/dist-packages/pickleshare-0.7.5.dist-info
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pickleshare-0.7.5.dist-info$ ls -a
.  ..  DESCRIPTION.rst  INFO  INSTALLER  METADATA  RECORD  WHEEL  metadata.json  top_level.txt
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pickleshare-0.7.5.dist-info$ cat INFO
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{sK_f2tz_scHkrKAGRZkGYE9vzcF.QX5IDO0wSOwkjNzEzW}
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pickleshare-0.7.5.dist-info$ 

```
### New Learnings 
Learnt to know to where to use ls and ls -a and also practiced more of cat and cd commands.

### References


## making directories

We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!

Watch:

```
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ mkdir my_directory
hacker@dojo:/tmp$ ls
my_directory
hacker@dojo:/tmp$ cd my_directory
hacker@dojo:/tmp/my_directory$ touch my_file
hacker@dojo:/tmp/my_directory$ ls
my_file
hacker@dojo:/tmp/my_directory$ ls /tmp/my_directory/my_file
/tmp/my_directory/my_file
hacker@dojo:/tmp/my_directory$

```
Now, go forth and create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!

### Solve 
**Flag:** `pwn.college{YzgZBjgUhlnhL_1afsP0NUZjcF5.QXxMDO0wSOwkjNzEzW}`

Used the cd command to change directory to /tmp then made a directory using the mkdir command and then used the touch command to make a file in the new directory.

```bash

hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{YzgZBjgUhlnhL_1afsP0NUZjcF5.QXxMDO0wSOwkjNzEzW}
hacker@commands~making-directories:/tmp/pwn$ 

```
### New Learnings
Learnt to use the mkdir command to create new directories.

### References


## finding files

So now we know how to list, read, and create files. But how do we find them? We use the find command!

The find command takes optional arguments describing the search criteria and the search location. If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory (.). For example:

```
hacker@dojo:~$ mkdir my_directory
hacker@dojo:~$ mkdir my_directory/my_subdirectory
hacker@dojo:~$ touch my_directory/my_file
hacker@dojo:~$ touch my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find
.
./my_directory
./my_directory/my_subdirectory
./my_directory/my_subdirectory/my_subfile
./my_directory/my_file
hacker@dojo:~$

```
And when specifying the search location:

```
hacker@dojo:~$ find my_directory/my_subdirectory
my_directory/my_subdirectory
my_directory/my_subdirectory/my_subfile
hacker@dojo:~$

```
And, of course, we can specify the criteria! For example, here, we filter by name:

```
hacker@dojo:~$ find -name my_subfile
./my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find -name my_subdirectory
./my_directory/my_subdirectory
hacker@dojo:~$

```
You can search the whole filesystem if you want!

```
hacker@dojo:~$ find / -name hacker
/home/hacker
hacker@dojo:~$

```
Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!

Several notes. First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!

### Solve
**Flag:** `pwn.college{s-RpBQ6B6nCbDPLvGZVsY9LM1sw.QXyMDO0wSOwkjNzEzW}`

Used the find command to find the flag file by name in the root directory, then used the cat command to read the path.

```bash

hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/lib/python3/dist-packages/sage/ext/__pycache__/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/lib/python3/dist-packages/sage/ext/__pycache__/flag
pwn.college{s-RpBQ6B6nCbDPLvGZVsY9LM1sw.QXyMDO0wSOwkjNzEzW}hacker@commands~finding-files:~$

```
### New Learnings
Learnt how to use the find command to find files by name.

### References


## Linking Files

If you use Linux (or computers) for any reasonable length of time to do any real work, you will eventually run into some variant of the following situation: you want two programs to access the same data, but the programs expect that data to be in two different locations. Luckily, Linux provides a solution to this quandary: links.

Links come in two flavors: hard and soft (also known as symbolic) links. We'll differentiate the two with an analogy:

A hard link is when you address your apartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).
A soft link is when you move apartments and have the postal service automatically forward your mail from your old place to your new place.
In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediately yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.

Hard links sound simpler to most people (case in point, I explained it in one sentence above, versus two for soft links), but they have various downsides and implementation gotchas that make soft/symbolic links, by far, the more popular alternative.

In this challenge, we will learn about symbolic links (also known as symlinks). Symbolic links are created with the ln command with the -s argument, like so:

```
hacker@dojo:~$ cat /tmp/myfile
This is my file!
hacker@dojo:~$ ln -s /tmp/myfile /home/hacker/ourfile
hacker@dojo:~$ cat ~/ourfile
This is my file!
hacker@dojo:~$

```
You can see that accessing the symlink results in getting the original file contents! Also, you can see the usage of ln -s. Note that the original file path comes before the link path in the command!

A symlink can be identified as such with a few methods. For example, the file command, which takes a filename and tells you what type of file it is, will recognize symlinks:

```
hacker@dojo:~$ file /tmp/myfile
/tmp/myfile: ASCII text
hacker@dojo:~$ file ~/ourfile
/home/hacker/ourfile: symbolic link to /tmp/myfile
hacker@dojo:~$

```
Okay, now you try it! In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag!

### Solve 
**Flag:** `pwn.college{IkZTGgBo5ObnAKzeFi1NkZe5QVs.QX5ETN1wSOwkjNzEzW}`

Since, it did not allow to create symbolic link, I had to rename the existing symlink. Then, I created a symlinkthat points to the real flag.

```bash
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
ln: failed to create symbolic link '/home/hacker/not-the-flag': File exists
hacker@commands~linking-files:~$ file /home/hacker/not-the-flag
/home/hacker/not-the-flag: symbolic link to /challenge/catflag
hacker@commands~linking-files:~$ mv -v /home/hacker/not-the-flag /home/hacker/not-the-flag.orig
renamed '/home/hacker/not-the-flag' -> '/home/hacker/not-the-flag.orig'
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{IkZTGgBo5ObnAKzeFi1NkZe5QVs.QX5ETN1wSOwkjNzEzW}
hacker@commands~linking-files:~$

```
### New Learnings
Learnt about symbolic links and hard links and its applications.

### References
https://www.youtube.com/watch?v=m55AtwjBXpE&list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC&t=10s   