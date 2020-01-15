# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
/Users/stephenjohnson/projects/wats1030-intro-to-unix


* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE                         challenge_files                 nix_scavenger_hunt_stretch.md
README.md                       nix_scavenger_hunt.md           super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
total 48
drwxr-xr-x    9 stephenjohnson  staff   288B Jan 13 21:02 .
drwxr-xr-x   16 stephenjohnson  staff   512B Jan 13 21:02 ..
drwxr-xr-x   14 stephenjohnson  staff   448B Jan 13 21:02 .git
-rw-r--r--    1 stephenjohnson  staff   1.1K Jan 13 21:02 LICENSE
-rw-r--r--    1 stephenjohnson  staff   2.7K Jan 13 21:02 README.md
drwxr-xr-x  111 stephenjohnson  staff   3.5K Jan 13 21:02 challenge_files
-rw-r--r--    1 stephenjohnson  staff   5.7K Jan 14 21:06 nix_scavenger_hunt.md
-rw-r--r--    1 stephenjohnson  staff   319B Jan 13 21:02 nix_scavenger_hunt_stretch.md
-rw-r--r--    1 stephenjohnson  staff   255B Jan 13 21:02 super_scavengers.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
What manual page do you want? (after inputing 'man')
'a': Include directory entries whose names begin with a dot (.).
'l': (The numeric digit ``one''.)  Force output to be one entry per line.  This is the default when output is not to a terminal.
'h': When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte in order to
    reduce the number of digits to three or less using base 2 for sizes.


* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
Applications    System          Volumes         cores           etc             opt             sbin            usr
Library         Users           bin             dev             home            private         tmp             var


* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
Stephens-MacBook-Pro:~ stephenjohnson$ cd /
Stephens-MacBook-Pro:/ stephenjohnson$ ls
Applications    System          Volumes         cores           etc             opt             sbin            usr
Library         Users           bin             dev             home            private         tmp             var
Stephens-MacBook-Pro:/ stephenjohnson$ pwd
/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/Users/stephenjohnson

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
(files with .demo)
2015_special_stuff.demo 
cloaked-wookie.demo
scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
Stephens-MacBook-Pro:challenge_files stephenjohnson$ cd -
/Users/stephenjohnson/projects/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*
cd -

* Press the up arrow a few more times. *What do you see?*
pushing the up arrow a few more times, shows the recent commands you inputed 

* Run the `history` command. *What do you see?*
A list of several commands that were inputed
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
stephenjohnson

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
stephenjohnson console  Jan 14 20:41 
stephenjohnson ttys000  Jan 14 20:50

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
22:54  up  2:13, 2 users, load averages: 1.66 1.66 1.54

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
From what I gather, this lists all of the files have on your computer. I also see the same list from 'history'.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
I see CPU usage and processes information.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*


* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
