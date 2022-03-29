# 💾 The Terminal

## Opening the Terminal and Prompt

Always remember: **Treat the terminal like a text-only file explorer**. It is not a calculator or hacking machine (although it can be) – it is simply a way to access, modify, and delete files or software using text commands. Although the terminal of a completely foreign operating system may sound really intimidating at first, there are only a couple commands that you need to fully memorize!

To start, let's open the terminal. In Kali, a GUI button which has a `>_` symbol is available at the top left. However, all distros universally accept the shortcut `Ctrl + Alt + T`.

You should be getting an odd textbox that looks like this:

```bash
user@host:~$ █
```

Note: Not all distros have this format. Some are formatted like `[user@host ~]$` or `(user@host)-[~]$`, and some could just be a `user$`.

All this gibberish is called a **prompt**, and is hosted by an environmental variable called **PS1**, or **primary prompt variable**. Let's break this down:

* `user`: Indicates the user you logged in with.
* `host`: The name of your Linux system.
* `~`: Indicates the **home directory**, which is the default **present working directory** of Linux distros (we'll talk about this shortly). This will change depending on your PWD (ex. `/home`).
* `$`: Indicates user type. Regular users are indicated with a `$`, whilst root/super users are indicated with a `#` (or `%` for csh, zsh and tcsh).
* `@`, `:`: Separators, nothing more to it.

If you want to change your PS1, learn more [here](https://linuxconfig.org/bash-prompt-basics).

## Your First Command

Let’s run our first command:

```bash
user@host:~$ pwd
```

You should be getting an output that looks something like:

```bash
/home/user
```

The `pwd` command stands for “present working directory”, and requests the system for information regarding what folder you are currently accessing (Note: It's good to imagine the terminal as a physical entity, working its way through folders with commands). The **directory** is simply the path of files you need to take to reach the folder you are currently in, like street directions. `Kali` is the name of the default user, and most files you create in the GUI are located here, such as the `Desktop` and `Downloads` folder. **The root directory of Linux is** `/`.

If a command has finished running, it will create a newline and the prompt will come back:

```bash
user@host:~$ pwd
/home/user
user@host:~$ █
```

This is perfectly normal. However, sometimes a command will do this:

```bash
user@host:~$ nc 10.0.0.1 # DON'T TRY THIS COMMAND, IT IS AN EXAMPLE


```

This state is called a _hung_ or _frozen_ terminal. To interrupt or exit the operation, press `Ctrl + C` or `Delete`.

Note that although your commands may run, they may not always return an output. For example, creating a file with `touch` (we'll talk about this later) executes perfectly fine, but doesn't tell the user that it has succeeded; it will only return **errors**. Always be careful when executing code. **Never paste code you don't understand into the terminal.**

## The Anatomy of a Command

A single command will usually look like this:

```bash
command -f arguments # SINGLE CHARACTER
command --flag arguments # MULTI-CHARACTER
```

There are two types of commands:

1. **Built-in commands**: A name which is associated with a software pre-installed into your environment.
2. **External commands**: The command is either a pre-defined name by the operating system, or a custom one installed by other software. When you want your terminal to run custom software like nmap, you could type nmap to run it, which typically wouldn’t be possible without it installed.

#### Flags

**Flags** are additional user-inputted parameters which explain to the system how you want the program to run (often called “arguments”).

Be careful when typing flags, as there is a difference between a single dash and double dash! A single dash means the flag is **single-character**, while a double dash means the flag is **multi-character**. If you typed `-flag` instead of `--flag` the terminal would read it as `-f -l -a -g`, which is really not good.

Note that single-letter flags are often shorthand for longer ones. For example, `ls -a` is the same thing as `ls --all`.

***

#### Check-up

1. What should you always think of the terminal as?
2. Where are all your personal files located?
3. What is Linux’s root directory?
4. What do flags do, and what is the difference between a single-dash and double-dash flag?
5. BONUS: What would happen if I tried to run the command wireshark without the software “Wireshark” installed?
