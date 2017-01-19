# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite Unix or Linux operating system. You are welcome and encouraged to consult any additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with this repository, so you will need to fork the repo into your own Github account and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. 
*Paste the output of the `pwd` command here:*
```
/home/cabox/workspace        
```
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. 
*What directories and files do you see when you run `ls`?*
```
LICENSE    
challenge_files        
nix_scavenger_hunt_stretch.md       
README.md  
nix_scavenger_hunt.md          
```
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. 
*How are the results different when you use the `-alh` options?*
```
When -alh comes back it lists the same files in the directory, plus files that have a '.' in front of them. It also gives more information about the file size and the time the file was created. 

drwxrwxr-x  4 cabox cabox 4.0K Jan 13 09:21 .                            
drwxr-xr-x 11 cabox cabox 4.0K Jan 13 14:24 ..                           
drwxrwxr-x  8 cabox cabox 4.0K Jan 13 09:21 .git                         
-rw-rw-r--  1 cabox cabox 1.1K Jan 13 09:21 LICENSE                      
-rw-rw-r--  1 cabox cabox 2.7K Jan 19 01:25 README.md                    
drwxrwxr-x  7 cabox cabox 4.0K Jan 13 09:21 challenge_files              
-rw-rw-r--  1 cabox cabox 5.6K Jan 19 01:50 nix_scavenger_hunt.md        
-rw-rw-r--  1 cabox cabox  317 Jan 13 09:21nix_scavenger_hunt_stretch.md  
```
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. 
*Write down what those options do?*
```
-a shows all (including hidden)
-l use a long listing format
-h --human-readable with -l, print sizes in human readable format
```
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. 
*What files and directories do you see listed?*
```
bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr            
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var     
```
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) 
*Then run `pwd` and paste the output here:*
I used 'cd ..' to move up in the directory
```
/home       
```
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. 
*Run `pwd` and paste the response here:*
```
/home/cabox   
```
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. 
*How many files do you find?*
I tried to use cd challenge_files to move to that directory but needed to first cd to the workspace and then cd to the directory. After that I used ls *.demo to list only files with the .demo pattern
```
3
2015_special_stuff.demo  cloaked-wookie.demo  scooter-double-mamba.demo  
```
* Use the `cd` command to move "up" one directory. 
*Where are you in the filesystem now?*
I used 'cd ..'
```
/home/cabox/workspace  
```
* Press the up arrow on your keyboard. 
*What just happened?*
```
Cool! It recalled the last command I used
```
* Press the up arrow a few more times. 
*What do you see?*
```
It scrolls through the commands I used, down arrow scrolls forward through the command history. 
```
* Run the `history` command. 
*What do you see?*
```
Allllll the commands I used, mostly lots of pwd. 
```

### Observing the System

* Discover what account you are logged into using the `whoami` command. 
*What username are you currently using?*
```
cabox         
```
* Discover who else is on your system with the `who` command. 
*Are any other users using your system? If so, list them here:*
```
No, it lists more information about my username. 
```
* How long has your system been running? Use `uptime` to see, and 
*paste the result here:*
```
 02:27:41 up  1:08,  1 user,  load average: 0.00, 0.00, 0.00  
 ```
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) 
*How do you interpret what you see here?*
```
ps displays the current processes running
a = show processes for all users
u = display the process's user/owner
x = also show processes not attached to a terminal
```
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) 
*How do you interpret what you see here?*
```
It looks like a real-time listing of the processes running
```

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. 
*How many files did you find?*
```
2
credit_cards.txt   credit_cards2.txt
```
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) 
*What is the date in the file you have viewed?*
```
Last updated: 01-15-2015
```
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. 
*Where is that file located?*
```
tmp
```
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). 
*How many files did you find?*
```
$ grep 'WA' *.user 
2
Britt-Erdman.user:O'Harachester, WA 37261                                                   
Lissie-Strosin.user:Jewessfurt, WA 00816-7241  
```
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. 
*Paste the result showing the file and line where the word "Waldo" shows up.*
```
$ grep -r 'Waldo' challenge_files
challenge_files/serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Wald
o sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. 
Explicabo vel esse blanditiis dolorem culpa non quia.
```

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. 
*What do you see in the `files.txt` file?*
```
$ ls>files.txt
$ more files.txt
LICENSE                                                                                     
README.md                                                                                   
challenge_files                                                                             
files.txt                                                                                   
nix_scavenger_hunt.md                                                                       
nix_scavenger_hunt_stretch.md    
nix_scavenger_hunt_stretch
```
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. 
*Describe what you see when you run `ls -alh | more`.*
```
I see the results listed from top to the end of the page, and then --More-- leading to more results
```
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. 
*Paste the list of processes that reference your username here:*
```
root       518  0.0  0.6  63876  3480 ?        Ss   02:43   0:00 sshd: cabox [priv]         
cabox      520  0.0  0.2  63876  1468 ?        S    02:43   0:00 sshd: cabox@pts/0          
cabox      521  0.0  0.8  20632  4556 pts/0    Ss+  02:43   0:00 -bash                      
root      1149  0.0  0.6  63876  3480 ?        Ss   03:06   0:00 sshd: cabox [priv]         
cabox     1151  0.0  0.2  64008  1488 ?        S    03:06   0:00 sshd: cabox@pts/1          
cabox     1152  0.0  0.8  20564  4484 pts/1    Ss   03:06   0:00 -bash                      
root      1354  0.0  0.6  63876  3328 ?        Ss   03:09   0:00 sshd: cabox [priv]         
cabox     1356  0.0  0.2  64008  1488 ?        S    03:09   0:00 sshd: cabox@notty          
cabox     1357  0.0  0.1  12776   852 ?        Ss   03:09   0:00 /usr/lib/openssh/sftp-serve
r                                                                                           
cabox     1368  0.0  0.2  15520  1140 pts/1    R+   03:17   0:00 ps aux                     
cabox     1369  0.0  0.1   8816   760 pts/1    S+   03:17   0:00 grep --color=auto cabox  
```

*DONE*
