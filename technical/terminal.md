# The Terminal (Command Line)

## Basics

The most widely used way to interact with a personal computer is through a Graphical User Interface (GUI). In a GUI we use our mouse and keyboard we can give instructions using menu-driven interactions.

GUIs were created in order to have an intuitive way of learning to use a computer, however it _scales extremely poorly_. Hence, we introduce the **command line interface (CLI)**.

You may hear the term 'shell' also mentioned. A Shell is both a CLI _and_ a scripting language. Using the Shell allows users to repeat tasks with or without modification as many times as we want. The most common and popular shell is Bash, which is the default set up on most Shells.

Sequences of Shell commands can be written into a _Script_ 

In the terminal, the character that appears automatically (in my case a % symbol) indicates to the terminal that it needs to enter whatever follows.

## Inputs

- `whoami` will return the username of the current terminal user.
- `ls` is short for listing and will list the contents of the current directory
  - we can add `-F` to this command and our CLI will add an indicator as to what each file is (trailing `/` indicates a directory, `@` indicates a link, `*` inidcates an executable).
- `pwd` stands for 'Print Working Directory' and essentially shows where you are on your computer
  - In my directory, this prints `/Users/username`. At the top of this, we have `/` which we refer to as the _root directory_
- For Mac, by preceding the command with `man` our CLI prints the manual of the command. We can exit this by pressing 'q'
- `cd` stands for 'Change Directory', and does exactly that, we tell the CLI that we want to move into a new directory.
  - Printing `cd` without an argument will return us to our home directory
  - `cd ..` will return is to a level higher in our current working directory
- _Tab completion_ works by the user beginning typing, then pressing tab and the CLI will auto complete what the user is writing. For example `cd Do` followed the TAB key will completed `cd Documents`
- `mkdir` stands for make directory and makes a directory in our current working directory.
  - `-p` allows us to create a directory with nested sub-directories within it
- `touch` followed by a file name and specified extension will create a file in your current working directory
- `mv` followed by the specified thing to move and then the new location will move your selection to that new location. If you're not actually changing the location, then this command is the equivalent of renaming.
- `cp` copies a file instead of moving it.
  - `-r` adds a 'recursive' option to this command. The entire directory and all it's contents will be copied (backed up).
- `rm` is short for remove and is essentially a 'delete' command
  - `-r` adds a 'recursive' option to this command. The entire directory and all it's contents will be deleted.

###### Wildcards

We can use Wildcards in the terminal to access multiple files at once. There are two types of wildcard

- `*` is used to match zero or more characters. For example `*.txt` will select all .txt files in the current working directory
- `?` is used to match one character. For example, say we have two files, `methane.txt` and `ethane.txt`. by specifying `?ethane.txt` we would only be selecting `methane.txt`
