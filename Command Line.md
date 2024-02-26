* **pwd (Print working directory)**
	* this command means “print working directory” and it just shows you which directory you are in, note the path stems from the root directory.
* Absolute Path of files
	*  This is the path from the root directory.
	*  Example : /home/pete/docs
* Relative Path of files
	* This is the path from where you are currently in filesystem.
	* Example : cd pictures
* ls (List Directories)
	* The ls command will list directories and files in the current directory by default, however you can specify which path you want to list the directories of.
	* Example : 
		* ls
		* ls /home/pete
	* Flags:
		* ls -a : Filenames that start with . are hidden, you can view them however with the ls command and pass the -a flag to it (a for all).
		* ls -l : this shows a detailed list of files in a long format.
			* starting from the left: file permissions, number of links, owner name, owner group, file size, timestamp of last modification, and file/directory name.
		* ls  -la : list of all files in long format
		* ls -r : reverse order while sorting
		* ls -R : recursively list directory contents
		* ls -t : sort by modification time, newest first
* 