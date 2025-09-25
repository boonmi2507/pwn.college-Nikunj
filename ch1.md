# Hello Hackers

## Intro to Commands
In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:
```
hacker@dojo:~$ whoami
hacker
hacker@dojo:~$
```
### Solve
**Flag:** `pwn.college{cUiNtyGlMQ4wpFLv_J-RgCiCn2e.QX3YjM1wSOwkjNzEzW}`

Here, I first executed the command whoami, which simply displayed hacker 

```bash
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{cUiNtyGlMQ4wpFLv_J-RgCiCn2e.QX3YjM1wSOwkjNzEzW}

```

### New Learnings
I learnt how use pwn.college using ssh.

### References 


## Intro to Arguments
Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments. Observe:
```
hacker@dojo:~$ echo Hello
Hello
hacker@dojo:~$
```

### Solve
**Flag:** `pwn.college{0nrmModnSqyi6gh5x2kAlhikBdT.QX4YjM1wSOwkjNzEzW}`

hello was the command and hackers was the argument.

```bash
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{0nrmModnSqyi6gh5x2kAlhikBdT.QX4YjM1wSOwkjNzEzW}

```

### New Learnings
I learnt about basic arguments and commands.

### References 


## Command History
You're going to type a lot of commands, and typing everything from scratch can be annoying. Luckily, the shell saves a history of every command you invoke.

You can scroll through those saved commands with the up/down arrow keys, and we'll practice that in this challenge. This challenge will inject the flag into your history. Bring up a terminal, hit the up arrow, and grab it! In other challenges, the history will contain the log of the commands you've run, so if you need to run a similar command again, you can use the arrow keys to scroll through and find it!

### Solve
**Flag:** `pwn.college{IlCs3fE5Qm4Qen6FFENeRYST0lC.0lNzEzNxwSOwkjNzEzW}`

```bash
hacker@hello~command-history:~$ the flag is pwn.college{IlCs3fE5Qm4Qen6FFENeRYST0lC.0lNzEzNxwSOwkjNzEzW}
```

### New Learnings
Learnt how to use up/down keys to navigate through history of commands.

### References 
