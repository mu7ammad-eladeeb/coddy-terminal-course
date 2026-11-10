# Introduction

## What Is The Terminal

The **terminal** is a powerful text-based interface that lets you communicate directly with your computer's operating system.

Instead of clicking buttons and icons, you type commands to navigate files, run programs, and manage your system. Learning the terminal is an essential skill for any developer.

## Your First Command

### Challenge

**Beginner**

Use the `echo` command to print `Hello World!` to the terminal.

> *Remember that the output is **case sensitive**. Make sure your text matches exactly.*

Use the `echo` command followed by your text in double quotes.

#### Hints

**Hint 1**

A command line has two parts: the program you run and the argument you pass it. Here the program is `echo` and the argument is your text.

**Hint 2**

Type `echo`, a space, then your text inside double quotes, and press Enter. The text is **case sensitive**, so it has to match the task exactly.

### Solution

    echo "Hello World!"

### Explanation

The `echo` command is used to print text to the terminal.

A command line has two parts:

- `echo` → the **program/command** you run.
- `"Hello World!"` → the **argument** you pass to the command.

The text is written inside **double quotes**, as required by the challenge.

When you run:

    echo "Hello World!"

the terminal prints:

    Hello World!

The output is **case sensitive**, so the capitalization, spaces, and exclamation mark must match the required text exactly.

## **Comments**

**Comments** are lines in your shell script that are ignored by the shell. They are used to add notes and explanations to your code for human understanding.

In the shell, a comment starts with the `#` symbol. Everything after `#` on that line is ignored:

    # This is a comment
    echo "Hello!"  # This also prints Hello!

When you run the above, only `Hello!` is printed: the comments are completely invisible to the shell.

**Common uses for comments:**

**1. Explaining what a command does:**

    # Print a welcome message
    echo "Welcome to the terminal!"

**2. Disabling a command temporarily:**

    # echo "This line is disabled"
    echo "This line will execute"

**3. The Shebang line:**

A special comment at the very top of a shell script tells the system which shell to use:

    #!/bin/bash
    echo "This script runs with Bash"

This line starts with `#!` (called a **shebang**) followed by the path to the shell. It is always the first line of a script.

**4. TODO Comments: mark future tasks:**

    # TODO: Add error handling here
    echo "Processing files..."
    
# Navigation

## **Print Working Directory**

The `pwd` command stands for **Print Working Directory**. It shows you the **full path** of the directory you are currently in.

When you open a terminal, you start in your **home directory**. The `pwd` command helps you confirm exactly where you are in the filesystem at any moment.

Simply type `pwd` and press Enter:

```bash
pwd

```

The output will look something like this:

```bash
/home

```

This is called a **path**. It shows the full location of your current directory, starting from the **root** of the filesystem (`/`).

**Understanding paths:**

- `/`: the root of the entire filesystem
- `/home`: the home directory

* `/home/documents`: the documents folder inside home

`pwd` is especially useful when you have navigated deep into different folders and need to remember where you are.

## **List Files**

The `ls` command stands for **list**. It shows you all the files and folders inside your current directory.

Simply type `ls` and press Enter:


```python
ls

```

The output will show everything in your current location:


```python
documents
readme.txt

```

**Useful options you can add to `ls`:**

`ls -l`: shows a **detailed list** with file sizes, permissions, and dates:


```python
ls -l

```

`ls -a`: shows **all files**, including hidden files that start with a `.`:


```python
ls -a

```

`ls -la`: combines both options, showing a detailed list of all files including hidden ones:


```python
ls -la

```

You can also list the contents of a **specific folder** by passing its name:


```python
ls documents

```

This shows the contents of the `documents` folder without having to navigate into it first.

## **Change Directory**

The **`cd`** command stands for **Change Directory**. It lets you navigate from one folder to another in the filesystem.

To move into a folder, type **`cd`** followed by the folder name:

```python
cd documents

```

After running this, you are now inside the **`documents`** folder. You can confirm this with **`pwd`**:

```python
/home/documents

```

**Useful ways to use `cd`:**

**`cd ..`**. Move **up one level** to the parent directory:

```python
cd ..

```

**`cd ~`**: go directly to your **home directory** from anywhere:

```python
cd ~

```

**`cd /`**: go to the **root directory**, the very top of the filesystem:

```python
cd /

```

**`cd -`**: go back to the **previous directory** you were in:

```python
cd -

```

**Tip:** You can combine **`cd`** with **`ls`** and **`pwd`** to explore your filesystem confidently: list what's there, move into it, and confirm where you are.

## **Absolute vs Relative Paths**

When navigating the filesystem, you can refer to a location in two ways: using an **absolute path** or a **relative path**.

**Absolute Path**: starts from the **root** of the filesystem (**`/`**). It always points to the same location no matter where you currently are:

```python
cd /home/documents

```

An absolute path always begins with **`/`**.

**Relative Path**: starts from your **current directory**. It depends on where you are right now:

```python
cd documents

```

If you are currently in **`/home`**, this will take you to **`/home/documents`**.

**Comparing the two:**

- If you are in **`/home`** and want to go to **`/home/documents`**:
  Absolute: **`cd /home/documents`**
  Relative: **`cd documents`**

* If you are in **`/home/documents`** and want to go up one level:
  Absolute: **`cd /home`**
  Relative: **`cd ..`**

**Special relative path symbols:**

- **`.`**. Refers to your **current directory**

* **`..`**. Refers to the **parent directory** (one level up)

```python
cd ./documents   # same as: cd documents
cd ..            # go up one level
```

## **Home And Root Directory**

Two of the most important directories in any Unix-based filesystem are the **root directory** and the **home directory**. Understanding the difference between them is important because they represent two very different locations in the filesystem.

**Root Directory (`/`)**

The root directory is the **top of the entire filesystem**. Every file and folder on your system lives somewhere inside it. It is represented by a single forward slash:

```bash
cd /

```

From the root, you can reach any location on the system using an absolute path.

**Home Directory (`~`)**

The home directory is your **personal space** in the filesystem. It is where you normally start when you open a new terminal session. It is represented by the tilde symbol:

```bash
cd ~

```

You can always return to your home directory from anywhere using **`cd ~`** or simply **`cd`** with no arguments:

```bash
cd

```

Your home directory usually contains your personal files and folders, such as documents, downloads, and configuration files.

**Comparing root and home:**

- **`/`**: the root of the whole system. It contains all files and directories on the system.
- **`~`**: your personal home directory. It usually points to **`/home/username`**.

Think of the root as the **entire building**, and your home directory as **your own room inside it**.

You can always check where **`~`** points to by running:

```bash
echo ~

```

For example, if your username is `username`, the command might output:

```bash
/home/username
```

# Files

## **Create A File**

The **`touch`** command is used to **create a new empty file** in your current directory.

Simply type **`touch`** followed by the name of the file you want to create:

```bash
touch hello.txt

```

This creates a new empty file called **`hello.txt`**. You can confirm it was created by running **`ls`**:

```bash
ls
hello.txt

```

The `ls` command lists the files and folders in your current directory, so seeing `hello.txt` in the output confirms that the file was created.

**Creating multiple files at once:**

You can create several files in a single command by listing their names separated by spaces:

```bash
touch file1.txt file2.txt file3.txt

```

This creates three empty files: `file1.txt`, `file2.txt`, and `file3.txt`.

**Creating a file inside a folder:**

You can create a file directly inside another directory without navigating into it first:

```bash
touch documents/notes.txt

```

This creates `notes.txt` inside the `documents` directory. The `documents` directory must already exist; otherwise, the command will fail.

**Note:** If the file already exists, **`touch`** will not overwrite its contents. Instead, it updates the file's **last modified timestamp**, which records when the file's contents were last changed.

## **Read A File**

The **`cat`** command is short for **concatenate**, which means to link things together. While its original purpose was to join files, its most common use today is to **read and display the contents of a file** directly in the terminal.

Simply type **`cat`** followed by the filename:

```bash
cat readme.txt

```

The contents of the file will be printed to the terminal immediately.

**Other useful ways to read files:**

**`head`**: displays only the **first 10 lines** of a file:

```bash
head readme.txt

```

**`tail`**: displays only the **last 10 lines** of a file:

```bash
tail readme.txt

```

You can control how many lines to show with the **`-n`** option:

```bash
head -n 5 readme.txt   # show first 5 lines
tail -n 3 readme.txt   # show last 3 lines

```

**`less`**: opens the file in a **scrollable viewer**. Press **`q`** to quit:

```bash
less readme.txt

```

**Note:** **`cat`** is best for short files. For long files, **`less`** is more comfortable to read.

## **Copy A File**

The **`cp`** command stands for **copy**. It lets you create a copy of a file in a new location or with a new name.

The basic format is:

```bash
cp source destination

```

For example, to copy **`readme.txt`** and name the copy **`backup.txt`**:

```bash
cp readme.txt backup.txt

```

The original file stays in place and a new copy is created.

**Copy a file into a folder:**

You can copy a file directly into another directory:

```bash
cp readme.txt documents/readme.txt

```

Or simply pass the folder as the destination and the filename will be kept:

```bash
cp readme.txt documents/

```

**Copy a folder and all its contents:**

To copy an entire directory, use the **`-r`** flag (recursive):

```bash
cp -r documents backup_documents

```

The **`-r`** flag is only **required** for directories. It is still accepted on a single file, where it simply copies that file.

**Note:** **`cp`** will **overwrite** the destination file if it already exists.

Use the **`-i`** flag to get a confirmation prompt before overwriting:

```bash
cp -i readme.txt backup.txt
```
## **Move And Rename A File**

The **`mv`** command stands for **move**. It is used to **move a file to a different location** or to **rename a file**: both actions use the exact same command.

The basic format is:

```python
mv source destination

```

**Renaming a file:**

To rename **`readme.txt`** to **`info.txt`**:

```python
mv readme.txt info.txt

```

The file stays in the same directory but now has a new name.

**Moving a file to another directory:**

To move **`readme.txt`** into the **`documents`** folder:

```python
mv readme.txt documents/

```

The original file is removed from the current directory and placed inside **`documents`**.

**Moving and renaming at the same time:**

You can move a file to a new location and give it a new name in one command:

```python
mv readme.txt documents/info.txt

```

**Note:** Unlike **`cp`**, **`mv`** does **not** keep the original file. It is moved, not copied.

Use **`-i`** to get a prompt before overwriting an existing file:

```python
mv -i readme.txt documents/
```

## **Delete A File**

The **`rm`** command stands for **remove**. It permanently **deletes a file** from the filesystem.

Simply type **`rm`** followed by the filename:

```python
rm readme.txt

```

The file is deleted immediately. You can confirm it is gone with **`ls`**.

**Deleting multiple files at once:**

```python
rm file1.txt file2.txt file3.txt

```

**Deleting a folder and all its contents:**

To delete an entire directory including everything inside it, use the **`-r`** flag (recursive):

```python
rm -r documents

```

**Safety flags:**

**`-i`**: asks for confirmation before deleting each file:

```python
rm -i readme.txt

```

**`-f`**: force delete without any prompts (use with caution!):

```python
rm -f readme.txt

```

> ***Warning:** The terminal has **no recycle bin**. Files deleted with **`rm`** are gone permanently and cannot be recovered. Always double-check before running **`rm`**.*

# Directories

## **Create A Directory**

The **`mkdir`** command stands for **make directory**. It creates a new folder in your current location.

Simply type **`mkdir`** followed by the name of the folder you want to create:
```python
mkdir projects

```

You can confirm it was created by running **`ls`**:
```python
ls
documents
projects
readme.txt

```

**Creating multiple directories at once:**

You can create several folders in a single command by listing them separated by spaces:
```python
mkdir projects documents backups

```

**Creating nested directories:**

Use the **`-p`** flag to create a directory and all its parent directories at once:
```python
mkdir -p projects/app/src

```

Without **`-p`**, this would fail if **`projects`** or **`app`** don't already exist. With **`-p`**, all three folders are created automatically.

**Note:** Directory names follow the same rules as file names: avoid spaces and special characters. Use hyphens or underscores instead:
```python
mkdir my-project    # ✅ good
mkdir my_project    # ✅ good
mkdir my project    # ❌ creates two folders: my and project
```

## **Copy A Directory**

Just like copying a file with **`cp`**, you can also copy an entire directory. However, to copy a directory and **all of its contents**, you must use the **`-r`** flag, which stands for **recursive**.

The basic format is:
```python
cp -r source destination

```

For example, to copy the **`documents`** folder and name the copy **`documents_backup`**:
```python
cp -r documents documents_backup

```

Both the original folder and the copy will now exist. You can verify with **`ls`**:
```python
ls
documents
documents_backup
readme.txt

```

**Copying a directory into another directory:**

If the destination already exists as a directory, the source folder will be placed **inside** it:
```python
cp -r documents projects/

```

This creates **`projects/documents`** with all the original contents.

**Note:** Without the **`-r`** flag, **`cp`** will refuse to copy a directory and show an error. Always use **`-r`** when copying folders.

## **Move And Rename A Directory**

Just like with files, the **`mv`** command is used to **move or rename a directory**. The great thing about **`mv`** is that it works the same way for both files and folders: no extra flags needed.

The basic format is:
```python
mv source destination

```

**Renaming a directory:**

To rename the **`documents`** folder to **`files`**:
```python
mv documents files

```

The folder stays in the same location but now has a new name.

**Moving a directory into another directory:**

To move the **`documents`** folder into a folder called **`projects`**:
```python
mv documents projects/

```

The **`documents`** folder is now located at **`projects/documents`**.

**Moving and renaming at the same time:**

You can move a directory to a new location and give it a new name in one command:
```python
mv documents projects/files

```

**Note:** Unlike **`cp -r`**, **`mv`** does **not** keep the original directory. It is moved entirely. Always double-check your source and destination before running **`mv`**.

## **Delete A Directory**

To delete a directory in the terminal, you have two options depending on whether the directory is empty or not.

**Deleting an empty directory:**

The **`rmdir`** command stands for **remove directory**. It can only delete a directory that is **completely empty**:
```python
rmdir empty_folder

```

If the folder contains any files or subdirectories, **`rmdir`** will fail with an error.

**Deleting a directory and all its contents:**

To delete a directory along with everything inside it, use **`rm`** with the **`-r`** flag (recursive):
```python
rm -r documents

```

This removes the **`documents`** folder and every file and subfolder inside it.

You can also combine it with **`-f`** to force delete without any confirmation prompts:
```python
rm -rf documents

```

> ***Warning:** **`rm -rf`** is one of the most powerful and dangerous commands in the terminal. It permanently deletes everything without asking. Always double-check your path before running it. There is no undo.*

# **Wildcards and Patterns**

## **The Star Wildcard**

A **wildcard** is a special character that acts as a placeholder to match one or more characters in filenames. Wildcards let you work with multiple files at once without typing every name.

The **star wildcard** **`*`** matches **any number of characters** (including zero). It is the most powerful and commonly used wildcard.

For example, to list all files ending in **`.txt`**:
```bash
ls *.txt

```

This matches any filename that ends with **`.txt`**, no matter how long the name is.

**More examples:**

Match all files starting with **`photo`**:
```bash
ls photo*

```

Match all files containing **`report`** anywhere in the name:
```bash
ls *report*

```

Match all files of any name or extension:
```bash
ls *

```

You can use **`*`** with any command, not just **`ls`**. For example, copy all **`.jpg`** files into a folder:
```bash
cp *.jpg photos/

```

Or delete all **`.log`** files at once:
```bash
rm *.log

```

> ***Tip:** Always run **`ls`** with your wildcard pattern first before using it with **`rm`** or **`mv`**. This way you can see exactly which files will be affected before making any changes.*

## **The Question Mark Wildcard**

The **question mark wildcard** **`?`** matches **exactly one character**. Unlike **`*`**, which matches any number of characters, **`?`** is more precise: each **`?`** represents a single character position.

For example, if you have these files:
```bash
file1.txt
file2.txt
file3.txt
file10.txt
notes.txt

```

Using **`?`** to match files with exactly one character after **`file`**:
```bash
ls file?.txt

```

Output:
```bash
file1.txt
file2.txt
file3.txt

```

Notice that **`file10.txt`** is **not** matched because **`10`** is two characters, not one.

**Using multiple question marks:**

Each **`?`** matches exactly one character, so you can chain them:
```bash
ls file??.txt  # matches file10.txt, file23.txt, etc.

```

**Mixing with other characters:**
```bash
ls ???.txt     # matches any .txt file with exactly a 3-character name
ls img_?.jpg   # matches img_1.jpg, img_2.jpg but NOT img_10.jpg

```

**When to use `?` vs `*`:**

- Use **`?`** when you know exactly how many characters vary.
- Use **`*`** when the number of varying characters is unknown.

## Bracket Wildcards

The bracket wildcard `[]` matches exactly one character from a specific set or range of characters that you define inside the brackets.

For example, if you have these files:

```text
file1.txt
file2.txt
file3.txt
file4.txt
file5.txt
```

### Matching specific characters

Match only files with `1`, `2`, or `3`:

```bash
ls file[123].txt
```

**Output:**

```text
file1.txt
file2.txt
file3.txt
```

- `[]`: Matches exactly one character from the set of characters inside the brackets.
- `[123]`: Matches one character that is either `1`, `2`, or `3`.
- `ls`: A command that lists files and directories.

### Using ranges inside brackets

Instead of listing every character, you can use a range with a hyphen `-`:

```bash
ls file[1-3].txt    # same as [123]
ls file[a-z].txt    # matches any lowercase letter
ls file[A-Z].txt    # matches any uppercase letter
ls file[0-9].txt    # matches any single digit
```

- `-`: Defines a range between two characters.
- `[1-3]`: Matches one digit from `1` to `3`.
- `[a-z]`: Matches one lowercase letter from `a` to `z`.
- `[A-Z]`: Matches one uppercase letter from `A` to `Z`.
- `[0-9]`: Matches one digit from `0` to `9`.
- **Lowercase:** Letters from `a` to `z`.
- **Uppercase:** Letters from `A` to `Z`.
- **Digit:** A numeric character from `0` to `9`.

### Negating a bracket pattern

Use `!` or `^` at the start of the bracket expression to match any character **not** in the specified set:

```bash
ls file[!45].txt    # matches file1, file2, file3 but NOT file4 or file5
ls file[^45].txt    # same result
```

- `!`: When placed immediately after `[`, it excludes the listed characters in Bash and many other shells.
- `^`: Also indicates negation in many shells, including Bash, when placed immediately after `[`.
- **Negating:** Excluding specified characters from a match.
- `[!45]` or `[^45]`: Matches one character other than `4` or `5`.

**Note:** These patterns match filenames only if the corresponding files exist. For example, `file[!45].txt` can match `file1.txt`, `file2.txt`, or `file3.txt` among the example files, but it can also match other single-character filenames such as `filea.txt` if they exist.

### Combining character sets

You can combine individual characters and ranges in the same bracket expression:

```bash
ls file[1-3a-c].txt
```

This matches:

- `file1.txt`
- `file2.txt`
- `file3.txt`
- `filea.txt`
- `fileb.txt`
- `filec.txt`

- `[1-3a-c]`: Matches exactly one character that is either a digit from `1` to `3` or a lowercase letter from `a` to `c`.
- **Character set:** A collection of characters that a pattern is allowed to match.
- **Wildcard pattern:** A pattern used by the shell to find filenames that match specified rules.

**Key takeaway:** Bracket wildcards match **exactly one character** from a set or range. They are useful when you want to match specific characters, character ranges, or everything except certain characters.

## Combining Wildcards

The real power of wildcards comes when you **combine them together**. You can mix `*`, `?`, and `[]` in a single pattern to create very precise file matching.

Given this filesystem:

```text
photo_1.jpg
photo_2.jpg
photo_10.jpg
photo_1.png
photo_2.png
report_1.txt
report_2.txt
notes.txt
```

### Combining `*` and `[]`

List image files with the extensions `.jpg` and `.png`:

```bash
ls *.[jp]*
```

This matches filenames containing a dot followed by `j` or `p`, then any number of additional characters. For the example files, it matches `.jpg` and `.png` files.

You can also use **brace expansion** to list files with specific extensions:

```bash
ls *.{jpg,png}
```

- `*`: Matches zero or more characters.
- `[jp]`: Matches exactly one character, either `j` or `p`.
- `.{jpg,png}`: Brace expansion generates separate patterns, `*.jpg` and `*.png`, before the shell runs `ls`.
- **Brace expansion:** A shell feature that generates multiple strings from a pattern containing braces and comma-separated alternatives.

**Note:** `*.[jp]*` can also match other extensions beginning with `j` or `p`, such as `.jpeg`. It is broader than matching only `.jpg` and `.png`.

### Combining `?` and `[]`

List only single-digit photo files ending in `.jpg`:

```bash
ls photo_[0-9].jpg
```

This matches:

```text
photo_1.jpg
photo_2.jpg
```

It does not match `photo_10.jpg` because `[0-9]` matches exactly one digit.

- `?`: Matches exactly one character of any kind.
- `[0-9]`: Matches exactly one digit from `0` to `9`.
- **Single-digit:** A number represented by one digit, such as `1` or `7`.

### Combining all three wildcards

Match report files with a single digit before `.txt`:

```bash
ls *_[0-9].txt
```

This matches:

```text
report_1.txt
report_2.txt
```

Explanation:

- `*`: Matches zero or more characters before the underscore.
- `_`: Matches a literal underscore.
- `[0-9]`: Matches exactly one digit.
- `.txt`: Matches the literal `.txt` extension.

Now match files that start with `p` or `r`, followed by any characters, an underscore, exactly one character, and `.txt`:

```bash
ls [pr]*_?.txt
```

This matches:

```text
report_1.txt
report_2.txt
```

Explanation:

- `[pr]`: Matches exactly one character, either `p` or `r`.
- `*`: Matches zero or more characters after the first character.
- `_`: Matches a literal underscore.
- `?`: Matches exactly one character after the underscore.
- `.txt`: Matches the literal `.txt` extension.

**Important:** In the example filesystem, `notes.txt` does not match because its name does not contain the required underscore and extra character before `.txt`.

### Using wildcards with other commands

Wildcards work with many shell commands, not just `ls`.

#### Move single-digit JPG photos into a folder

```bash
mv photo_[0-9].jpg archive/
```

This moves files such as `photo_1.jpg` and `photo_2.jpg` into the `archive/` directory.

- `mv`: Moves files or directories, and can also rename them.
- `archive/`: The destination directory. It must already exist for this command to work as intended.

#### Delete `.log` files from immediate subfolders

```bash
rm */*.log
```

This removes `.log` files located one directory level below the current directory.

- `rm`: Removes files.
- `*/*.log`: Matches files whose parent directory is one level below the current directory and whose names end in `.log`.
- **Subfolder:** A directory inside another directory.
- **Immediate subfolder:** A directory directly inside the current directory, rather than a deeper nested directory.

**Warning:** `rm` deletes files without moving them to a recycle bin in typical command-line environments. Check what a wildcard matches before running a deletion command. You can preview matching paths with:

```bash
ls */*.log
```

### Key takeaway

- `*` matches zero or more characters.
- `?` matches exactly one character.
- `[]` matches exactly one character from a specified set or range.
- `{a,b}` uses brace expansion to generate alternatives; it is not a wildcard itself.

Combining these patterns lets you select files precisely for listing, moving, copying, or deleting.

# File Content

## Head And Tail

When working with large files, you often don't need to read the entire file. You just need to see the beginning or the end. The **`head`** and **`tail`** commands let you do exactly that.

### The `head` command

The **`head`** command shows the **first lines** of a file. By default, it shows the first 10 lines:

```bash
head log.txt
```

To specify how many lines to show, use the **`-n`** flag:

```bash
head -n 3 log.txt   # show first 3 lines
head -n 1 log.txt   # show only the first line
```

- **`head`**: Displays the beginning of a file.
- **`-n`**: Specifies the number of lines to display.
- **`log.txt`**: The name of the file being read.
- **Flag (option):** An argument that changes how a command behaves.

### The `tail` command

The **`tail`** command shows the **last lines** of a file. By default, it shows the last 10 lines:

```bash
tail log.txt
```

To specify how many lines to show:

```bash
tail -n 3 log.txt   # show last 3 lines
tail -n 1 log.txt   # show only the last line
```

- **`tail`**: Displays the end of a file.
- **`-n`**: Specifies the number of lines to display.
- **Log file:** A file that records events, activities, or messages produced by a program or system.

### When to use each

- Use **`head`** to preview the structure or header of a file.
- Use **`tail`** to check the most recent entries in a log file.

### A useful trick: combining both

You can use both commands together to see the start and end of a file at the same time:

```bash
head -n 2 log.txt
tail -n 2 log.txt
```

- `head -n 2 log.txt` displays the first two lines.
- `tail -n 2 log.txt` displays the last two lines.

**Note:** These are two separate commands, so they display their results one after the other.

**Key takeaway:** Use `head` to inspect the beginning of a file and `tail` to inspect its end without displaying the entire contents.

## **Word Count**

The **`wc`** command stands for **word count**. It counts the number of lines, words and characters in a file.

we have **`notes.txt`**:

```text
Buy groceries from the store
Call the doctor tomorrow morning
Finish the terminal course today
Read the new book this weekend
Clean up the project folder
```

Simply type **`wc`** followed by the filename:

```bash
wc notes.txt
```

The output shows three numbers followed by the filename:

```text
  5  26  154 notes.txt
```

- First number: number of **lines**
- Second number: number of **words**
- Third number: number of **bytes** (the same as the character count for plain English text)

You can also use flags to get only the information you need:

**`-l`**: count only **lines**:

```bash
wc -l notes.txt
```

**`-w`**: count only **words**:

```bash
wc -w notes.txt
```

**`-c`**: count only **bytes** (use **`-m`** for characters, which differs for accented or non-Latin text):

```bash
wc -c notes.txt
```

**Counting multiple files at once:**

```bash
wc -l *.txt   # count lines in all .txt files
```

**How does `wc -l` count lines?**

**`wc -l`** counts **newline characters** (**`\n`**), not the number of visible lines. This means if your file has 5 lines but the last line has **no newline at the end**, **`wc -l`** will report **`4`** instead of **`5`**.

This is standard Unix behavior: a proper text file should always end with a newline character on the last line. Most text editors add this automatically.

```bash
wc -l notes.txt
5 notes.txt   # correct: last line ends with newline

wc -l notes.txt
4 notes.txt   # missing newline at end of file
```

### **Common use cases:**

- Check how many lines are in a large log file
- Count words in a document
- Verify a file has the expected number of entries

**Note:** The example output `5 26 154 notes.txt` assumes the file contains five newline-terminated lines with the stated byte count. The exact counts depend on the file's contents, spacing, encoding, and whether the last line ends with a newline.

## **Sort Command**

The **`sort`** command arranges the lines of a file in **alphabetical or numerical order**.

We have **`fruits.txt`**:

```text
banana
apple
cherry
mango
```

Simply type **`sort`** followed by the filename:

```bash
sort fruits.txt
```

The output will be:

```text
apple
banana
cherry
mango
```

### **Useful flags:**

**`-r`**: sort in **reverse** (descending) order:

```bash
sort -r fruits.txt
```

**`-n`**: sort **numerically** instead of alphabetically:

```bash
sort -n numbers.txt
```

Without **`-n`**, numbers are sorted as text, so **`10`** would come before **`2`**. With **`-n`**, they sort correctly by value.

For example, if `numbers.txt` contains:

```text
10
2
30
1
```

Without `-n`:

```bash
sort numbers.txt
```

Output:

```text
1
10
2
30
```

With `-n`:

```bash
sort -n numbers.txt
```

Output:

```text
1
2
10
30
```

**`-u`**: sort and remove **duplicate lines** at the same time:

```bash
sort -u fruits.txt
```

**`-k`**: sort by a specific **column** (useful for files with multiple columns):

```bash
sort -k2 data.txt   # sort by the second column
```

For example, if `data.txt` contains:

```text
John 30
Alice 25
Mark 40
```

Running:

```bash
sort -k2 data.txt
```

Sorts the lines based on the second column.

**Note:** By default, `sort` does not modify the original file. It only prints the sorted result to the screen.


## Unique Command

The `uniq` command filters out consecutive duplicate lines from a file, showing only unique lines.

### Example File

We have a file named `duplicates.txt` containing:

```text
apple
banana
apple
cherry
banana
banana
```

### Removing Consecutive Duplicates

**Important:** `uniq` only removes duplicates that are next to each other. In the example above, the two consecutive `banana` lines are duplicates, but the two `apple` lines are not consecutive.

This is why `uniq` is almost always used together with `sort` first:

```bash
sort duplicates.txt | uniq
```

Output:

```text
apple
banana
cherry
```

The `sort` command sorts the lines alphabetically, placing identical lines next to each other. Then `uniq` removes the consecutive duplicates.

### Understanding the Pipe (`|`)

The `|` symbol is called a **pipe**. It sends the output of one command as the input to another command.

For example:

```bash
sort duplicates.txt | uniq
```

1. `sort duplicates.txt` sorts the contents of the file.
2. `|` sends the sorted output to the next command.
3. `uniq` removes consecutive duplicate lines.

This is a powerful pattern you will use often in the terminal.

### Useful Flags

#### 1. `-c` — Count Occurrences

The `-c` flag prefixes each line with the number of times it appears.

```bash
sort duplicates.txt | uniq -c
```

Output:

```text
      2 apple
      3 banana
      1 cherry
```

**Explanation:**

- `apple` appears 2 times.
- `banana` appears 3 times.
- `cherry` appears 1 time.

#### 2. `-d` — Show Only Duplicated Lines

The `-d` flag shows only lines that appear more than once consecutively in the input.

```bash
sort duplicates.txt | uniq -d
```

Output:

```text
apple
banana
```

Both `apple` and `banana` appear more than once in the file.

#### 3. `-u` — Show Only Unique Occurrences

The `-u` flag shows only lines that appear exactly once in the input.

```bash
sort duplicates.txt | uniq -u
```

Output:

```text
cherry
```

`cherry` appears only once in the file.

### Key Takeaways

- `uniq` removes consecutive duplicate lines.
- `sort` is commonly used before `uniq` to group identical lines together.
- `|` passes the output of one command to another.
- `uniq -c` counts occurrences of each line.
- `uniq -d` shows only duplicated lines.
- `uniq -u` shows only lines that occur once.

**Remember:** `uniq` does not automatically sort the input. Using `sort` first ensures that identical lines are grouped together, allowing `uniq` to process them correctly.

## **Grep Basics**

**`grep`** stands for **Global Regular Expression Print**. It is one of the most powerful and commonly used terminal commands. It searches through files and prints every line that contains a matching pattern.

We have **`server.log`**:

```text
info: server started
info: listening on port 8080
error: disk full
warning: high memory usage
info: request received
error: connection timeout
info: server shutdown
```

The basic format is:

```bash
grep "pattern" filename
```

For example, to find every line that contains the word **`error`**:

```bash
grep "error" server.log
```

Output:

```text
error: disk full
error: connection timeout
```

Only the lines containing **`error`** are printed. All other lines are hidden.

### **Searching in multiple files:**

```bash
grep "error" *.log   # search all .log files
```

### **Searching for a phrase with spaces:**

```bash
grep "connection timeout" server.log
```

### **Case sensitivity:**

By default, **`grep`** is **case sensitive**. So searching for **`error`** will not match **`Error`** or **`ERROR`**:

```bash
grep "error" server.log    # matches: error
grep "Error" server.log    # matches: Error
grep "ERROR" server.log    # matches: ERROR
```

### **Brief explanation of important terms:**

- **`grep`:** A command used to search for matching text in files.
- **Pattern:** The text or regular expression that `grep` searches for.
- **Filename:** The file in which `grep` searches.
- **Case sensitive:** Treats uppercase and lowercase letters as different characters.
- **`*.log`:** A wildcard pattern that matches filenames ending in `.log`.
- **Quotes (`" "`):** Keep a phrase with spaces together as one search pattern.
- **Matching line:** A line that contains the specified pattern.


## **Grep With Flags**

**`grep`** becomes even more powerful when you add **flags** to control how it searches and what it displays.

### **Most useful grep flags:**

**`-i`**: **case insensitive** search. Matches regardless of uppercase or lowercase:

```bash
grep -i "error" server.log   # matches error, Error, ERROR
```

**`-n`**: show **line numbers** alongside each matching line:

```bash
grep -n "error" server.log
3:error: disk full
6:error: connection timeout
```

**`-c`**: show only the **count** of matching lines, not the lines themselves:

```bash
grep -c "error" server.log
2
```

**`-v`**, **invert** the search, show lines that do **not** match the pattern:

```bash
grep -v "info" server.log
error: disk full
warning: high memory usage
error: connection timeout
```

**`-r`**: search **recursively** through all files in a directory:

```bash
grep -r "error" logs/   # search all files inside the logs folder
```

**`-l`**: show only the **filenames** that contain a match, not the matching lines:

```bash
grep -l "error" *.log
```

### **Combining flags:**

You can combine multiple flags together:

```bash
grep -in "error" server.log   # case insensitive + show line numbers
grep -vc "info" server.log    # invert + count non-info lines
```

### **Brief explanation of important terms:**

- **Flag:** An option added to a command to change its behavior.
- **Case insensitive (`-i`):** Treats uppercase and lowercase letters as equivalent.
- **Line number (`-n`):** Displays the line's position in the file where the match was found.
- **Count (`-c`):** Displays the number of matching lines.
- **Invert (`-v`):** Displays lines that do not contain the specified pattern.
- **Recursive (`-r`):** Searches through files in a directory and its subdirectories.
- **Filename (`-l`):** Displays the names of files that contain at least one match.
- **Combining flags:** Using more than one flag in the same command, such as `-in` for case-insensitive search with line numbers.

# Redirection

## **Standard Output**

Every command in the terminal has three **data streams** connected to it. Understanding these streams is the foundation of redirection: one of the most powerful features of the command line.

The first stream is called **standard output**, often abbreviated as **`stdout`**. This is where commands send their normal results. When you run **`ls`** or **`cat`**, the text you see on screen is coming through standard output.

```bash
echo "Hello, World!"
```

The message **`Hello, World!`** is sent to standard output, which by default displays on your terminal screen.

Similarly, when you list files:

```bash
ls
```

The list of filenames flows through standard output to your screen.

By default, standard output is connected to your terminal display. But here is where it gets interesting. You can **redirect** this output somewhere else, like into a file. Instead of seeing the results on screen, you can capture them for later use.

In the upcoming lessons, you will learn how to redirect standard output to files, and discover the other two streams: standard input and standard error.

### **Brief explanation of important terms:**

- **Data streams:** Channels used by a command to receive input or send output.
- **Standard output (`stdout`):** The stream where a command sends its normal results.
- **Redirection:** Changing where a command's input or output goes.
- **Terminal:** The interface where you type commands and view their output.
- **`echo`:** A command that displays text.
- **`ls`:** A command that lists files and directories.
- **`cat`:** A command commonly used to display the contents of files.


## **Overwrite To A File**

Now that you understand standard output, let's redirect it somewhere useful. The **`>`** operator takes the output of a command and writes it to a file instead of displaying it on screen.

```bash
echo "Hello" > greeting.txt
```

This creates a file called **`greeting.txt`** containing the word **`Hello`**. Nothing appears on screen because the output went into the file instead.

You can redirect the output of any command:

```bash
ls > filelist.txt
cat names.txt > backup.txt
date > timestamp.txt
```

**Warning:** The **`>`** operator **overwrites** the file completely. If the file already exists, its previous contents are erased and replaced with the new output.

```bash
echo "First line" > notes.txt
echo "Second line" > notes.txt
cat notes.txt
```

Output:

```text
Second line
```

The first line is gone because the second command overwrote the entire file. This behavior is powerful but requires caution. You can accidentally lose data if you redirect to an existing file.

### **Brief explanation of important terms:**

- **`>` (redirection operator):** Sends a command's standard output into a file.
- **Overwrite:** Replaces the existing contents of a file with new content.
- **`greeting.txt`:** The file receiving the output from the `echo` command.
- **`echo`:** Displays text, which can be redirected into a file.
- **`cat`:** Displays the contents of a file.
- **`ls`:** Lists files and directories.
- **`date`:** Displays the current date and time.
- **Standard output (`stdout`):** The stream carrying a command's normal results.


## **Append To A File**

The **`>`** operator overwrites files, which can be dangerous when you want to keep existing content. The **`>>`** operator solves this by **appending** to a file instead of replacing it.

```bash id="8q2f6s"
echo "First line" >> notes.txt
echo "Second line" >> notes.txt
cat notes.txt
```

Output:

```text id="6y2b8v"
First line
Second line
```

Both lines are preserved because **`>>`** adds new content at the end of the file. If the file does not exist, it creates a new one, just like **`>`** does.

This is perfect for building log files or collecting output over time:

```bash id="j2n5gk"
date >> activity.log
echo "User logged in" >> activity.log
date >> activity.log
echo "User logged out" >> activity.log
```

Each command adds a new line to **`activity.log`** without erasing previous entries. Use **`>`** when you want a fresh start, and **`>>`** when you want to accumulate data.

### **Brief explanation of important terms:**

- **`>>` (append operator):** Adds command output to the end of a file.
- **Append:** Add new content while preserving the existing content.
- **`>` (overwrite operator):** Replaces the existing contents of a file.
- **`notes.txt`:** The file that receives the text from the `echo` commands.
- **`cat`:** Displays the contents of a file.
- **`date`:** Displays the current date and time.
- **`activity.log`:** A log file that collects entries over time.
- **Log file:** A file used to record events or activities.


## **Standard Input**

The second data stream is **standard input**, abbreviated as **`stdin`**. While standard output is where commands send their results, standard input is where commands **receive** data.

Many commands can read from a file by taking the filename as an argument:

```bash id="n6k2v4"
cat notes.txt
sort names.txt
```

But you can also redirect a file's contents directly into a command using the **`<`** operator:

```bash id="g4w7p2"
sort < names.txt
```

This feeds the contents of **`names.txt`** into the **`sort`** command through standard input. The result is the same as **`sort names.txt`**, but the mechanism is different: the shell opens the file and connects it to standard input, instead of the command opening the file by its name.

You can combine input and output redirection in a single command:

```bash id="b8r3x1"
sort < names.txt > sorted_names.txt
```

This reads from **`names.txt`**, sorts the content, and writes the result to **`sorted_names.txt`**. Input redirection becomes especially useful when working with commands that expect data from standard input rather than a filename argument.

### **Brief explanation of important terms:**

- **Standard input (`stdin`):** The stream through which a command receives data.
- **`<` (input redirection operator):** Redirects a file's contents into a command's standard input.
- **`sort`:** Arranges lines of text in a specified order.
- **`cat`:** Displays the contents of a file.
- **Shell:** The program that interprets commands and handles redirection.
- **`>` (output redirection operator):** Sends a command's output to a file, overwriting its existing contents.
- **`sorted_names.txt`:** The file where the sorted output is saved.
- **Input redirection:** Supplying data to a command through standard input rather than through a filename argument.


## **Standard Error**

The third and final data stream is **standard error**, abbreviated as **`stderr`**. This stream is specifically for error messages and warnings, keeping them separate from normal output.

When a command fails, the error message goes to standard error, not standard output:

```bash id="q4n6v8"
ls nonexistent_folder
```

The error message you see comes through stderr. This separation matters because you can redirect errors independently from regular output.

To redirect standard error, use **`2>`** instead of **`>`**:

```bash id="x7m2p5"
ls nonexistent_folder 2> errors.txt
```

The **`2`** refers to stderr's file descriptor number (stdout is **`1`**, stderr is **`2`**). This command captures the error message in **`errors.txt`** while keeping your terminal clean.

You can redirect both streams to different files:

```bash id="k8r3t1"
ls existing_folder nonexistent_folder > output.txt 2> errors.txt
```

Successful output goes to **`output.txt`**, while any errors go to **`errors.txt`**. To send both streams to the same file, use **`2>&1`**:

```bash id="c9w5f2"
ls existing_folder nonexistent_folder > all_output.txt 2>&1
```

This redirects stderr to wherever stdout is going, combining everything into one file.

### **Brief explanation of important terms:**

- **Standard error (`stderr`):** The stream used by a command to send error messages and warnings.
- **`2>`:** Redirects standard error to a file, overwriting the file if it already exists.
- **File descriptor:** A number used by the operating system to identify an open input or output stream.
- **`1`:** The file descriptor for standard output (`stdout`).
- **`2`:** The file descriptor for standard error (`stderr`).
- **`output.txt`:** The file where normal output is saved.
- **`errors.txt`:** The file where error messages are saved.
- **`2>&1`:** Redirects standard error to the same destination as standard output.
- **`all_output.txt`:** The file that receives both standard output and standard error.

# Piping

## What Is a Pipe?

A **pipe** is a way to send the output of one command directly into another command.

In the terminal, the pipe symbol is:

```bash
|
```

It takes the **standard output (`stdout`)** of the command on its left and sends it as the **standard input (`stdin`)** to the command on its right.

**Example**

Suppose you have a file named `names.txt` containing a list of names.

You can use `cat` to display the file's contents and `sort` to sort them alphabetically:

```bash
cat names.txt | sort
```

### How does it work?

1. `cat names.txt` reads the file and sends its contents to standard output.
2. The pipe (`|`) takes that output and sends it to the next command.
3. `sort` receives the contents as standard input and sorts the names alphabetically.
4. The sorted result is displayed in the terminal.

The important thing is that the output of the first command becomes the input of the second command without creating an intermediate file.

### Using a Temporary File Instead

You could achieve a similar result by saving the output of the first command in a temporary file:

```bash
cat names.txt > temp.txt
sort < temp.txt
```

Here:

- `>` redirects the output of `cat` into `temp.txt`.
- `<` redirects the contents of `temp.txt` into `sort`.

However, this approach creates an additional file that you may need to delete afterward:

```bash
rm temp.txt
```

Using a pipe avoids the need for this temporary file.

### What Is a Pipeline?

A **pipeline** is a sequence of two or more commands connected using pipes.

For example:

```bash
cat names.txt | sort | uniq
```

This command performs three operations:

1. `cat names.txt` reads the file.
2. `sort` sorts the names alphabetically.
3. `uniq` removes adjacent duplicate lines.

Each command receives the output of the previous command as its input.

### **Remember:**

- `|` connects commands.
- The command on the left sends its standard output to the pipe.
- The command on the right receives that output as standard input.
- You can connect multiple commands to create a pipeline.
- Pipes allow you to combine commands without creating temporary files.



## Chaining Two Commands

Now that you understand what a pipe does, let's see how to use it effectively with two commands.

The key is choosing commands that work well together, where the output of the first command makes sense as input for the second.

**Example 1: Counting Files with `ls` and `wc -l`**

A common pairing is **`ls`** with **`wc -l`** to count directory entries:

```bash
ls | wc -l
```

- **`ls`** lists the files and directories in the current directory, typically one entry per line when its output is piped.
- **`|`** sends the output of `ls` to the next command.
- **`wc -l`** counts the number of lines it receives.

The result is the number of entries listed in the current directory (including directories, not just regular files).

**Example 2: Previewing a File with `cat` and `head`**

Another useful combination is **`cat`** with **`head`** to preview a file:

```bash
cat longfile.txt | head -5
```

This displays only the first **5 lines** of the file.

Here's how it works:

1. `cat longfile.txt` reads the file and sends its contents to standard output.
2. The pipe (`|`) sends that output to `head`.
3. `head -5` displays only the first five lines.

You could also use **`head -5 longfile.txt`** directly, since `head` can read a file by itself.

However, piping becomes essential when the first command generates output that isn't simply reading a file.

**Example 3: Displaying Detailed Information with `ls -l` and `head`**

For example, you can combine **`ls -l`** with **`head`**:

```bash
ls -l | head -3
```

This displays only the first **3 lines** of the detailed directory listing.

- **`ls -l`** displays detailed information about directory entries, such as permissions, owner, size, and modification date.
- **`head -3`** displays only the first three lines of that output.

The pipe transforms two simple commands into a more powerful operation by allowing one command's output to become another command's input.

### Important Terms

- **`ls`**: Lists files and directories.
- **`wc -l`**: Counts the number of lines.
- **`cat`**: Displays the contents of a file.
- **`head -5`**: Displays the first five lines.
- **`head -3`**: Displays the first three lines.
- **Command chaining**: Connecting commands so they work together.
- **Pipe (`|`)**: Sends the output of one command to another as input.



## Chaining Multiple Commands

You're not limited to connecting just two commands. Pipes can chain as many commands as you need, with each one processing the output of the previous command.

Simply add more **`|`** symbols to extend the pipeline:

```bash
cat data.txt | sort | head -5
```

This command performs three operations:

1. `cat data.txt` reads the file and sends its contents to standard output.
2. `sort` sorts all lines alphabetically.
3. `head -5` displays only the first 5 lines of the sorted output.

Data flows from left to right through each command in sequence.

**Example 2: Finding Unique Entries**

Here's a practical example that finds unique sorted entries:

```bash
cat names.txt | sort | uniq
```

The file contents get sorted first, which groups duplicate lines together. Then **`uniq`** removes consecutive duplicate lines.

**The order matters here:** `uniq` only removes adjacent duplicates, so sorting must come first to ensure identical entries are next to each other.

**Example 3: Counting Unique Entries**

You can add even more stages. To count how many unique names exist:

```bash
cat names.txt | sort | uniq | wc -l
```

This pipeline performs four operations:

1. `cat names.txt` reads the file.
2. `sort` sorts the names alphabetically.
3. `uniq` removes consecutive duplicate names.
4. `wc -l` counts the remaining lines.

The result is the number of unique names in the file.

### Important Terms

- **Pipeline**: A sequence of commands connected using pipes.
- **`sort`**: Sorts lines alphabetically by default.
- **`uniq`**: Removes consecutive duplicate lines.
- **`wc -l`**: Counts the number of lines.
- **Transformation step**: An operation that changes or processes the data as it passes through a pipeline.
- **Data flow**: The movement of output from one command to the next.

**Remember:** Each pipe adds another transformation step. When building longer pipelines, think about what each command needs as input and what it produces as output. The output format of one command must make sense as input for the next.

