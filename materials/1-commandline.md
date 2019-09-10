# Commandline and Your Environment

For advanced commandline documentation and exercises please checkout (this page)[
https://github.com/ndanielsen/intro-cli-git-github/blob/master/materials/4-Command-Line-Advanced.md].



## Environmental Variables

Environment variables (ENVs) contain information about your login session, stored for the system shell (terminal) to use when executing commands. They exist whether you’re using Linux, Mac, or Windows. Many of these variables are set by default during installation or user creation.

ENVs are helpful because they allow you to separate code/ logic from configuration. 

Checkout this chapter reading from the Twelve Factor about on [configuration](https://12factor.net/config).


### Accessing Current ENVs

Let's find the home directory on our machine:

>$ echo $HOME

This is the user's home directory. Variables have the $ in front of them.

### Let's Look at All of them

>$ echo env


That's alot of information. Let's scroll through it slowly using the pipe operator and `less`. 

>$ echo env | less


Hint: You can press the `q` button to escape.


### Setting Envs - Temporary

We can temporarily set them for user in our programs like this:

>$ export MY_NAME=Nathan
>$ export FULL_NAME="Nathan Danielsen"

You can also add it before you run a script.

>$ FRIEND_NAME="Bonnie Wolfe" bash script/shoutout.sh



#### EXERCISES:

1) Set a these ENVs in your terminal and then print them back.

- HACK4LA=rocks
- LOS_ANGELES="Has the best icecream!"

2) Bonus: Modify the `shoutout.sh` to say something nice about someone who you admire using one or more ENVs.


### Setting Envs - Permament

You can set your own persistent environment variables in your shell (terminal) configuration file, the most common of which for macs is `~/.bash_profile` or in linux is `~/.bashrc`.


This is how you can view it on a mac:

>
>$ cat ~/.bash_profile
>

We're not going to configure anything in it today. It is risky to do in a workshop setting.

Likely, editing it will require the use of `sudo`. Check out the (`4-Command-Line-Advanced.md`)[https://github.com/ndanielsen/intro-cli-git-github/blob/master/materials/4-Command-Line-Advanced.md] for details on the use of `sudo`.

Please don't make changes during the workshop as I likely won't have time to fix your computer if you mess it up.


## Bash Scripts

Bash scripts can be used for various purposes, such as executing a shell command, running multiple commands together, customizing administrative tasks, performing task automation etc.

## Shebang

The first line on a bash script to tell the computer what interpreter (computer language / runtime) should execute the script with telling it which one.

Look in `scripts/` for working examples.

Examples:

### Bash (terminal)

script:
./scripts/hello_class.sh

file contents:
> #!/bin/bash
>
> echo "Hello class!"


script:
./scripts/hello_world.py

### Python (programming language / runtime)

> #!/usr/bin/env python3
>
> echo "Hello world!"


### Exercise

- Try to run these scripts on your computer.
- Bonus can you figure out the file permissions on those files?


## Make script executable (runnable) by your computer

We can only run files on our computers that have the correct permissions. 

`chmod` modifies the permissions of the file specified by file name to the permissions specified by permissions.

To make these two scripts executable by everyone, we need to run:

> chmod 777 scripts/hello_class.sh
> chmod 777 scripts/hello_world.py


The first 7 sets the permissions for the user, the second 7 sets the permissions for the group, and the third 7 sets the permissions for everybody else.


Permissions:
    7, rwx, read, write, and execute
    6, rw-, read and write
    5, r-x, read and execute
    4, r--, read-only
    3, -wx, write and execute
    2, -w-, write only
    1, --x, execute only
    0, ---, none



## Exercise







