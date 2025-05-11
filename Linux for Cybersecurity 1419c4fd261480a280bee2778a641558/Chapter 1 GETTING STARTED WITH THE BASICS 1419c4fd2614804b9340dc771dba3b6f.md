# Chapter 1  GETTING STARTED WITH
THE BASICS

# Introductory Terms and Concepts

## Binaries

This term refers to files that can be executed, similar to
executables in Windows. Binaries generally reside in the /usr/bin or
usr/sbin directory and include utilities such as ps, cat, ls, and ifconfig
(we’ll touch on all of four of these in this chapter) as well as applications such as the wireless hacking tool aircrack-ng and the intrusion
detection system (IDS) Snort.

## Case sensitivity

Unlike Windows, the Linux filesystem is case sensitive. This means that Desktop is different from desktop, which is different
from DeskTop. Each of these would represent a different file or directory
name. Many people coming from a Windows environment can find this
frustrating. If you get the error message “file or directory not found”
and you are sure the file or directory exists, you probably need to check
your case.

## Directory

 This is the same as a folder in Windows. A directory provides a way of organizing files, usually in a hierarchical manner.

## Home

 Each user has their own /home directory, and this is generally
where files you create will be saved by default.

## Kali

 Kali Linux is a distribution of Linux specifically designed for
penetration testing. It has hundreds of tools preinstalled, saving you
the hours it would take to download and install them yourself. I will be
using the latest version of Kali at the time of this writing: Kali 2018.2,
first released in April 2018.

## root

 Like nearly every operating system, Linux has an administrator
or superuser account, designed for use by a trusted person who can do
nearly anything on the system. This would include such things as reconfiguring the system, adding users, and changing passwords. In Linux,
that account is called root. As a hacker or pentester, you will often use
the root account to give yourself control over the system. In fact, many
hacker tools require that you use the root account.

## Shell

This is an environment and interpreter for running commands
in Linux. The most widely used shell is bash, which stands for Bourneagain shell, but other popular shells include the C shell and Z shell. I
will be using the bash shell exclusively in this book.

## Terminal

This is a command line interface (CLI).

# The Linux Filesystem

/root The home directory of the all-powerful root user

/etc Generally contains the Linux configuration files—files that control when and how programs start up

/home The user’s home directory

/mnt Where other filesystems are attached or mounted to the
filesystem

/media Where CDs and USB devices are usually attached or mounted
to the filesystem

/bin Where application binaries (the equivalent of executables in
Microsoft Windows or applications in macOS) reside

/lib Where you’ll find libraries (shared programs that are similar to
Windows DLLs)

# Command lines

`pwd` - command, pwd, returns your
location within the directory structure.

`whoami` - If you’ve forgotten whether you’re logged in as root or another user, you
can use the whoami command to see which user you’re logged

`cd` -  To change directories from the terminal, use the change directory command,
cd.

`cd ..` - To move up one level in the file structure (toward the root of the file
structure, or /), we use cd followed by double dots (..), as shown here:

`cd ../ ..`  - move twice

`ls` - To see the contents of a directory (the files and subdirectories), we can use
the ls (list) command. This is very similar to the dir command in Windows.

`ls -l` - long listing

`ls -la` - a shows hidden content

`example --help` -  guidance for hacking tool use

`-? and -h` - are options too

`man "example"` - providing you with more
detailed information than the help screen.

### Finding Stuff

`locate “example”` - this command will go through your entire
filesystem and locate every occurrence of that word.

`whereis “binary file”` - If you’re looking for a binary file, you can use the whereis command to
locate it. This command returns not only the location of the binary but
also its source and man page if they are available.

`which “example”` - In short, the `which` command in Linux tells you the **location** (path) of a command or program in the directories listed in the **PATH** variable.

`find [path] [conditions] [actions]`

**[path]** - The directory where you want to start the search. If you want to search the entire system, use `/`. To search from the current directory, use `.`

**[conditions]**: The criteria to filter the files (e.g., file name, type, size).
**[actions]**: What to do with the found files (e.g., print their names, delete them, etc

kali >find /(1) -type f(2) -name apache2 (3)
First I state the directory in which to start the search, in this case / .
Then I specify which type of file to search for, in this case f for an ordinary file . Last, I give the name of the file I’m searching for, in this case
apache2 .

`ps "example`"-  command is used to display information about processes running on the machine.

## `grep`

The  command is used to search for specific keywords in text or files. It's especially useful when combined with piping, where the output of one command is used as input for another command.

```perl
perl
Copy code
grep "keyword" filename

```

This will search for the word `keyword` in the specified file.

If you want to search for the keyword `error` in a log file, use:

```perl
perl
Copy code
grep "error" /var/log/syslog

```

## Piping

Piping (`|`) allows you to take the output of one command and pass it to another. For example, if you want to list all files and search for the word `apache2`, you can combine `ls` and `grep` like this:

```bash
bash
Copy code
ls -l | grep "apache2"

```

This command lists files and filters the results to show only those that contain `apache2`.

## Modifying Files and Directories

### `cat`

`cat > “example”` - creates file with name example(and after that u input when u done ctrl + d)/or overwrite 

`cat example` - to see existing file

`cat >> “example”` - you will add content in existing file

### `touch`

`touch “example”` - This command was originally developed so a user could simply touch a file to change some of its details, such as the date it was created or modified. However, if the file
doesn’t already exist, this command creates that file by default.

### `mkdir`

`mkdir “example”` - The command for creating a directory in Linux is mkdir, a contraction of
make directory. To navigate to this newly created directory, simply enter this:
`cd newdirectory`

### `cp`

`cp oldfile root/newdirectory/newfile`  -  copy file from old directory to new directory with new name
The `cp` command works for both files and directories. To copy a directory, you need to use the `-r`      `cp -r olddirectory /root/newdirectory`

`mv saba sabanew` - command can be used to move a file or directory to a new location or simply to give an existing file a new name.  saba to sabanew

`rm "sabanew"` - to remove file

`rm -r “directory”` - remove directory (`rmdir “directory` - safe option)i