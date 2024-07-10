# Manage-Authorization

## Project description
The research team at my organization needs to update the file permissions for certain files and
directories within the projects directory. The permissions don't currently reflect the level of
authorization that should be given to the respective users. Checking and updating these permissions will help keep
their system secure. To complete this task, I have performed the following tasks:

## Check file and directory details
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Screenshot (101)_proc](https://github.com/franckley/Manage-Authorization/assets/134894186/cfaf8b3e-615f-40a4-b598-3e6ff83e9e37)
The third line of the screenshot displays a command I entered, and the other lines that follow, display its
output. The code lists all contents of the projects directory. I used the ls command with the
-la option to display a detailed listing of the file contents that also returned hidden files. The
output of my command indicates that there is one directory named drafts, one hidden file
named .project_x.txt, and five other project files. The 10-character string in the first
column represents the permissions set on each file or directory.

## Describe the permissions string
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:

* **1st character:** This character is either a `d` or hyphen (`-`) and indicates the file type. If it’s a `d`, it’s a directory. If it’s a hyphen (`-`), it’s a regular file.
* **2nd-4th characters:** These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the user. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted to the user.
* **5th-7th characters:** These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the group. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted for the group.
* **8th-10th characters:** These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for others. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (`-`) instead, that indicates that this permission is not granted for others.

For example, the file permissions for `project_t.txt` are `-rw-rw-r--`. Since the first character is a hyphen (`-`), this indicates that `project_t.txt` is a file, not a directory. The second, fifth, and eighth characters are all `r`, which indicates that user, group, and others all have read permissions. The third and sixth characters are `w`, which indicates that only the user and group have write permissions. No one has execute permissions for `project_t.txt`.


## Change file permissions
The organization determined that other shouldn't have write access to any of their files. To
comply with this, I referred to the file permissions that I previously returned. I determined
`project_k.txt` must have the write access removed for other.

The following code demonstrates how I used Linux commands to do this:

![Screenshot (101)_proc](https://github.com/franckley/Manage-Authorization/assets/134894186/a3d9d90e-4c8f-4c92-9751-4ef896144eed)
