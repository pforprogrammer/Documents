### **Remaining Topics/commands**
---
## **1. chmod Calculator (Permissions Calculator)**
The `chmod` command is used to change file or directory permissions in Linux. Permissions are represented in octal (numbers) or symbolic (letters) format.

### **Groups for Permissions**
- **Owner**: The person who owns the file.
- **Group**: Users in the same group as the file.
- **Others (Public)**: Everyone else.

### **Permission Types**
- **`r`** (Read): View file contents.
- **`w`** (Write): Modify file contents.
- **`x`** (Execute): Run the file as a program.

### **Octal Values**
| Permission | Binary | Octal |
|------------|--------|-------|
| `---`      | `000`  | `0`   |
| `--x`      | `001`  | `1`   |
| `-w-`      | `010`  | `2`   |
| `-wx`      | `011`  | `3`   |
| `r--`      | `100`  | `4`   |
| `r-x`      | `101`  | `5`   |
| `rw-`      | `110`  | `6`   |
| `rwx`      | `111`  | `7`   |

### **Examples**
- **`chmod 644 file.txt`**: Gives **read-write** to the owner and **read-only** to others.
- **`chmod 755 script.sh`**: Gives **read-write-execute** to the owner and **read-execute** to others.

Use online chmod calculators to compute octal values easily.

---

## **2. Creating and Displaying Hidden Files**
- A file is considered **hidden** if its name starts with a dot (`.`).
  
### **Create a Hidden File**
```bash
touch .hiddenfile
```

### **List Hidden Files**
```bash
ls -a
```
The `-a` flag lists all files, including hidden ones.

---

## **3. Difference Between `sudo` and `sudo su`**
- **`sudo`**: Runs a single command as the root user. For example:
  ```bash
  sudo apt update
  ```
- **`sudo su`**: Switches to the root user shell (a complete session as root). Example:
  ```bash
  sudo su
  ```
  To exit root shell, type:
  ```bash
  exit
  ```

---

## **4. All About Vim**
Vim is a text editor.

### **Commands in Vim**
1. **Open a File**:
   ```bash
   vim filename
   ```
2. **Insert Mode** (to write text):
   - Press **`i`** to enter **insert mode**.
3. **Save and Exit**:
   - Press **`ESC`**, then type **`:wq`** and press **Enter**.
4. **Exit Without Saving**:
   - Press **`ESC`**, then type **`:q!`** and press **Enter**.

---

## **5. Checking Processes**
A process is any running program.

### **Commands to Check Processes**
1. **`ps`**: Shows running processes.
   ```bash
   ps
   ```
2. **`ps -aux`**: Displays all processes with detailed info.
   ```bash
   ps -aux
   ```
3. **`ps -ef`**: Shows processes in full format.
   ```bash
   ps -ef
   ```

### **All Flags for `ps`**
- **`-a`**: Show processes of all users.
- **`-u`**: Display user-related info.
- **`-x`**: Show processes without a controlling terminal.
- **`-f`**: Full format listing.

---

## **6. Using `top`**
Displays real-time system processes.

### **Command**
```bash
top
```
- Press **`q`** to exit.

---

## **7. Process ID**
Every process has a unique Process ID (PID).

### **Find a Process by Name**
```bash
ps -aux | grep process_name
```

---

## **8. Kill a Process**
### **Command**
```bash
kill PID
```
Replace `PID` with the process ID.

### **Force Kill**
```bash
kill -9 PID
```
# **File System Architecture**
---
## **File System Overview**
### Definitions :
1. **Boot Block**: A small part of the file system that contains the instructions for starting (booting) the operating system.
2. **Superblock**: The part of the file system that stores key information about the file system, like size, structure, and available space.
3. **Inode Block**: A data structure that holds metadata (information) about files, like their size, permissions, and location.
4. **Data Block**: The actual space on the disk where the contents of the files are stored.

---

---
**Analogy** Let’s imagine the UNIX file system is like a **giant library** where books are stored neatly so everyone can find them. Each part of the file system has a special job, just like different sections of the library. Let’s understand the **key components** step by step:

---

### 1. **Boot Block** - The Library’s Entrance
- **What it is**: The boot block is like the **front door of the library**. It’s the first thing you see when you want to enter.
- **What it does**: When the computer starts, the boot block tells it how to get inside the library (file system) and start finding things.
- **Analogy**: Imagine you’re a librarian, and the boot block is the map at the entrance that shows you where to go to start organizing the books.

---

### 2. **Superblock** - The Library's Master Plan
- **What it is**: The superblock is like the **library's rule book and inventory list**. It knows everything about how the library is set up.
- **What it does**: It keeps track of how many books (files) are in the library, how many shelves (blocks) are available, and where the important sections are.
- **Analogy**: Think of it as a library catalog system that helps you know if the fiction section has enough space left for new books.

---

### 3. **Inode Block** - The Labels on the Books
- **What it is**: An inode is like a **label on a book** that tells you all about it.
- **What it does**: The inode stores information about the file, like:
  - What’s the book’s title? (File name)
  - Where is it on the shelf? (File location)
  - Who is allowed to read or write it? (Permissions)
  - How many copies are there? (Links)
- **Analogy**: Every book (file) has a tag that says where to find it and who can read it.

---

### 4. **Data Blocks** - The Actual Books
- **What it is**: The data blocks are like the **actual books in the library**.
- **What it does**: This is where all the real content (text, images, videos) is stored. If a file is a story, the data block contains the story’s words.
- **Analogy**: Imagine rows of shelves with books. The data blocks are the books themselves, while the inode block is just the label describing each book.

---

### How It All Works Together:
1. The **boot block** starts everything and gives the library the go-ahead to open.
2. The **superblock** is like the head librarian who knows the rules and layout of the library.
3. The **inode block** helps find and describe each book (file).
4. The **data blocks** hold the actual books (files) that people come to the library to read.

---

### Example:
Let’s say you want to open a file (read a book):
1. The **boot block** says, "We’re open for business."
2. The **superblock** tells you where to look.
3. The **inode block** gives you the details of the book you want.
4. The **data block** hands you the actual book to read.

