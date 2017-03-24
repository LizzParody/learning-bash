# The Linux Command Line

## Questions about Bash (that I answer using spaced repetition software)

# CHAPTER 1
-  What GUI?  
 Graphical user interface.  
 Is a type of user interface that allows users to interact with electronic devices through graphical icons and visual indicators. 

- What is CLI?  
Command line interface.  
s a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

- Graphical user interfaces make easy tasks easy, while command line interfaces make difficult tasks possible  
TRUE

- Que es Kernel?  
El kernel o núcleo es la parte central o el corazón del sistema operativo de linux. Se podría decir que el kernel funciona como intermediario entre el software y el hardware, puesto que es el que recibe las órdenes de los elementos del sistema operativo para enviárselas a este.

- What is shell?  
The shell is a program that takes keyboard commands and passes them to the operating system to carry out. We need the terminal to interact with the shell. The terminal give us access to the shell.

- What is bash?  
 The shell program in linux is called bash. Is an acronym for Bourne Again Shell.

- What is the shell prompt?  
```
Lizzies-MacBook-Pro:~ Lizzie$  //it it appears whenever the shell is ready to accept input.
```

- What happens If the last character of the prompt is a hash mark (#) rather than a dollar sign?  
It means that the terminal session has superuser privileges. This means that either we are logged in as the root user or we’ve selected a terminal emulator that provides superuser (administrative) privileges.

- What is the command history?   
If we press the up-arrow key, we see that the previous command reappears after the prompt.

- Print the date in the shell.
```
$ date
```
- Print the calendar in the shell.  
$ cal

- Check the current amount of free space on your disk drives.  
$ df

- What is a virtual terminal or virtual console?  
Even if we have no terminal emulator running, several terminal sessions continue to run behind the graphical desktop.

# CHAPTER 2 

- Print the current directory.  
$ pwd -> print current working directory. The directory we are working on.

- Change directory  
$ cd -> change directory

- List the content of the current directory.  
$ ls -> To list the files and directories in the current working directory, or any directory.

- How is called the first directory in the filesystem?    
The root directory. It contains files and subdirectories, which contain more files and subdirectories, and so on.

- Linux always have a single filesystem tree, regardless of how many drives or storage devices are attached to the computer. 
TRUE.

- What is a parent directory?  
The directory above the current working directory.

- What is a pathname?  
Is the route we take along the branches of the tree to get to the directory we want. Pathnames can be specified in one of two ways, as absolute pathnames or as relative pathnames.

- What is an Absolute Pathname?  
An absolute pathname begins with the root directory and follows the tree branch by branch until the path to the desired directory or file is completed.

- What is inside the directory /usr/bin?  
Is a directory on your system in which most of your system’s programs are installed.

- What is a Relative Pathname?  
A relative pathname starts from the working directory, not from the root directory.

- What is the difference between the special symbols . (dot) and .. (dot dot)?  
The . symbol refers to the working directory and the .. symbol refers to the working directory’s parent directory.

- Go to the /usr/bin directory. Then go back to  the /usr directory 
```
$ cd /usr/bin 
$ cd /usr -> using an absolute pathname
$cd .. -> using a relative pathname
```
- Go to the /usr directory. Then change the directory to /usr/bin directory.
```
$cd /usr
$ cd /usr/bin -> using an absolute pathname
$cd ./bin -> using a relative pathname (but you can omit the ./ because is implied)
$cd bin
```

- Changes the working directory to your home directory.
```
$ cd
```
- Changes the working directory to the previous working directory.
```
$ cd -
```
- Change the directory for the /Desktop/bob directory.
```
$ cd ~/Desktop/bob 
```

- Filenames that begin with a period character are hidden.
TRUE

- How can you list a file that is hidden?
```
$ ls -a
```

- Filenames and commands in Linux, as in Unix, are NOT case sensitive. The file- names File1 and file1 refer to same files.  
FALSE. They are case sensitive.

- Is very important to not embed spaces in filenames.
TRUE. Embedding spaces in filenames will make many command line tasks more difficult.

# CHAPTER 3

- List the files in /usr directory
```
$ ls /usr.
```
- List both directories, home directory and /usr directory
```
$ ls ~ /usr. -> Home is represented by ~
```

- Long list the root directory. Define which is the command, the option and the argument
$ ls -l / -> By adding -l to the command, we changed the output to the long format.
ls is the command, -l is the option and / is the argument.

So most commands look something like this:
        command -options arguments



- What does the following command does $ ls -lt?
The ls command is given two options, the l option to produce long format output, and the t option to sort the result by the file’s modification time.

- List the document directory to reverse the order of the sort of modification time.
$ cd /Document
$ ls -ltr -> the r command means reverse.

- The ls command has a large number of possible options. The most common are:  
-a  
-d  
-F  
-h  
-l  
-r  
-S  
-t  
What does each means?  

-a -> all (even the files that are hidden)  
-d -> directory  
-F -> classify (This option will append an indicator character to the end of each listed name for example, a forward slash if the name is a directory).  
-h -> human readable  
-l -> long format  
-r -> reverse  
-S -> sort result by file size.  
-t -> sort by modification time  



- Determine a file's type   
file filename -> When invoked, the file command will print a brief description of the file’s contents
$ file picture.jpg
picture.jpg: JPEG image data, JFIF standard 1.01

- What is the less command?  
Is a program to view text files.

- What is the ASCII text.  
Is short for American Standard Code for Information Interchange. This simple encoding scheme was first used on Teletype machines.

- Use the less command to see what's inside a file.  
$ less filename. To escape, press q.

- What is the /dev directory?  
This is a special directory that contains device nodes. “Everything is a file” also applies to devices. Here is where the kernel maintains a list of all the devices it understands.

- What is the /etc directory?  
The /etc directory contains all of the system-wide configuration files. It also contains a collection of shell scripts that start each of the system services at boot time. Everything in this directory should be readable text.

- What is the home directory?  
In normal configurations, each user is given a directory in /home. Ordinary users can write files only in their home directories. This limitation protects the system from errant user activity.

- What is the /sbin directory?  
This directory contains “system” binaries. These are programs that perform vital system tasks that are generally reserved for the superuser.

- What is the temp directory?  
The /tmp directory is intended for storage of temporary, transient files created by various programs. Some configurations cause this directory to be emptied each time the system is rebooted.

- What is the /usr directory?  
The /usr directory tree is likely the largest one on a Linux system. It contains all the programs and support files used by regular users.

- What is the /usr/bin directory?  
/usr/bin contains the executable programs installed by your Linux distribution. It is not uncommon for this directory to hold thousands of programs.

- What is the /usr/lib directory?  
The shared libraries for the programs in /usr/bin.

- What is the /usr/sbin directory?  
Contains more system administration programs.

- What is the /var directory?  
With the exception of /tmp and /home, the directories we have looked at so far remain relatively static; that is, their contents don’t change. The /var directory tree is where data that is likely to change is stored. Various databases, spool files, user mail, etc. are located here.

- What is a symbolic link?  
Is a special kind of file that points to another file, (also known as a soft link or symlink).  It simply points to another entry somewhere in the file system.  Not only does this solve the problem of the version upgrade of a program, but it also allows us to keep both versions on our machine. 

- What is a hard link?  
Hard links also allow files to have multiple names, but they do it in a different way.

# CHAPTER 4

- What is a wildcard?
Special characters to help you rapidly specify groups of filenames. (also known as globbing) It allows you to select filenames based on patterns of characters. 

- What are the matches of the following wildcards?
```
*
?
[*characters*
[!*characters*]
[[:class:]]
```
```
\*   // Any character
?   // Any single character
[ * characters* // any character that is a member of the set *characters*
[!*characters*]  // Any character that is not a member of the set characters
[[:class:]] // Any character that is a member of the specified class.
```

- Make a directory called example and add the files:
Gorilla
game.txt
Soup
3mosqueters 
Then list the files that begins with g.
```
$ mkdir example
$ cd example
$ touch gorilla game soup
$ ls ./g*
```

- Now print the files that begins with g and ends with .txt
```
$ ls g*txt
```

- List any files beginning with s, o w.
```
ls [sw]*
```

- List any files beginning with upper case.
```
ls [[:upper:]]*
```

- List any files beginning with a number.
```
ls [[:digit:]]*
```

- Qué es GNOME?  
Es el entorno de escritorio para linux. El entorno de escritorio es un conjunto de software para ofrecer al usuario de una computadora una interacción amigable y cómoda.

- Make a directory called meow in desktop
```
$ cd ~/Desktop
$ mkdir meow
```

- What is the command for copy?
```
$ cp item1 item2
```

- What is the command -i and the command -r?
-i is interactive. Before overwriting an existing file, prompt the user for confirmation. If this option is not specified, cp will silently overwrite files.
-r means recursive Recursively copy directories and their contents. This option (or the -a option) is required when copying directories.

- The command mv (move) is used to move files and rename them.  
TRUE

- Unix-like operating systems such as Linux do not have an undelete command. Once you delete something with rm, it’s gone  
TRUE.

- Remove using the interactive commnand the game file.
rm -i game

- What do you enter to delete a directory?
rm -r [directory]

- How do you override the --interactive option and ignore nonexistent
  files? 
with the command -f (force)

- How do you create a symbolic link and a hard link?
```
ln [file link]  // to create hard link
ln -s [item link] // to create symbolic links where item is a file
o directory
```

- By default, every file has a single hard link that gives the file its name. When we create a hard link, we create an additional directory entry for a file.  
TRUE

- A hard link can reference a file outside its own filesystem.
FALSE

- A hard link can reference to files and directories.
FALSE. A hard link cannot reference a directory.

- When a hard link is deleted, the link is removed, but the contents of the file itself continue to exist 
TRUE

- A Symbolic links work by creating a special type of file that contains a text pointer to the referenced file or directory. 
TRUE

- When you delete a symbolic link, only the link is deleted, not the file itself. If the file is deleted before the symbolic link, the link will continue to exist but will point to nothing. (the link is broken) ls will list them as red.
TRUE

- Create a directory in the desktop call playground. And inside it
  create tow directores called dir1 and dir2
```
$ cd ~/Desktop
$ mkdir playground
$ mkdir playground/dir1 playground/dir2
```

- Copy the passwd file fomr the /etc directory
```
$ cp /etc/passwd . 
```

- In the playground directory create a file called fun and create a
  hard link
$ touch fun
$ ln fun fun-hard

- Create a symbolic link in the file fun
$ ln -s fun fun-sym


# CHAPTER 5

- What does the type command does?
is a shell builtin that displays the kind of command the shell will execute, given a particular command name.
```
type [command]
```

- Find where is located cd.
```
which cd
```

- Get the documentation of cd.
```
help cd
```

- Display the manual page of ls
```
man ls
```

- Display a Very Brief Description of mkdir
```
whatis mkdir
```

- Get info about pwd
```
info pwd
```

- First change directory to /usr, then list the directory, and finally return to the original directory in one command line.
```
cd ~/usr; ls; -cd;
```

- Alias foo to:  cd ~/usr; ls; -cd; and then unalias it.
```
$ alias foo='cd /usr; ls; cd -'
$ unalias foo
```

# CHAPTER 6

- What is I/O redirection?
I/O redirection allows us to change where output goes and where input comes from. Normally, output goes to the screen and input comes from the keyboard, but with I/O redirection we can change that.

- What is the redirection operator?
>

- Print the result of ls bin in the file ls-output.txt.
```
$ ls -l /usr/bin/ > ~/Desktop/ls-output.txt
```

- Now print a directory that doesn't exist like ls -l /bin/usr > ls-output.txt. What happend to the ls-output.txt? because It returns an error in the shell and the file has zero length. when we redirect output with the > redirection operator, the destination file is always rewritten from the beginning

- Write the history command in the file last500.txt and then delete what
  is inside. 
$ history > last500.txt
$ > last500.txt


- What is the operator to append an output instead of overwritting? 
>>

- Long list the /bin/usr error directory to error.txt
$ ls -l /bin/usr 2> ls-error.txt

- What does the cat command does?
The cat command reads one or more files and copies them to standard output.

- Create the files: file1 file2 file3 with the content line1 line2 and
  line3.

concatenate the three files into a single one.
```
$ touch file1 file2 file3
$ echo line1 > file1
$ echo line2 > file2
$ echo line3 > file3
cat file* > allFiles
```

- Using the command cat, create the file dog.txt and write "luna"
  inside it.
```
$ cat > dog.txt
luna
CTRL-D // to tell cat it has reached the end of file.
```

- What does the pipelines does?
Using the pipe operator | (vertical bar), the standard output of one command can be piped into the standard input of another.

- Redirect the list of /usr/bin to less. And then sort ite
```
$ ls -l /usr/bin | less
$ ls -l /usr/bin | sort | less
```

- What does the uniq command does?
 uniq accepts a sorted list of data from either standard input or a single filename argument and, by default, removes any duplicates from the list.

- What does the wc command does?
The wc (word count) command is used to display the number of lines, words, and bytes contained in files. 

- What does the wc -l command does?
limits its output to only report lines. 

- count and sort the number of lines in the /bin folder.
```
ls /bin | sort | wc -l
```

- What does the grep command does?
When grep encounters a “pattern” in the file, it prints out the lines containing it.

- Print all the files in /usr/bin folder that contain the world zim in it.
```
ls /usr/bin | grep zip
```

- Print the las 8 lines in the last500.txt file
```
tail -n 5 last500.txt
```

- Print the last 5 lines in /usr/bin directory.
```
ls /usr/bin | tail -n 5
```
- Print the first 10 lines and 5 line of the file last500.txt
```
head last500.txt
head -n 5 last500.txt
```

























