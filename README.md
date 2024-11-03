# Introduction to Unix commands for Bioinformatics

Welcome to our beginner's Bash tutorial! Bash (Bourne Again Shell) is a powerful command-line shell that allows you to interact directly with your computer's operating system. With Bash, you can navigate your file system, manipulate files, automate tasks, and much more. Whether you're a developer, data scientist, or just someone curious about command-line skills, understanding Bash is an essential skill that can make your computer work for you in powerful ways.

### Contents

1. Getting started with Bash
2. Basic bash commands for file system navigation
3. Working with Data in Bash


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

### Working with Data in Bash

After learning basic file operations, let’s move on to some data manipulation commands. These are especially useful for bioinformaticians handling large datasets. 

1. Extracting Specific Columns

```
cut -d 'delimiter' -f fields filename
```
-d specifies the delimiter (e.g., a comma ,, tab \t, or space).
-f specifies the field(s) you want to extract.

Example: Suppose you have a file called genes.tsv with tab-separated columns: gene name, expression level, and chromosome. Here’s an example:
```
GeneA    12.3    chr1
GeneB    7.8     chr2
GeneC    19.4    chr1
GeneD    3.5     chr3
```
To extract only the gene names (first column):

```
cut -f 1 genes.tsv 
```

To extract gene names and expression levels (first and second columns):
```
cut -d $"\t" -f 1,2 genes.tsv
```
2. Sorting by columns
The sort command allows you to arrange data in ascending or descending order.

Example 1: Sorting Genes by Expression Level Continuing with the genes.tsv file above, let’s sort it by the expression level (second column) in descending order:

```
sort -k2,2nr genes.tsv
```
-k column: Sort by a specific column.
-n: Sort numerically (for numbers).
-r: Reverse the sort order (descending).

Example 2: Sorting by Chromosome If you want to sort genes by their chromosome (third column), alphabetically:
```
sort -k3 genes.tsv
```
3. Finding Unique Lines
The uniq command is useful for identifying unique entries in a sorted list.

Example 1: Suppose you have a sorted file chromosomes.txt that lists chromosomes associated with genes and you want to count unique chromosomes 
   
```
chr1
chr1
chr2
chr3
chr3
chr3
```
```
sort chromosomes.txt | uniq -c
```
4. Combining cut, sort, and uniq in Bioinformatics
   
Example 1: Sort by gene name and expression level (descending)
```
cut -f1,2 gene_data.tsv | sort -k1,1 -k2,2nr

```
Example 2: Find unique genes based on highest expression level

```
cut -f1,2 gene_data.tsv | sort -k1,1 -k2,2nr | uniq -f1
```
