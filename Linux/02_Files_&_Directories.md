
# Directories
---

### 1. **`ls`** - List Directory Contents

The `ls` command lists the files and directories in the current directory.

- **Flags**:
  - `-l`: Long listing format (permissions, size, owner, etc.)
  - `-a`: Show hidden files (those starting with `.`)
  - `-h`: Human-readable sizes (e.g., 1K, 5M)
  - `-r`: Reverse order
  - `-t`: Sort by modification time (newest first)

**Examples**:
```bash
# List all files and directories, including hidden ones, in long format
ls -la

# List files in reverse order, sorted by modification time
ls -ltr

# List files with human-readable sizes (e.g., MB, GB)
ls -lh
```

---

### 2. **`cd`** - Change Directory

The `cd` command changes the current directory.

- **Flags**:
  - `-`: Change to the previous directory.

**Examples**:
```bash
# Change to a specific directory
cd /home/user/Documents

# Go to the previous directory
cd -
```

---

### 3. **`pwd`** - Print Working Directory

The `pwd` command prints the full path of the current directory.

**Examples**:
```bash
# Display the current working directory
pwd
```

---

### 4. **`mkdir`** - Make Directory

The `mkdir` command creates new directories.

- **Flags**:
  - `-p`: Create parent directories as needed.
  - `-v`: Verbose mode, show the directories being created.

**Examples**:
```bash
# Create a new directory
mkdir new_folder

# Create a nested directory (with parent directories)
mkdir -p new_folder/subfolder

# Create a directory and display a message
mkdir -v new_folder
```

---

### 5. **`rmdir`** - Remove Empty Directory

The `rmdir` command removes empty directories.

**Examples**:
```bash
# Remove an empty directory
rmdir empty_folder
```

---

### 6. **`rm`** - Remove Files or Directories

The `rm` command removes files or directories.

- **Flags**:
  - `-r`: Recursively remove directories and their contents.
  - `-f`: Force removal without prompting for confirmation.
  - `-v`: Verbose mode, show files being removed.
  - `-i`: Interactive mode, ask for confirmation before each file is removed.

**Examples**:
```bash
# Remove a directory and its contents
rm -r folder_to_delete

# Forcefully remove a directory and its contents without confirmation
rm -rf folder_to_delete

# Remove a file with confirmation
rm -i file.txt

# Verbosely remove files
rm -v file1.txt file2.txt
```

---

### 7. **`mv`** - Move or Rename Files or Directories

The `mv` command moves or renames files or directories.

- **Flags**:
  - `-v`: Verbose mode, show files being moved.
  - `-i`: Interactive mode, ask for confirmation before overwriting.
  - `-u`: Move only if the source file is newer than the destination.

**Examples**:
```bash
# Move a file to another directory
mv file.txt /home/user/Documents/

# Rename a directory
mv old_folder new_folder

# Move files and display verbose output
mv -v file1.txt file2.txt /home/user/backup/

# Move only if the source file is newer
mv -u file1.txt /home/user/Documents/
```

---

### 8. **`cp`** - Copy Files or Directories

The `cp` command copies files or directories.

- **Flags**:
  - `-r`: Recursively copy directories.
  - `-i`: Ask for confirmation before overwriting.
  - `-v`: Verbose mode, show files being copied.
  - `-u`: Copy only if the source file is newer than the destination.

**Examples**:
```bash
# Copy a file to another directory
cp file.txt /home/user/backup/

# Copy a directory and its contents
cp -r folder1 folder2

# Verbosely copy files
cp -v file1.txt file2.txt /home/user/Documents/

# Copy only if the source file is newer
cp -u file1.txt /home/user/Documents/
```

---

### 9. **`find`** - Search for Files or Directories

The `find` command searches for files and directories based on various criteria.

- **Flags**:
  - `-name`: Search by name.
  - `-type`: Search by type (`f` for file, `d` for directory).
  - `-exec`: Execute a command on each found file.
  - `-size`: Search by file size.

**Examples**:
```bash
# Find all `.txt` files in the current directory and subdirectories
find . -name "*.txt"

# Find all directories in `/home/user/`
find /home/user/ -type d

# Execute a command on found files (e.g., remove all `.log` files)
find . -name "*.log" -exec rm -v {} \;
```

---

### 10. **`tree`** - Display Directory Tree

The `tree` command displays the contents of directories in a tree-like format.

- **Flags**:
  - `-L <level>`: Limit the depth of the tree display.
  - `-a`: Show hidden files.
  - `-f`: Show full path for each file.

**Examples**:
```bash
# Display the directory tree with a maximum depth of 2
tree -L 2

# Display the directory tree with hidden files
tree -a

# Display the full path for each file
tree -f
```

---

### 11. **`chmod`** - Change File Permissions

The `chmod` command changes the file or directory permissions.

- **Flags**:
  - `-R`: Apply changes recursively to files in a directory.
  - `-v`: Verbose mode, show changes made.

**Examples**:
```bash
# Change the permissions of a file to read, write, and execute for the owner
chmod 755 file.txt

# Recursively change permissions of files in a directory
chmod -R 755 folder

# Verbosely change permissions
chmod -v 755 folder
```

---

### 12. **`chown`** - Change Ownership of Files or Directories

The `chown` command changes the ownership of a file or directory.

- **Flags**:
  - `-R`: Apply changes recursively to files in a directory.

**Examples**:
```bash
# Change the owner of a file to 'user' and the group to 'group'
chown user:group file.txt

# Recursively change ownership of files in a directory
chown -R user:group folder
```

---

### 13. **`ln`** - Create Hard and Symbolic Links

The `ln` command creates links to files or directories.

- **Flags**:
  - `-s`: Create a symbolic link (symlink).
  - `-f`: Force the creation of the link (overwrite existing links).

**Examples**:
```bash
# Create a symbolic link to a file
ln -s /path/to/original /path/to/symlink

# Create a hard link to a file
ln /path/to/original /path/to/hardlink

# Force the creation of a symbolic link
ln -sf /path/to/original /path/to/symlink
```

---

### 14. **`df`** - Display Disk Space Usage

The `df` command displays information about disk space usage for mounted file systems.

- **Flags**:
  - `-h`: Display sizes in human-readable format (e.g., MB, GB).
  - `-T`: Show the file system type.

**Examples**:
```bash
# Display disk space usage in human-readable format
df -h

# Display disk space usage along with file system types
df -T
```

---

### 15. **`du`** - Display Disk Usage of Files and Directories

The `du` command estimates and displays the disk usage of files and directories.

- **Flags**:
  - `-h`: Human-readable format (e.g., KB, MB).
  - `-s`: Show only the total size for each argument.
  - `-a`: Show disk usage for all files (not just directories).

**Examples**:
```bash
# Display disk usage in human-readable format
du -h

# Display total disk usage of a directory
du -sh folder

# Display disk usage for all files in a directory
du -ah folder
```

---

### 16. **`stat`** - Display Detailed Information About a File or Directory

The `stat` command provides detailed information about a file or directory.

**Examples**:
```bash
# Display detailed information about a file
stat file.txt
```

---

# Files

## To write to a file in Linux, you can use several methods :

### 1. **Using `echo` Command**
The `echo` command is used to print text to the terminal or into a file.

- **Syntax**: `echo "text" > filename`
- `>`: This operator redirects the output to the specified file, creating the file if it doesn't exist. If the file already exists, it overwrites the file.

- **Example**:
```bash
echo "Hello, this is a new line of text." > file.txt
```
This command will write "Hello, this is a new line of text." into `file.txt`.

- **To Append Text**:
You can use `>>` to append to the file without overwriting its current contents:
```bash
echo "This is another line of text." >> file.txt
```

### 2. **Using `cat` Command**

The `cat` command can be used to create and write to a file.

- **Syntax**: `cat > filename`
- Once you run the command, you can type the text you want to write into the file. To save the file and exit, press `CTRL+D`.

- **Example**:
```bash
cat > file.txt
```
After running this command, you can type your content, and when you're done, press `CTRL+D` to save and exit.

### 3. **Using `nano` or `vim` Editors**

The `nano` and `vim` commands are text editors that allow you to write and edit files.

#### Using `nano`:
- **Syntax**: `nano filename`
- This will open the `nano` text editor. After typing the text you want to save, press `CTRL+O` to write the file, and `CTRL+X` to exit.

- **Example**:
```bash
nano file.txt
```
After you type your content, press `CTRL+O` to save and `CTRL+X` to exit.

#### Using `vim`:
- **Syntax**: `vim filename`
- Open the file in `vim`. Press `i` to enter Insert mode, type the text you want, then press `ESC` to exit Insert mode. After that, type `:wq` to write and quit.

- **Example**:
```bash
vim file.txt
```
After editing, press `ESC`, type `:wq`, and hit `Enter` to save and exit.

### 4. **Using `tee` Command**

The `tee` command is used to read from standard input and write to files, and it can also be used with the `-a` flag to append text to a file.

- **Syntax**: `echo "text" | tee filename`
- **To append**: `echo "text" | tee -a filename`

- **Example**:
```bash
echo "Appended text using tee." | tee -a file.txt
```
This command appends the text "Appended text using tee." to `file.txt`.

### 5. **Using `printf` Command**

The `printf` command is similar to `echo`, but it allows more control over formatting.

- **Syntax**: `printf "formatted text" > filename`

- **Example**:
```bash
printf "This is a formatted text.\n" > file.txt
```

---

 ### **file-related commands in Ubuntu**
---

### 1. **`cat`** - Concatenate and Display Files

The `cat` command is used to display the contents of a file, concatenate multiple files, or create files.

- **Flags**:
  - `-n`: Number all output lines.
  - `-b`: Number non-blank output lines.
  - `-E`: Display `$` at the end of each line.

**Examples**:
```bash
# Display the contents of a file
cat file.txt

# Concatenate two files into a new file
cat file1.txt file2.txt > combined.txt

# Display contents with line numbers
cat -n file.txt
```

---

### 2. **`tac`** - Reverse the Output of `cat`

The `tac` command is similar to `cat`, but it displays the contents of a file in reverse order (bottom to top).

**Examples**:
```bash
# Display the contents of a file in reverse order
tac file.txt
```

---

### 3. **`more`** - View File Contents (Page-by-Page)

The `more` command is used to view the contents of a file one page at a time.

**Examples**:
```bash
# View the contents of a file one page at a time
more file.txt
```

---

### 4. **`less`** - View File Contents (More Advanced than `more`)

The `less` command allows for backward and forward navigation through a file, making it more powerful than `more`.

- **Flags**:
  - `-N`: Display line numbers.
  - `-S`: Do not wrap long lines.

**Examples**:
```bash
# View the contents of a file
less file.txt

# View a file with line numbers
less -N file.txt

# View a file without wrapping long lines
less -S file.txt
```

---

### 5. **`head`** - Display the Beginning of a File

The `head` command displays the first few lines of a file. By default, it shows the first 10 lines.

- **Flags**:
  - `-n <number>`: Display the first `n` lines.

**Examples**:
```bash
# Display the first 10 lines of a file (default)
head file.txt

# Display the first 5 lines of a file
head -n 5 file.txt
```

---

### 6. **`tail`** - Display the End of a File

The `tail` command displays the last few lines of a file. By default, it shows the last 10 lines.

- **Flags**:
  - `-n <number>`: Display the last `n` lines.
  - `-f`: Follow the file (useful for watching log files in real time).

**Examples**:
```bash
# Display the last 10 lines of a file (default)
tail file.txt

# Display the last 5 lines of a file
tail -n 5 file.txt

# Follow a file and display new lines as they are added
tail -f file.txt
```

---

### 7. **`file`** - Determine File Type

The `file` command determines the file type (e.g., text, executable, image) by analyzing the file's contents.

**Examples**:
```bash
# Determine the file type of a file
file file.txt

# Determine the file type of a file that is not a plain text file
file image.jpg
```

---

### 8. **`find`** - Search for Files and Directories

The `find` command searches for files and directories based on specified criteria like name, type, size, and more.

- **Flags**:
  - `-name <pattern>`: Search for files by name.
  - `-type <type>`: Search by type (e.g., `f` for file, `d` for directory).
  - `-exec <command>`: Execute a command on the found files.

**Examples**:
```bash
# Find files named 'file.txt' in the current directory and subdirectories
find . -name "file.txt"

# Find all directories in the `/home/user/` path
find /home/user/ -type d

# Find files and delete them (e.g., remove all `.log` files)
find . -name "*.log" -exec rm -f {} \;
```

---

### 9. **`touch`** - Create Empty Files or Update Timestamps

The `touch` command creates an empty file if it does not exist or updates the timestamp of an existing file.

- **Flags**:
  - `-c`: Do not create any files if they do not exist.
  - `-t <time>`: Set a specific time for the file.

**Examples**:
```bash
# Create an empty file named file.txt
touch file.txt

# Update the timestamp of an existing file
touch file.txt

# Create a file if it does not exist, and do nothing if it exists
touch -c file.txt
```

---

### 10. **`cp`** - Copy Files and Directories

The `cp` command copies files or directories from one location to another.

- **Flags**:
  - `-r`: Recursively copy directories and their contents.
  - `-i`: Interactive mode, ask for confirmation before overwriting files.
  - `-v`: Verbose mode, show the files being copied.
  - `-u`: Copy only if the source file is newer than the destination.

**Examples**:
```bash
# Copy a file from one location to another
cp file.txt /path/to/destination/

# Copy a directory and its contents
cp -r folder1 /path/to/destination/

# Verbosely copy files
cp -v file1.txt file2.txt /path/to/destination/

# Copy only if the source file is newer than the destination
cp -u file1.txt /path/to/destination/
```

---

### 11. **`mv`** - Move or Rename Files and Directories

The `mv` command moves or renames files or directories.

- **Flags**:
  - `-i`: Interactive mode, ask for confirmation before overwriting files.
  - `-v`: Verbose mode, show the files being moved.

**Examples**:
```bash
# Rename a file
mv oldfile.txt newfile.txt

# Move a file to another directory
mv file.txt /path/to/destination/

# Verbosely move files
mv -v file1.txt file2.txt /path/to/destination/
```

---

### 12. **`rm`** - Remove Files or Directories

The `rm` command removes files or directories.

- **Flags**:
  - `-r`: Recursively remove directories and their contents.
  - `-f`: Force removal without prompting for confirmation.
  - `-i`: Interactive mode, ask for confirmation before each file is removed.
  - `-v`: Verbose mode, show files being removed.

**Examples**:
```bash
# Remove a file
rm file.txt

# Remove a directory and its contents
rm -r folder

# Forcefully remove a file without confirmation
rm -f file.txt

# Verbosely remove files
rm -v file1.txt file2.txt
```

---

### 13. **`chmod`** - Change File Permissions

The `chmod` command changes the permissions of a file or directory.

- **Flags**:
  - `-R`: Apply changes recursively to files in a directory.
  - `-v`: Verbose mode, show the permissions being changed.

**Examples**:
```bash
# Change file permissions to 755 (read/write/execute for owner, read/execute for others)
chmod 755 file.txt

# Recursively change permissions of files in a directory
chmod -R 755 folder

# Verbosely change permissions
chmod -v 755 file.txt
```

---

### 14. **`chown`** - Change File Owner

The `chown` command changes the owner of a file or directory.

- **Flags**:
  - `-R`: Apply changes recursively to files in a directory.

**Examples**:
```bash
# Change the owner of a file to 'user' and the group to 'group'
chown user:group file.txt

# Recursively change ownership of files in a directory
chown -R user:group folder
```

---

### 15. **`stat`** - Display Detailed Information About a File

The `stat` command displays detailed information about a file or directory, such as its size, access permissions, and modification times.

**Examples**:
```bash
# Display detailed information about a file
stat file.txt
```

---

### 16. **`ln`** - Create Hard and Symbolic Links

The `ln` command creates links to files or directories.

- **Flags**:
  - `-s`: Create a symbolic link (symlink).
  - `-f`: Force the creation of the link (overwrite existing links).

**Examples**:
```bash
# Create a symbolic link to a file
ln -s /path/to/original /path/to/symlink

# Create a hard link to a file
ln /path/to/original /path/to/hardlink

# Force the creation of a symbolic link
ln -sf /path/to/original /path/to/symlink


```

---

### 17. **`du`** - Disk Usage

The `du` command estimates file space usage.

- **Flags**:
  - `-h`: Human-readable format (e.g., KB, MB, GB).
  - `-s`: Show only the total size of a directory.
  - `-a`: Show the size of all files, not just directories.

**Examples**:
```bash
# Display the size of a file or directory
du -h file.txt

# Display the total size of a directory
du -sh folder

# Show the size of all files in a directory
du -ah folder
```

---
