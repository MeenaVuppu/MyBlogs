Hello,

I've been learning Linux commands that can be handy for day-to-day actions in the terminal.

Many useful Linux commands can help you accomplish various tasks on your system. Here are some of the most commonly used commands that can be helpful:

1. whoami: To see the name of the person who is using this terminal currently.
    
2. su &lt;username&gt;: To change the user to either root or another person.
    
    * su root gives us access to do everything after entering the root password.
        
3. ls: This command is used to list the files and directories in a directory.
    
    * ls -l is also very useful as it displays files along with file permissions
        
    * ls -a lists all files including hidden files.
        
    * ls -ld will display the information about the directory in long format, including the permissions, owner, group, size, and modification time, and show only the directory but not its contents.
        
    
    NOTE: checkout the tree command to view directories and files in it in tree structure.
    
4. cd: This command is used to change the current working directory.
    
    \- There are certain shortcuts to navigate between directories as below:
    
    * cd / takes us to the root directory
        
    * cd ~ takes us to the home directory of the current user
        
    * cd . or cd./ means current directory
        
    * cd .. takes us to the parent/previous directory
        
    * cd - is used to switch between directories
        
5. mkdir: This command is used to create a new directory.
    
6. touch: This command is used to create a new empty file or update the timestamp on an existing file.
    
7. cp: This command is used to copy files and directories.
    
    * cp &lt;source\_file&gt; &lt;destination\_file&gt;: copies source\_file to destination\_file if already exists, else creates the destination file and then copies the source\_file.
        
8. mv: This command is used to move or rename files and directories.
    
9. rm: This command is used to delete files and directories.
    
    * rm -rf: This command is used to remove directories recursively. This means it deletes the parent directory including all the subdirectories and files.
        
    
    NOTE: Be cautious while using this command as a directory or file will be deleted permanently. There will be no undoing here!
    
10. cat: This command is used to display the contents of a file.
    

That's it! These are the basic commands for today. I hope this will be useful for a quick reference!