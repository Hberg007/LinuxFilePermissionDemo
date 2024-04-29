<h1>Update File Permissions in Linux<h1>


<h2>Description</h2>
Demonstration of checking and updating permissions in Linux to reflect correct level of authorization for users.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 


<h2>Environments Used </h2>

- <b>Windows</b> 

<h2>Exercise Walk-Through:</h2>

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.
 <br />
 <br />
  <p align="center">  <img width="600" alt="image" src="https://github.com/Hberg007/LinuxFilePermissionDemo/assets/168477827/82da4faf-04bc-4076-b8ca-b8015d4492ce">
<br />
<br />

    The first line of the screenshot displays the command I entered, and the other lines display the output. 

    The code lists all contents of the projects directory. 

    I used the ls command with the -la option to display a detailed list of the file contents that also returned hidden files. 

    The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt and five other project files. 

    The 10-character string in the first column represents the permissions set on each file or directory.
<br/>
<br />
<h2> Strings Permissions Explained:</h2>
<br />
<br />
    The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. 

    The characters and what they represent are as follows:

    [1st character]: This character is either a (d) or hyphen (-) and indicates the file type. If it’s a (d), it’s a directory. If it’s a hyphen (-), it’s a regular file.

    [2nd-4th characters]: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it     
    that this permission is not granted to the user.

    [5th-7th characters]: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it 
    indicates that this permission is not granted for the group.

    [8th-10th characters]: These characters indicate the read (r), write (w), and execute (x) permissions for the other. When one of these characters is a hyphen (-) instead, it 
    indicates that this permission is not granted for other.
<br />

   For example, the file permissions for project_t.txt are -rw-rw-r--. 
   
   Since the first character is a hyphen (-), this indicates that project_t.txt is a file, not a directory.
   
   The second, fifth and eight characters are all r, which indicates that the user, group, and other all have read permissions. 
   
   The third and sixth characters are w, which indicates that only the user and the group have write permissions. 
   
   No one has execute permissions for project_t.txt.
<br />
<br />
<h2> Change File Permissions:</h2>
<br />
<br />

The organization determined that "other" users shouldn’t have write access to any of their files. 
<br />
<br />
To comply with this, I referred to the file permissions that I previously returned. 
<br />
<br />
I determined project_k.txt must have write access removed for other.
<br />
<br />
The following code demonstrates how I used Linux commands to do this:
<br />
<br />
 <p align="center"> <img width="700" alt="image" src="https://github.com/Hberg007/LinuxFilePermissionDemo/assets/168477827/e2100271-1032-484a-8711-b689f2647562">
<br />
<br />

    The first two lines of the screenshot show the commands I entered, and the other lines show the output of the second command entered. 

    The chmod command changes permissions on files and directories. 
 
    The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. 

    In this example, I removed write permissions from other for the project_k.txt file. 

    After this, I used the ls -la command to review the updates I made.
<br />
<br />
<h2> Change File Permissions on Hidden Files:</h2>

<br />
<br />
The research team at my organization recently archived project_x.txt. 
<br />
<br />
They do not want anyone to have write access to this project, but the user and group should have read access.
<br />
<br />
The following code demonstrates how I used Linux commands to change the permissions:
<br />
<br />

<p align="center"> <img width="700" alt="image" src="https://github.com/Hberg007/LinuxFilePermissionDemo/assets/168477827/fd0b4e43-5f38-4d22-9c0a-cdea45c64bf4">
<br />
<br />
    
    The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. 
  
    I know .project_x.txt is a hidden file because it starts with a period (.) 
    
    In this example, I removed write permissions from the user with u-w. 
    
    Then, I removed write permissions from the group with g-w, and finally added read permissions to the group with g+r.
<br />
<br />
<h2> Change Directory Permissions:</h2>
<br />
<br />

My organization only wants the researcher2 user to have access to the drafts directory and its contents. 
<br />
<br />
This means that no one other than researcher2 should execute permissions.
<br />
<br />
The following code demonstrates how I used Linux commands to change permissions:
<br />
<br />

<p align="center"> <img width="700" alt="image" src="https://github.com/Hberg007/LinuxFilePermissionDemo/assets/168477827/90ea2000-ebf5-473d-aaa8-09309bc10991">
<br />
<br />

    The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. 
    
    I previously determined that the group had execute permissions, so I used the chmod command to remove them. 
    
    The researcher2 user already had execute permissions, so they did not need to be added.
<br />
<br />
<h2> Summary:
<br />
<br />
I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. 

The first step in this was using ls -la to check the permissions for the directory. 

This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on the files and directories.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
