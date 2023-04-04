Handling files is one of the essential tasks you perform on a Linux system. In Linux, everything is treated as a file, and there are many commands available to handle files effectively.

We have seen basic commands of Linux, and how to access files or directories by changing permissions in the previous blog. So in this blog, we will explore some of the *most commonly used commands* to manage files in Linux.

### 1\. Creating Files:

The first step to handling files is creating them. There are different ways to create files in Linux. The most commonly used command is the **touch** command. The touch command is used to create a new file and when a file with the same name exists, it updates the modification timestamp of that file.

The syntax for creating a new file using the touch command is as follows:

```bash
touch filename
#To create a file named example.txt, you would run the following command:
meena@LAPTOP-2AHVQEVL:~/home$ touch example.txt
#Observe below outputs to see how touch command modifies timestamp on existing file
meena@LAPTOP-2AHVQEVL:~/home$ ls -l example1.txt
-rw-r--r-- 1 meena meena 7 Feb 27 13:12 example1.txt
meena@LAPTOP-2AHVQEVL:~/home$ touch example1.txt
meena@LAPTOP-2AHVQEVL:~/home$ ls -l example1.txt
-rw-r--r-- 1 meena meena 7 Mar  1 23:44 example1.txt
```

### 2\. Viewing Files:

Once you have created a file, the next step would be to view its contents. The command for viewing files is the **cat** command. It displays the contents of a file on the screen.

The syntax for using the cat command is as follows:

```bash
cat filename 
#To view the contents of the file named sample.txt, you would run the following command: 
meena@LAPTOP-2AHVQEVL:~/home$ touch sample.txt 
meena@LAPTOP-2AHVQEVL:~/home$ echo 'hello!' > sample.txt 
meena@LAPTOP-2AHVQEVL:~/home$ cat sample.txt 
hello!
```

### 3\. Copying Files:

The command for copying files from one location to another is the **cp** command.

The syntax for using the cp command is as follows:

```bash
cp <source_file> <destination_file>
#To copy a file named example.txt to a new file named example1.txt, you would run the following commands:
meena@LAPTOP-2AHVQEVL:~/home$ touch example.txt example1.txt
meena@LAPTOP-2AHVQEVL:~/home$ echo 'monday' > example.txt
meena@LAPTOP-2AHVQEVL:~/home$ cat example.txt
monday
meena@LAPTOP-2AHVQEVL:~/home$ cat example1.txt
meena@LAPTOP-2AHVQEVL:~/home$ cp example.txt example1.txt
meena@LAPTOP-2AHVQEVL:~/home$ cat example1.txt
monday
meena@LAPTOP-2AHVQEVL:~/home$ cat example.txt
monday
```

### 4\. Moving or Renaming Files:

The command for moving files from one location to another is the **mv** command.

This command is also used to rename file names.

The syntax for using the mv command is as follows:

```bash
mv <source_file> <destination_file>
#To move a file named bye.err from home to a folder named rough, you would run the following commands:
meena@LAPTOP-2AHVQEVL:~/home$ pwd
/home/meena/home
meena@LAPTOP-2AHVQEVL:~/home$ ls
bye.err  example.txt  example1.txt  hi.txt  rough  rough.sh
meena@LAPTOP-2AHVQEVL:~/home$ mv bye.err /home/meena/home/rough
meena@LAPTOP-2AHVQEVL:~/home$ ls
example.txt  example1.txt  hi.txt  rough  rough.sh
meena@LAPTOP-2AHVQEVL:~/home$ cd rough
meena@LAPTOP-2AHVQEVL:~/home/rough$ ls
bye.err
```

Renaming files with the mv command:

```bash
meena@LAPTOP-2AHVQEVL:~/home$ touch ruffnotes.txt
#To rename ruffnotes to roughnotes, we can use mv with <old_name> followed by <new_name> as shown below
meena@LAPTOP-2AHVQEVL:~/home$ mv ruffnotes.txt roughnotes.txt
```

### 5\. Deleting Files:

The command for deleting files is the **rm** command.

The syntax for using the rm command is as follows:

```bash
rm filename
#To delete a file named example.txt, you would run the following command:
meena@LAPTOP-2AHVQEVL:~/home$ ls
example.txt  example1.txt  hi.txt  rough  rough.sh
meena@LAPTOP-2AHVQEVL:~/home$ rm example.txt
meena@LAPTOP-2AHVQEVL:~/home$ ls
example1.txt  hi.txt  rough  rough.sh
```

NOTE: To delete directories that include subdirectories, use **rm -r**. This command recursively deletes directories and their subdirectories and any files these subdirectories may contain.

### 6\. Comparing Files:

We can compare files in Linux by using three variations of the diff command as shown below.

* The command for comparing files is the **diff** command.
    

The syntax for using the mv command is as follows:

```bash
meena@LAPTOP-2AHVQEVL:~/home$ diff hi.txt hello.txt
1c1
< hi
---
> hello
4c4
< great
---
> good
6c6
<
---
>
```

In the above output of the diff command:

1c1 - the first digit indicates the line number in file1, the last digit indicates the line number in file2 and the middle character can represent either a: add, c: change, d: delete.

The "&lt;" symbol indicates that the line is present in file 1, but not in file 2, while the "&gt;" symbol indicates that the line is present in file 2, but not in file 1.

* We can also compare files side by side by using **sdiff** command. This command shows the difference between the files as shown below:
    

```bash
meena@LAPTOP-2AHVQEVL:~/home$ sdiff hi.txt hello.txt
hi                                                            | hello
have                                                            have
a                                                               a
great                                                         | good
day                                                             day
                                                              |
```

* Another way to compare files is using the **vimdiff** command which opens files in two windows side by side as shown below:
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1677695406231/c1054cba-42c0-4122-8dfe-81390026409f.png align="center")

### 7\. Searching in Files:

Searching for specific text or patterns in files is a common task in Linux. Here, we will discuss some of the most common methods for searching in files.

* Using the **grep** command-
    

The grep command is a built-in utility in Linux that searches for patterns in one or more files.

To use the grep command, simply type the following into the terminal:

```bash
meena@LAPTOP-2AHVQEVL:~/home$ grep d example1.txt
monday
```

NOTE: We can use several other options and even search with wildcards on the grep command. Check out what wildcards are!

*Extra:*

If you want to know the type of any file use the **file** command followed by the filename.

```bash
meena@LAPTOP-2AHVQEVL:~$ file rough
rough: ASCII text
```

## Input, Output, and Redirection:

Input/output redirection is the process of changing the default input or output of a command or program. By default, most commands and programs in Linux read input from the keyboard (standard input), write output (standard output) and error (standard error) to the screen. We can use numeric file descriptors for each one of them to make it easy for our computer to reference as shown below:

* standard input - stdin - 0
    
* standard output - stdout - 1
    
* standard error - stderr - 2
    

Now, you can use redirection to change the source or destination of input or output.

1. **\&gt; :** redirects standard output to a file.
    
    For example, to redirect the output of the "ls" command to a file called "output.txt", you would type:
    
    ```bash
    ls > output.txt
    ```
    
    NOTE: *The stdin usually overwrites the contents of a file but if we want to append some text at the end of the file we can also use the* ***\&gt;&gt;*** *symbol.*
    
2. **&lt;** : redirects standard input from a file.
    
    For example, to read input from a file called "input.txt" instead of the keyboard, you would type:
    
    ```bash
    command < input.txt
    ```
    
3. **2&gt;** : In addition to standard input and output, Linux also has a standard error stream (stderr). By default, error messages are printed on the screen, but you can also redirect them to a file or another command using the "2&gt;" operator. For example, to redirect error messages to a file called "error.txt", you would type:
    
    ```bash
    command 2> error.txt
    ```
    
    This will redirect all error messages from the "command" to the "error.txt" file.
    
4. **|** (pipe): redirects the output of one command to the input of another command. For example, to list all files in the current directory and then count the number of lines in the output, you would type:
    

```bash
meena@LAPTOP-2AHVQEVL:~/home$ ls
bye.err  example1.txt  hello.txt  hi.txt  rough  rough.sh  rough.txt  roughnotes.txt  today.sh
meena@LAPTOP-2AHVQEVL:~/home$ ls | wc -l
9
```

Here, the output of the "ls" command is piped (redirected) to the "wc -l" command, which counts the number of lines in the output.

### Conclusion:

In conclusion, handling files in Linux is a crucial skill that every Linux user should have. There are many commands available to handle files effectively, and the commands mentioned in this blog are just a few of the most commonly used commands. By mastering these commands, you will be able to handle files efficiently and effectively in Linux.

That's it for now, see you soon in the next one :)