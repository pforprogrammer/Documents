

### 1. **`ls` (List Files and Directories)**
This command shows you what’s inside a folder (directory).

#### Basic Command:
```bash
ls
```

#### Example:
Let’s say you’re in a folder with files called **"homework.txt"**, **"games"** (a folder), and **"notes.pdf"**.
```bash
ls
```
Output:
```
homework.txt  games  notes.pdf
```

#### Flags (Options):
- **`-l`**: Shows a detailed list (long format) with file permissions, sizes, and dates.
- **`-a`**: Shows **all** files, including hidden ones (files that start with a dot `.`).

#### Real Example:
```bash
ls -la
```
Output:
```
drwxr-xr-x  2 user user 4096 Nov 12 08:00 games
-rw-r--r--  1 user user  256 Nov 12 08:00 homework.txt
-rw-r--r--  1 user user 1024 Nov 12 08:00 notes.pdf
```

---

### 2. **`pwd` (Print Working Directory)**
This command tells you **where you are** in the folder structure (like your current address).

#### Basic Command:
```bash
pwd
```

#### Example:
If you’re in a folder called **"/home/user/Documents"**, typing `pwd` will show you:
```bash
/home/user/Documents
```
This tells you that you're in the "Documents" folder.

---

### 3. **`cd` (Change Directory)**
This command lets you **move** from one folder to another.

#### Basic Command:
```bash
cd folder_name
```

#### Example:
Let’s say you’re in **"/home/user"** and you want to go to your **Documents** folder:
```bash
cd Documents
```
Now you’re inside **"/home/user/Documents"**.

#### Flags (Options):
- **`cd ..`**: Move **up** one level (back to the parent directory).
- **`cd ~`**: Go to your **home** folder (usually **/home/username**).

#### Real Example:
```bash
cd ..
```
This takes you one folder up.

---

### 4. **`mkdir` (Make Directory)**
This command creates a new folder.

#### Basic Command:
```bash
mkdir folder_name
```

#### Example:
If you want to create a folder called **"school"**:
```bash
mkdir school
```
Now you have a new folder called **"school"**.

#### Flags (Options):
- **`-p`**: Creates parent directories if they don’t exist.

#### Real Example:
```bash
mkdir -p projects/2024/school
```
This creates the folder **"projects"**, inside it a folder **"2024"**, and inside that, a folder called **"school"** all in one command!

---

### 5. **`touch` (Create an Empty File)**
This command makes an **empty file** (like a blank piece of paper).

#### Basic Command:
```bash
touch file_name
```

#### Example:
If you want to create an empty file called **"notes.txt"**:
```bash
touch notes.txt
```
Now you have an empty file named **"notes.txt"**.

#### Flags (Options):
- **`touch -a`**: Change only the file’s **access time** (when it was last opened).
- **`touch -m`**: Change only the file’s **modification time** (when it was last changed).

---

### 6. **`cp` (Copy Files and Directories)**
This command copies files or folders from one place to another.

#### Basic Command:
```bash
cp source destination
```

#### Example:
If you want to copy **"homework.txt"** to a folder called **"backup"**:
```bash
cp homework.txt backup/
```
Now, there will be a copy of **"homework.txt"** inside the **backup** folder.

#### Flags (Options):
- **`-r`**: Copy a directory **recursively** (which means it copies everything inside the folder too).
- **`-i`**: Asks for confirmation before overwriting any files.
- **`-v`**: Verbose mode (shows what’s happening during the copy).

#### Real Example:
```bash
cp -rv games backup/
```
This copies the **games** folder and everything inside it to the **backup** folder and shows the process as it happens.

---

### 7. **`mv` (Move or Rename Files and Directories)**
This command moves or renames files or folders.

#### Basic Command:
```bash
mv source destination
```

#### Example 1 (Move):
If you want to move **"notes.txt"** into the **Documents** folder:
```bash
mv notes.txt Documents/
```
Now **"notes.txt"** is inside the **Documents** folder.

#### Example 2 (Rename):
If you want to rename **"notes.txt"** to **"classnotes.txt"**:
```bash
mv notes.txt classnotes.txt
```
Now the file is called **"classnotes.txt"**.

#### Flags (Options):
- **`-i`**: Asks for confirmation before overwriting.
- **`-v`**: Shows what’s happening during the move.

---

### 8. **`rm` (Remove Files and Directories)**
This command deletes files or folders (be careful with this one!).

#### Basic Command:
```bash
rm file_name
```

#### Example:
If you want to delete **"oldnotes.txt"**:
```bash
rm oldnotes.txt
```
Now the file is deleted.

#### Flags (Options):
- **`-r`**: Remove directories **recursively** (deletes the folder and everything inside it).
- **`-i`**: Asks for confirmation before deleting.
- **`-f`**: Forces deletion without asking (dangerous!).
  
#### Real Example:
```bash
rm -r backup/
```
This deletes the **backup** folder and everything inside it.

---

### 9. **`cat` (Display File Contents)**
This command shows the contents of a file.

#### Basic Command:
```bash
cat file_name
```

#### Example:
If you want to see what’s inside **"homework.txt"**:
```bash
cat homework.txt
```
This shows the text written in **"homework.txt"**.

#### Flags (Options):
- **`-n`**: Shows line numbers in the file.

---

### 10. **`nano` (Edit Files)**
This command opens a file for editing directly in the terminal.

#### Basic Command:
```bash
nano file_name
```

#### Example:
If you want to edit **"homework.txt"**, type:
```bash
nano homework.txt
```
This opens the file, and you can start typing or editing right away. Use **CTRL + X** to exit and **Y** to save changes.

---

# Assignmet # 1

Sure! Here's your **assignment** with clear tasks to practice the file commands in Ubuntu:

---

### **Linux File Commands Assignment**

1. **Listing Files and Directories**
   - Use the `ls` command to list all the files and folders in your home directory.
   - Use the `ls -la` command to list all files (including hidden files) with details.

2. **Navigating Directories**
   - Find your current directory using the `pwd` command.
   - Change into the **Documents** folder using the `cd` command.
   - Go back to the home directory using `cd ..`.
   - Go directly to your home directory using `cd ~`.

3. **Creating Directories and Files**
   - Create a folder named **"practice"** in your home directory using `mkdir`.
   - Inside the **practice** folder, create two more folders named **"school"** and **"fun"**.
   - Create an empty file called **"homework.txt"** inside the **school** folder using `touch`.
   - Create an empty file called **"games.txt"** inside the **fun** folder.

4. **Copying and Moving Files**
   - Copy **homework.txt** from the **school** folder to the **fun** folder using the `cp` command.
   - Move **games.txt** from the **fun** folder to the **school** folder using the `mv` command.
   - Rename **homework.txt** to **assignments.txt** using the `mv` command.

5. **Deleting Files and Directories**
   - Delete the **games.txt** file from the **school** folder using the `rm` command.
   - Remove the entire **fun** folder and its contents using `rm -r`.

6. **Viewing File Contents**
   - Open and view the contents of **assignments.txt** using the `cat` command.
   - Edit **assignments.txt** using the `nano` command. Write some text in the file, save, and exit.

---

This assignment covers all the commands we discussed. Practice each task one by one in your terminal, and you’ll master these basic Linux file commands! Let me know if you need help with any step. 😊

---

## **Remaining Linux commands** 
---

### 11. **`head` (View the Beginning of a File)**
This command shows the first few lines of a file.

#### Basic Command:
```bash
head file_name
```

#### Example:
If you want to see the first 10 lines of **"notes.txt"**:
```bash
head notes.txt
```

#### Flags (Options):
- **`-n`**: Specify the number of lines to display.
  ```bash
  head -n 5 notes.txt
  ```
  This shows the first 5 lines.

---

### 12. **`tail` (View the End of a File)**
This command shows the last few lines of a file.

#### Basic Command:
```bash
tail file_name
```

#### Example:
If you want to see the last 10 lines of **"notes.txt"**:
```bash
tail notes.txt
```

#### Flags (Options):
- **`-n`**: Specify the number of lines to display.
  ```bash
  tail -n 5 notes.txt
  ```
  This shows the last 5 lines.

---

### 13. **`find` (Search for Files and Directories)**
This command searches for files or folders based on their name or type.

#### Basic Command:
```bash
find /path -name file_name
```

#### Example:
If you want to find a file named **"homework.txt"** in the **Documents** folder:
```bash
find ~/Documents -name homework.txt
```

#### Flags (Options):
- **`-type d`**: Find directories.
- **`-type f`**: Find files.

---

### 14. **`grep` (Search for Text in Files)**
This command finds specific text inside a file.

#### Basic Command:
```bash
grep "text_to_find" file_name
```

#### Example:
If you want to find the word **"math"** in **"homework.txt"**:
```bash
grep "math" homework.txt
```
This shows all lines containing the word **"math"**.

#### Flags (Options):
- **`-i`**: Case-insensitive search.
- **`-n`**: Show line numbers.
  ```bash
  grep -n "math" homework.txt
  ```

---

### 15. **`chmod` (Change File Permissions)**
This command changes who can read, write, or execute a file.

#### Basic Command:
```bash
chmod permissions file_name
```

#### Example:
To give everyone permission to execute **"script.sh"**:
```bash
chmod +x script.sh
```

#### Real Example:
- **`chmod 777 file_name`**: Give all permissions (read, write, execute) to everyone.
- **`chmod 644 file_name`**: Allow only the owner to write; others can read.

---

### 16. **`chown` (Change File Ownership)**
This command changes who owns a file.

#### Basic Command:
```bash
chown new_owner file_name
```

#### Example:
If you want to make **user1** the owner of **"notes.txt"**:
```bash
chown user1 notes.txt
```

#### Real Example:
```bash
chown user1:user1 notes.txt
```
This sets both the owner and group to **user1**.

---

### 17. **`df` (Disk Usage Info)**
This command shows how much space is available on your disks.

#### Basic Command:
```bash
df
```

#### Example:
To see the disk space in human-readable format:
```bash
df -h
```

#### Flags (Options):
- **`-h`**: Show sizes in MB/GB instead of bytes.

---

### 18. **`du` (Directory Usage Info)**
This command shows how much space a folder or file is using.

#### Basic Command:
```bash
du folder_name
```

#### Example:
To see how much space the **Documents** folder is using:
```bash
du -h ~/Documents
```

---

### 19. **`top` (Task Manager for Linux)**
This command shows a live view of running processes, like Task Manager.

#### Basic Command:
```bash
top
```

#### Example:
Use **CTRL + C** to exit the **top** command.

---

### 20. **`ps` (Process Status)**
This command shows the processes running on your system.

#### Basic Command:
```bash
ps
```

#### Example:
To see detailed information about all processes:
```bash
ps -aux
```

---

These commands will make you more comfortable working with Linux. If you want to dive deeper into any of these or learn other commands, let me know! 😊

---

## **Assignment # 2**

---

### **Task 1: Viewing File Content**

1. **Using `head`:**  
   - Create a file named **sample.txt** and add the following lines:  
     ```
     Line 1: Welcome to Linux.
     Line 2: This is a test file.
     Line 3: Practice makes perfect.
     Line 4: Keep learning new commands.
     Line 5: Stay consistent!
     ```
     - Command to create the file:  
       ```bash
       echo -e "Line 1: Welcome to Linux.\nLine 2: This is a test file.\nLine 3: Practice makes perfect.\nLine 4: Keep learning new commands.\nLine 5: Stay consistent!" > sample.txt
       ```
   - Display the first 3 lines using `head`.  
     Command: `head -n 3 sample.txt`

2. **Using `tail`:**  
   - Show the last 2 lines of **sample.txt**.  
     Command: `tail -n 2 sample.txt`

---

### **Task 2: Searching Files and Text**

1. **Using `find`:**  
   - Create two directories: **project1** and **project2** in your home directory.  
     Command: `mkdir project1 project2`  
   - Inside **project1**, create a file named **report.txt**.  
     Command: `touch project1/report.txt`  
   - Use `find` to locate **report.txt** starting from your home directory.  
     Command: `find ~/ -name report.txt`

2. **Using `grep`:**  
   - Add the text **"The quick brown fox jumps over the lazy dog"** to **report.txt**.  
     Command: `echo "The quick brown fox jumps over the lazy dog" > project1/report.txt`  
   - Search for the word **"fox"** in **report.txt**.  
     Command: `grep "fox" project1/report.txt`  
   - Perform a case-insensitive search for **"FOX"**.  
     Command: `grep -i "FOX" project1/report.txt`

---

### **Task 3: Managing Permissions**

1. **Using `chmod`:**  
   - Create a script file named **script.sh** with the content:  
     ```bash
     #!/bin/bash
     echo "Hello, Linux!"
     ```  
     Command: `echo -e "#!/bin/bash\necho \"Hello, Linux!\"" > script.sh`  
   - Grant execute permission to the script.  
     Command: `chmod +x script.sh`  
   - Run the script.  
     Command: `./script.sh`

2. **Using `chown`:**  
   - Check the current ownership of **script.sh**.  
     Command: `ls -l script.sh`  
   - Change the owner of **script.sh** to your username (if not already owned by you).  
     Command: `chown your_username script.sh`

---

### **Task 4: Monitoring System Usage**

1. **Disk and Directory Usage:**  
   - Display your disk space usage in human-readable format using `df`.  
     Command: `df -h`  
   - Check the size of your **project1** directory using `du`.  
     Command: `du -h project1`

2. **View Running Processes:**  
   - Use the `top` command to monitor system processes. Observe for 10 seconds and then exit using **CTRL + C**.  
   - List all processes running on your system using `ps`.  
     Command: `ps -aux`

---

### **Task 5: Summarize Your Work**

1. **Create a Summary File:**  
   - Write a summary of what you learned and the commands you executed in a file named **assignment_summary.txt**.  
     Command: `nano assignment_summary.txt`  
   - Include:  
     - Key commands used.  
     - Any errors faced and how you resolved them.  

2. **Zip Your Work:**  
   - Compress the **project1**, **project2**, and **script.sh** into a zip file named **linux_assignment.zip**.  
     Command: `zip -r linux_assignment.zip project1 project2 script.sh`

---

### **Submission Guidelines:**

- Submit the **linux_assignment.zip** file.  
- Include screenshots of terminal outputs for each task in a folder named **screenshots**.

---

### **Assessment Criteria:**

- Accuracy of commands and outputs.  
- Proper use of file permissions and ownership commands.  
- Completeness of the summary file.  

---

### **Note:**  
If you encounter issues, document them in **assignment_summary.txt** and seek guidance! 😊
