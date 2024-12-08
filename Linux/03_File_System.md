### File System Mounting:

When working with Linux, **file system mounting** is a way to make storage devices (like USB drives, hard drives, or partitions) accessible to the operating system. This process allows the files and directories on the device to be used just like any other folder in the system.

---

### **What is Mounting?**

**Definition**:  
Mounting is the process of attaching a storage device or partition to a specific location in the directory tree (known as the mount point) so that its contents can be accessed.

**How it works in real life on a computer**:  
When you connect a USB drive or insert an external hard drive, the operating system must "mount" it to give you access. The drive's data becomes available at a specific folder in your Linux file system (e.g., `/media/usb` or `/mnt/disk`).

---

### **What is Unmounting?**

**Definition**:  
Unmounting is the process of safely detaching a storage device or partition from the file system.

**Why it’s important**:  
Unmounting ensures that all ongoing read/write operations on the device are completed before it is disconnected. This prevents data corruption or loss.

---

### **Key Commands for File System Mounting**

#### 1. **`mount`**: Attach a file system to the directory tree.
   - **Syntax**:  
     ```bash
     mount [device] [mount point]
     ```
   - **Example**: Mounting a USB drive located at `/dev/sdb1` to `/mnt/usb`:
     ```bash
     sudo mount /dev/sdb1 /mnt/usb
     ```
     - **Explanation**:
       - `/dev/sdb1`: Represents the device you want to mount.
       - `/mnt/usb`: The folder where the device will be mounted (you can create this folder if it doesn’t exist using `mkdir`).

   - After this command, you can access the USB drive's files under `/mnt/usb`.

---

#### 2. **`umount`**: Detach a mounted file system.
   - **Syntax**:  
     ```bash
     umount [mount point or device]
     ```
   - **Example**: Unmounting the USB drive:
     ```bash
     sudo umount /mnt/usb
     ```
     - **Explanation**: This safely detaches the USB drive so you can remove it without corrupting data.

---

#### 3. **`lsblk`**: List information about block devices (storage drives).
   - **Syntax**:  
     ```bash
     lsblk
     ```
   - **Example**:
     ```bash
     lsblk
     ```
     - **Output**:
       ```
       NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
       sda      8:0    0  500G  0 disk 
       ├─sda1   8:1    0  200G  0 part /
       ├─sda2   8:2    0  100G  0 part /home
       └─sda3   8:3    0  200G  0 part /data
       sdb      8:16   1   16G  0 disk 
       └─sdb1   8:17   1   16G  0 part /mnt/usb
       ```
       - **Explanation**:
         - **NAME**: Device name.
         - **SIZE**: Storage size.
         - **TYPE**: Type of device (disk, partition, etc.).
         - **MOUNTPOINT**: Shows where the device is mounted.

---

#### 4. **`blkid`**: Display information about block devices, including their UUIDs (Unique Identifiers).
   - **Syntax**:  
     ```bash
     blkid [device]
     ```
   - **Example**:
     ```bash
     blkid /dev/sdb1
     ```
     - **Output**:
       ```
       /dev/sdb1: UUID="1234-5678" TYPE="vfat"
       ```
     - **Explanation**:
       - **UUID**: A unique identifier for the partition.
       - **TYPE**: The file system type (e.g., `vfat`, `ext4`).

---

### **How Mounting Works Internally**

When a device is mounted:
1. The operating system reads the file system metadata (like file organization and structure) on the device.
2. It creates a link between the device and the directory (mount point) where its files will appear.
3. You can then access and modify the files as needed.

---

### **Practical Examples**

#### Mounting an External Drive:
1. **Check available drives**:
   ```bash
   lsblk
   ```
   Identify your device name, e.g., `/dev/sdb1`.

2. **Create a mount point**:
   ```bash
   sudo mkdir /mnt/usbdrive
   ```

3. **Mount the drive**:
   ```bash
   sudo mount /dev/sdb1 /mnt/usbdrive
   ```

4. **Verify the mount**:
   ```bash
   ls /mnt/usbdrive
   ```
   This lists the files and directories on the drive.

5. **Unmount when done**:
   ```bash
   sudo umount /mnt/usbdrive
   ```

---

#### Display Block Device Details:
```bash
lsblk
```
- This shows which devices are connected, their sizes, and where they are mounted.

#### Find File System Type and UUID:
```bash
blkid /dev/sdb1
```
- This shows details like the type of file system (e.g., `ext4`, `ntfs`) and its unique identifier.

---

### **Why Mounting is Important**
1. **Access Files**: Without mounting, the operating system cannot read or write data from external drives.
2. **Data Management**: Ensures files on devices are accessible and organized within the Linux directory tree.
3. **Safe Removal**: Unmounting prevents data corruption or loss by safely ending all active processes on the device.

---

### **File System Integrity**
File system integrity means ensuring that the file system on your computer is working correctly and that there is no corruption or damage in its structure. This is important because corruption can make files unreadable, cause data loss, or even crash the system.

---

### **Commands to Check and Repair File Systems**

1. **`fsck` (File System Consistency Check)**
   - **Full Form**: File System Check
   - **Definition**: A command to scan and fix issues in a file system. It checks the consistency and integrity of the file system and repairs problems like lost inodes or bad blocks.
   - **Usage**: Works with different file systems like ext4, FAT, or NFS (via specialized tools like `fsck.fat` or `fsck.nfs`).

   **Basic Syntax**:
   ```bash
   fsck [options] [file_system_or_device]
   ```

   **Example**:
   ```bash
   sudo fsck /dev/sda1
   ```
   - Checks and repairs the file system on partition `/dev/sda1`.

---

2. **`e2fsck` (Ext2/Ext3/Ext4 File System Check)**
   - **Full Form**: Extended File System Check
   - **Definition**: A specialized version of `fsck` for checking and repairing **ext-based** file systems (e.g., ext2, ext3, ext4).
   - **Usage**: Ensures consistency for Linux's native file systems like ext4.

   **Basic Syntax**:
   ```bash
   e2fsck [options] [device]
   ```

   **Example**:
   ```bash
   sudo e2fsck /dev/sda1
   ```
   - Checks the integrity of an ext4 partition on `/dev/sda1`.

---

3. **`fsck.fat`**
   - **Definition**: A specific `fsck` tool for checking and repairing **FAT file systems** (e.g., FAT12, FAT16, FAT32). FAT is commonly used on USB drives, memory cards, and older Windows systems.
   - **Usage**: Ensures the consistency of FAT-formatted drives.

   **Basic Syntax**:
   ```bash
   fsck.fat [options] [device]
   ```

   **Example**:
   ```bash
   sudo fsck.fat /dev/sdb1
   ```
   - Repairs a USB drive with a FAT32 file system.

---

4. **`fsck.nfs`**
   - **Definition**: A tool for verifying and repairing **Network File Systems (NFS)**. NFS is used to access files over a network as if they were on a local system.
   - **Usage**: Checks and resolves inconsistencies for file systems shared over the network.

   **Basic Syntax**:
   ```bash
   fsck.nfs [options] [network_file_system]
   ```

   **Example**:
   ```bash
   sudo fsck.nfs /mnt/nfs_share
   ```
   - Checks the NFS shared directory mounted at `/mnt/nfs_share`.

---

### **Why Are These Commands Used?**

1. **Detect and Fix Corruption**:
   - Disk errors, power failures, or improper shutdowns can corrupt a file system. These commands find and fix such errors.

2. **Prevent Data Loss**:
   - By repairing bad blocks and orphaned files, these tools help protect your data from being permanently lost.

3. **Optimize Performance**:
   - Fixing file system issues ensures the system runs efficiently.

4. **Ensure System Stability**:
   - A corrupted file system can cause crashes. Regular checks keep the system stable.

---

### **Where Are These Commands Used?**

- **`fsck`**:
  - For general-purpose checking and repair of all file systems.

- **`e2fsck`**:
  - Specifically for Linux file systems (ext2, ext3, ext4).

- **`fsck.fat`**:
  - For USB drives, SD cards, or devices formatted with FAT file systems.

- **`fsck.nfs`**:
  - On servers or systems using network-shared file systems.

---

### **Definitions**

1. **FAT (File Allocation Table)**:
   - A simple file system used on USB drives, SD cards, and older Windows systems.
   - Types: FAT12, FAT16, FAT32 (based on size).

2. **NFS (Network File System)**:
   - A protocol that allows files to be accessed over a network as if they were stored locally.

---

### **Practical Example**

1. To check and repair a USB drive formatted with FAT32:
   ```bash
   sudo fsck.fat /dev/sdb1
   ```

2. To check the integrity of a Linux partition with ext4:
   ```bash
   sudo e2fsck /dev/sda1
   ```

3. To check a mounted NFS directory:
   ```bash
   sudo fsck.nfs /mnt/shared_directory
   ```

---

### **Summary**
These commands are essential for ensuring your file systems are healthy, free of errors, and performing optimally. They are used in specific situations depending on the type of file system being checked or repaired. Always run these commands as a superuser (`sudo`) to avoid permission issues.

---
### **File Permissions in Linux**

In Linux, file permissions determine **who** can read, write, or execute a file or directory. These permissions ensure that only authorized users can access or modify files, protecting the system from accidental or malicious actions.

---

### **Key Concepts of File Permissions**

1. **Permission Types**:
   - **Read (r)**: Allows viewing the content of a file.
   - **Write (w)**: Allows modifying or deleting the file.
   - **Execute (x)**: Allows running the file (for scripts/programs) or accessing a directory.

2. **Permission Groups**:
   - **Owner (u)**: The user who owns the file.
   - **Group (g)**: The group that the file belongs to.
   - **Others (o)**: All other users on the system.

3. **Permission Format**:
   - Represented as `rwx` for each group (Owner, Group, Others).
   - Example:  
     ```
     -rwxr-xr-- 1 user group 1024 Nov 23 file.txt
     ```
     - **Owner**: `rwx` (Read, Write, Execute).
     - **Group**: `r-x` (Read, Execute).
     - **Others**: `r--` (Read only).

---

### **Commands to Manage File Permissions**

#### **1. `chmod` (Change Mode)**

**Definition**:  
`chmod` is used to change the permissions of a file or directory.

**Syntax**:  
```bash
chmod [options] [permissions] [file/directory]
```

**Examples**:
- Make a file readable, writable, and executable by the owner only:
  ```bash
  chmod 700 file.txt
  ```
  - `7`: Owner can read, write, and execute (`rwx`).
  - `0`: No permissions for group and others.

- Add execute permission for the group:
  ```bash
  chmod g+x file.txt
  ```

- Remove write permission for others:
  ```bash
  chmod o-w file.txt
  ```

---

#### **2. `chown` (Change Ownership)**

**Definition**:  
`chown` is used to change the owner and/or group of a file or directory.

**Syntax**:  
```bash
chown [owner][:group] [file/directory]
```

**Examples**:
- Change the owner of a file:
  ```bash
  sudo chown user1 file.txt
  ```

- Change both owner and group:
  ```bash
  sudo chown user1:group1 file.txt
  ```

- Change ownership recursively for a directory and its contents:
  ```bash
  sudo chown -R user1:group1 /path/to/directory
  ```

---

#### **3. `umask` (Set Default Permissions)**

**Definition**:  
`umask` defines the default permissions for newly created files and directories by specifying what permissions should be **removed**.

**Syntax**:  
```bash
umask [permissions]
```

**Default Calculation**:
- Subtract the `umask` value from the default permissions:
  - Default permissions for files: `666` (read and write for all).
  - Default permissions for directories: `777` (read, write, and execute for all).

**Examples**:
- Set `umask` to remove write permission for group and others:
  ```bash
  umask 022
  ```
  - Resulting permissions for a new file: `644` (Owner: rw-, Group: r--, Others: r--).

- Check the current `umask` value:
  ```bash
  umask
  ```

---

### **Practical Examples**

#### Example 1: Protecting a File
If you want only the file owner to read, write, and execute, but no one else:
```bash
chmod 700 secret.txt
```
- Only the owner can access the file.

---

#### Example 2: Sharing a File with a Group
If you want the owner and a group to have full access to a file:
```bash
chmod 770 shared.txt
chown user1:group1 shared.txt
```
- Owner and group members can read, write, and execute the file.

---

#### Example 3: Setting Default Permissions
If you want all new files to be readable and writable only by the owner:
```bash
umask 077
```
- Resulting permissions: `600` for files and `700` for directories.

---

### **Why File Permissions Are Important**
1. **Security**: Prevent unauthorized access to sensitive files.
2. **Collaboration**: Share files with specific users or groups.
3. **System Stability**: Avoid accidental modifications or deletions.

