# Commandline and Your Environment

For advanced commandline documentation and exercises please checkout [this page](
https://github.com/ndanielsen/intro-cli-git-github/blob/master/materials/4-Command-Line-Advanced.md).



## Environmental Variables

Environment variables (ENVs) contain information about your login session, stored for the system shell (terminal) to use when executing commands. They exist whether you’re using Linux, Mac, or Windows. Many of these variables are set by default during installation or user creation.

ENVs are helpful because they allow you to separate code/ logic from configuration. 

**ProTip:** Checkout this reading from the Twelve Factor about on [configuration](https://12factor.net/config).


### Accessing Current ENVs

Let's find the home directory on our machine:

```

$ echo $HOME

```

This is the user's home directory. Variables have a `$` in front of them.

### Let's Look at All of them

```

$ env

```


These are all of the ENVs for your user. It is a lot of information. We can scroll through it slowly using the pipe operator and `less`. 

```

$ env | less

```


Hint: You can press the `q` button to escape.


### Setting Envs - Temporary

Sometimes it is helpful to temporary setting ENVs for a program that is running or a short lived process. 

We can temporarily set them for user in our programs with `export` before them in a KEY=VALUE format.

```

$ export MY_NAME=Nathan
$ export FULL_NAME="Nathan Danielsen"

$ echo $MY_NAME
$ echo $FULL_NAME

```


You can also add an ENV before you run a script.

```

$ FRIEND_NAME="Bonnie Wolfe" bash scripts/shoutout.sh

```


#### EXERCISES:

Set these ENVs in your terminal and then print them back.

1) `HACK4LA` with value of "rocks"


2) `LOS_ANGELES` with value of "Has the best icecream"


#### BONUS EXERCISE:
- Modify the `shoutout.sh` to say something nice about someone who you admire using one or more ENVs.


### Setting Envs - Permament

You can set your own persistent environment variables in your shell (terminal) configuration file, the most common of which for macs is `~/.bash_profile` or in linux is `~/.bashrc`.


This is how you can view it on a mac:

```

$ cat ~/.bash_profile

```


We're not going to configure anything in the `bash_profile` today. It is risky to do in a workshop setting. Editing it will require the use of `sudo`. 

Check out [`4-Command-Line-Advanced.md`](https://github.com/ndanielsen/intro-cli-git-github/blob/master/materials/4-Command-Line-Advanced.md) for details on the use of `sudo`.


## Bash Scripts

Bash scripts can be used for various purposes, such as executing a shell command, running multiple commands together, customizing administrative tasks, performing task automation etc.

### Running a simple script

We can run a simple bash script like this. 

```
$ bash scripts/hello_class.sh

```

### Shebang

The first line on a bash script to tell the computer what interpreter (computer language / runtime) should execute the script.

Look in `scripts/` for working examples.

Examples:

### Bash (terminal)

script: `./scripts/hello_class.sh`

file contents:
```

#!/bin/bash

echo "Hello class!"

```

### Python (programming language / runtime)

If you don't have python3 installed on your computer, it will not work.

script: `./scripts/hello_world.py`

```

#!/usr/bin/env python3

print('hello world!')

```

## Make script executable by your computer

We can only run files on our computers that have the correct permissions. 

`chmod` modifies the permissions of the file specified by the file name to the permissions specified by permissions.

To make these two scripts executable by everyone, I had to run:

```

$ chmod 777 scripts/hello_class.sh
$ chmod 777 scripts/hello_world.py

```

The numbers after `chmod` correspond to permissions for the user, group and everybody else.

For example above:
- The first 7 sets the permissions for the user, 
- The second 7 sets the permissions for the group
- The third 7 sets the permissions for everybody else.

```
Permissions:
    7, rwx, read, write, and execute
    6, rw-, read and write
    5, r-x, read and execute
    4, r--, read-only
    3, -wx, write and execute
    2, -w-, write only
    1, --x, execute only
    0, ---, none
```

### Exercise

Create a script with name of `create_blog.sh` to create a `my_blog` project. 

The script should:

Create a folder called `my_blog`

Inside of that folder:
- Create a README.md file
- Create an index.html file
- Create a `posts/` folder
- Inside of `posts/` create a file  `civic_hacking_is_cool.txt`
- Inside of `posts/` create a file  `hack4la_dtla_is_great.txt`
- Inside of `posts/` create a file  `los_angeles_best_icecream.txt`

Should be runnable via `./create_blog.sh` and also `bash create_blog.sh`

**Extra Credit**

Create the README.md with some content aready inside of it.

ie: `echo 'Hello, world.' > Newfile.txt`

Hint: You can navigate or run `cd` inside of a script.



### Other Help and Hints

If you are struggling, please checkout the materials in [`Introduction to commandline, git and github`](https://github.com/ndanielsen/intro-cli-git-github) 
