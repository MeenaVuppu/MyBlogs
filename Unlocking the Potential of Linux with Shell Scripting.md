Hello All,

In this blog, let's look into the concept of how we do scripting in the Linux terminal. Linux provides powerful scripting capabilities through the use of shell scripts. **Shell** is a program that provides the interface between the user and an operating system.

There are different shells like the C shell, the Bourne shell, the Korn shell, the Z shell and the GNU Bourne-Again Shell.

A shell script is a text file that contains a series of commands (like a program) that can be executed in a shell. The shell script can be executed by the user or the system automatically.

The most commonly used shell in Linux is the **Bourne Again SHell (bash)**, which includes features from Korn and Bourne shell. It is the default shell in most Linux distributions so we will discuss it in this blog. Bash scripts are easy to write and are used to automate repetitive tasks or perform complex operations. This is where text editors like nano, vim, and emacs come into action.

We can use any of the text editors for shell scripting which we are comfortable working with, but vim and emacs are considered to be the most powerful ones. So, let us take a look at how we use these editors.

### **Using Nano:**

Nano is a user-friendly and straightforward text editor that is perfect for beginners. Here are some essential commands to get you started with nano:

* To open a file with nano: `nano filename`
    
* To save a file: `Ctrl + O`
    
* To exit nano: `Ctrl + X`
    
* To search for a string: `Ctrl + W`
    
* To cut a line: `Ctrl + K`
    
* To paste a line: `Ctrl + U`
    
* To undo the last action: `Ctrl + _`
    

There are several other shortcuts using which you can work with Nano.

### **Using Vim:**

Vim is a powerful text editor that offers more advanced features than nano. It is the modified version of vi. It has a steep learning curve, but once you master it, you'll find it to be a very efficient tool.

You need to know about the 3 modes of operations in vim:

* **Command mode:** This is the default mode when you open Vim. You can enter this mode by pressing the Esc key.
    
* **Insert mode:** To enter insert mode, press the 'i' key while in command mode.
    
* **Line mode:** To enter this mode, press the colon (:) while in command mode.
    

Here are some essential commands to get you started with Vim. The ones with : before represent they are entered in line mode, rest in command mode:

* To open a file with Vim: `vim filename`
    
* To enter insert mode: `i`
    
* To exit insert mode: `Esc`
    
* To save a file: `:w`
    
* To save and quit Vim: `:wq`
    
* To quit Vim without saving: `:q!`
    
* To search for a string: `/string`
    
* To cut a line: `dd`
    
* To paste a line: `p`
    
* To undo the last action: `u`
    
* To move the cursor to a specific line number: `:line_number`
    
* To set line numbers: `:set nu`
    
* To unset line numbers: `:set nonu`
    

There are several other shortcuts using which you can work with Vim.

### Using Emacs:

Emacs is a versatile text editor that is highly customizable and offers a vast range of features. It has a steeper learning curve than nano and Vim. Unlike the vi editor, the Emacs editor does not use an insert mode, and it is by default in editing mode. Here are some essential commands to get you started with Emacs:

* To open a file with Emacs: `emacs filename`
    
* To save a file: `Ctrl + X, Ctrl + S`
    
* To save and quit Emacs: `Ctrl + X, Ctrl + C`
    
* To cut a line: `Ctrl + K`
    
* To paste a line: `Ctrl + Y`
    
* To undo the last action: `Ctrl + X, U`
    
* To move the cursor to a specific line number: `Alt + G, line_number`
    

There are several other shortcuts using which you can work with Emacs.

\*You can find many cheat sheets or reference cards online for commands to use in respective editors.

**Finally! Let's move on to creating a simple shell script.**

For this, open a text editor of your choice (I'll use vim for now) and type the commands that you want to execute. Save the file with a ".sh" extension as this represents shell script.

For example, to create a shell script that displays the current date and time, open a text editor and type the following commands:

```bash
meena@LAPTOP-2AHVQEVL:~/home$ vim today.sh
#The above command opens script in command mode, press i and go to insert mode and enter the below script inside the editor. The first line tells the operating system which shell to use to run the script. In this case, we are using Bash. From the second line, you can write the commands you want to execute.
-----------------------------------------------------------------------------
#!/bin/bash
echo "Current date and time:"
date
```

To execute the above shell script, today.sh, navigate to the directory where the file is saved. For vim, we need to use the ./filename.sh command as shown below:

```bash
meena@LAPTOP-2AHVQEVL:~/home$ ./today.sh
-bash: ./today.sh: Permission denied
#Make the file executable by adding the execute permission with the following command:
meena@LAPTOP-2AHVQEVL:~/home$ chmod +x today.sh
meena@LAPTOP-2AHVQEVL:~/home$ ./today.sh
Current date and time:
Mon Feb 27 13:33:48 IST 2023
```

With practice and experience, you can become proficient in shell scripting and streamline your workflow in Linux. With the knowledge of the Linux file system and scripting, we can increase our productivity and take full advantage of the power of Linux.

That's it for now, see you in the next one :)