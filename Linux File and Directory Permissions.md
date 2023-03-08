Linux file permissions are one of the key components of its security system. In Linux, files and directories are protected by a set of permissions that determine who can access them and what actions can be performed on them. In this blog, we will discuss the basics of Linux file permissions and how to use them.

### File types in Linux:

Understanding file types is important for managing files and directories, as different file types have different permissions and behaviors.

In Linux, file types are represented by a single character in the first column of the output of the "ls -l" command. Here are some of the most common file-type symbols:

* "-" represents a regular file
    
* "d" represents a directory
    
* "l" represents a symbolic link
    

There are also other file types like device file (c), device file (b), pipe (p), and socket (s).

For example, if you run the "ls -l" command in a directory and see the following output which has different file types:

```bash
-rw-r--r-- 1 user group  1048 Feb 18 14:24 file.txt
drwxr-xr-x 2 user group  4096 Feb 19 09:32 directory
lrwxrwxrwx 1 user group    12 Feb 20 11:22 link -> /path/to/file
```

It is important to note that file types are determined by the filesystem and are not part of the file's contents.

### Linux File Ownerships and Permissions:

Every Linux system has three types of owners as described below:

* User (u)**:** A user is the one who created the file. By default, whoever creates the file becomes the owner of the file. A user can create, delete, or modify the file.
    
* Group (g)**:** A group can contain multiple users. All the users belonging to a group have the same access permission for a file.
    
* Other (o)**:** Anyone who has access to the file other than the user and group comes in the category of other. Other has neither created the file nor is a group member
    

Now let's look into the file permissions. In Linux, each file and directory is associated with three types of permissions:

* read (r)
    
* write (w)
    
* execute (x)
    

### Understanding Linux file permissions:

The read permission (r) allows users to view the contents of a file or directory, but not modify them. The write permission (w) allows users to modify the contents of a file or directory, while the execute permission (x) allows users to run executable files or access the contents of a directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676978482415/c75a1ddc-6f0b-4121-8b56-82a549f502da.png align="center")

The permission categories are represented by three groups with three characters each as represented in the above image. The first group represents the permissions of the owner (u), the second group represents the permissions of the group (g), and the third group represents the permissions of all other users (o) where each group consists of the characters r, w, x or a hyphen (-) to indicate whether the corresponding permission is allowed or not.

*Representation of file permissions:* File permissions are generally assigned in either symbolic or octal values. The octal values for Read -&gt; 4, Write -&gt; 2, Execute -&gt; 1. So, if a user has all permissions then the octal value will be (4 + 2 + 1) 7. Symbolically, permissions will be 'rwx' (order should be the same always in permissions). Refer below image and examples for more such combinations.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676977088338/d8de9e42-2871-4da3-a7ed-d6dd5c8d9899.png align="center")

### Using Linux File Permissions:

To view the permissions of a file or directory in Linux, you can use the "ls -l" command. This will display a list of all files and directories in the current directory, along with their permissions, owner, group, and other information.

To modify the permissions of a file or directory, you can use the "chmod" command. The syntax for this command is

```bash
chmod <permissions> <filename>
```

For example:

```bash
chmod u+rwx <filename>
#To give the user of a file read, write, and execute permissions
chmod 741 <filename>
#Here 3 digits represent user, group, others permissions of r,w,x in octal combination. above used 741 represent 7(4+2+1) -> r,w,x to user, 4(4+0+0) -> r to group and 1(0+0+1) -> x to others. 
chmod o-r <filename>
#To remove the read permission from all other users.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676960196293/672cfb93-5534-48ca-ab6b-5c5903201b20.png align="center")

NOTE: Take a look at umask command and see what it does.

This is all about file permissions, for now, see you in the next one :)
