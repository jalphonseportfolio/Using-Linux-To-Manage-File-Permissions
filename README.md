<h1>Using-Linux-To-Manage-File-Permissions</h1>

<h2>Description</h2>
The research team at an organization needs to update the file permissions for certain files and directories within the project's directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks:
<br />

<h2>Check file and directory details</h2>
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Screenshot 2024-12-29](https://github.com/jalphonseportfolio/Using-Linux-To-Manage-File-Permissions/blob/main/Images/pic01.png)

The screenshot's initial line exhibits the command I inputted, while subsequent lines showcase the output line. The provided code enumerates all items within the project's directory. I employed the ls command with the -la parameter to present an elaborate inventory of file contents, encompassing concealed files. The output of my command reveals the presence of a directory named "drafts," an obscured file titled ".project_x.txt," and an additional five project files. The sequence of ten characters in the opening column signifies the permissions designated to each file or directory.

<h2> Explain the Permissions String</h2>
Breaking down the 10-character string allows for the identification of authorized users and their specific access privileges. The characters and their corresponding meanings are as follows:

- <b>1st character: This character represents the file type and is either a d (for directory) or a hyphen (-) for a regular file.</b>

- <b>2nd-4th characters: These characters signify the user's read (r), write (w), and execute (x) permissions. The presence of a hyphen (-) indicates the absence of that particular permission for the user.</b>

- <b>5th-7th characters: These characters denote the group's read (r), write (w), and execute (x) permissions. A hyphen (-) signifies the lack of that specific permission within the group.</b>

- <b>8th-10th characters: These characters indicate other users' read (r), write (w), and execute (x) permissions. In this context, "other" refers to all users except the owner and the group. The presence of a hyphen (-) signifies the exclusion of that permission for other users.</b>

<h2>Change file permissions</h2>
The organization concluded that other users should not possess write access to any of their files. To adhere to this requirement, I consulted the file permissions that I had previously retrieved. After assessing the situation, I recognized that it was necessary to revoke write access for other users on the "project_k.txt" file.

![Screenshot 2024-12-29](https://github.com/jalphonseportfolio/Using-Linux-To-Manage-File-Permissions/blob/main/Images/pic02.png)


The initial two lines in the screenshot showcase the commands I inputted, while the subsequent lines exhibit the output of the second command. The chmod command is responsible for modifying permissions on files and directories. The first parameter defines the permissions to be altered, and the second parameter designates the file or directory. In this instance, I eliminated write permissions for "other" on the "project_k.txt" file. Following this adjustment, I employed "ls -la" to assess the modifications I implemented.


<h2> Change file permissions on a hidden file </h2>
The organization's research team has recently stored away the file project_x.txt. They intend to restrict write access to this project while maintaining read access for both the user and the group.

Below is an example of the Linux commands I employed to modify the permissions:

![Screenshot 2023-08-20 6 32 02 PM](https://github.com/jalphonseportfolio/Using-Linux-To-Manage-File-Permissions/blob/main/Images/pic03.png)

The initial two lines in the screenshot exhibit the commands I inputted, while the subsequent lines exhibit the output stemming from the second command. I am aware that the file .project_x.txt is concealed, as it initiates with a period (.). In this illustration, I eliminated the user and group's ability to write by utilizing u-w. Subsequently, I revoked the group's write permission using g-w and appended read permission using g+r.

<h2>Change directory permissions</h2>
In the organization, exclusive access to the drafts directory and its contents is reserved solely for the user named researcher2. This implies that no individual apart from researcher2 should possess execution privileges.

The subsequent code illustrates how I employed Linux commands to alter the permissions:

![Screenshot 2023-08-20 6 34 31 PM](https://github.com/jalphonseportfolio/Using-Linux-To-Manage-File-Permissions/blob/main/Images/pic04.png)


The initial two lines within the screenshot exhibit the commands I inputted, while the subsequent lines present the output stemming from the second command. I had previously identified that the group possessed execute permissions, prompting me to utilize the chmod command to revoke them. Since the researcher2 user was already endowed with execute permissions, no further action was necessary in that regard.

<h2> Conclusion</h2> 
In this project, I utilized Linux commands to manage file permissions within the projects directory to enhance system security. Initially, I checked the existing permissions using "ls -la" to identify the authorization levels for files and directories. Then, I explained the permissions string, detailing user, group, and other access rights. Following this, I changed permissions as required, such as revoking write access for other users on specific files and modifying permissions on hidden files. Additionally, I adjusted directory permissions to restrict execution privileges to designated users. Overall, by employing commands like chmod and ls, I successfully aligned file and directory permissions with the organization's security requirements, ensuring appropriate access levels.
</p>
