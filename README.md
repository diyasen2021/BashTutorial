# Introduction to Bash for Bioinformatics

Welcome to our beginner's Bash tutorial! Bash (Bourne Again Shell) is a powerful command-line shell that allows you to interact directly with your computer's operating system. With Bash, you can navigate your file system, manipulate files, automate tasks, and much more. Whether you're a developer, data scientist, or just someone curious about command-line skills, understanding Bash is an essential skill that can make your computer work for you in powerful ways.

### Getting started with Bash

**On MacOSX:**

Open **Finder**. <br>
Go to **Applications** > **Utilities**. <br> 
Double-click on **Terminal**.<br>

Alternatively, use **Spotlight Search**. <br>
Press Command + Space to open **Spotlight**. <br>
Type **"Terminal"** and press Enter.<br>


**Setting Up Your Bash Environment (Optional)** <br>
For many users, macOS comes pre-configured with a .bash_profile and .bashrc file. These files allow you to set environment variables, aliases, and custom configurations.<br>
To check if these files exist:<br>
```
ls -a ~
```

### Basic Bash Commands for File System Navigation and File Management
1. Navigating the File System
Display the current directory
```
pwd
```
Lists files and directories in the current directory
```
ls
```
Add -a to see hidden files (those starting with a dot, like .bash_profile).<br>
Add -l for a more detailed list, including permissions and file sizes.<br>

Change the current directory <br>
```
cd Documents
```
To go back to the previous directory, use cd - <br>
To return to your home directory, use cd ~ <br>

2. Creating and Managing Directories <br>

Create a new director 
```
mkdir myproject
```

3. Creating and Viewing Files <br>
Creates a new empty file
```
touch notes.txt
```
Display the contents of a file
```
cat notes.txt
```
Display first 10 lines of file 
```
head -n 10 notes.txt
```
Display last 10 lines of file
```
tail -n 10 notes.txt
```

4. Editing Files
While Bash itself doesn’t edit files directly, you can use text editors like nano:

Nano a simple text editor
```
nano notes.txt
```
Vim  a more advanced text editor
```
vim notes.txt
```
5. Moving, Renaming, and Copying Files
Moves or rename a file.
```
mv notes.txt notes2.txt
```
Copy a file.
```
cp notes2.txt notes.txt
```

6. Deleting Files and Directories

Delete a file
```
rm notes.txt
```
Delete a directory
```
rm -r my_project
```
7. Reviewing Your Command History
```
history
```
