 
## Filesystem Hierarchy 

1. **Root Directory (`/`)**: The base of the filesystem hierarchy.

2. **Binary Executables (`/bin`)**: Essential user binaries (e.g., `ls`, `cp`) necessary for basic system operations.

3. **Bootloader Files (`/boot`)**: Contains boot loader files and kernel images.

4. **Device Files (`/dev`)**: Special files representing system devices.

5. **System Configuration (`/etc`)**: Central repository for system-wide configuration files.

6. **User Home Directories (`/home`)**: Personal storage space for user files and settings.

7. **System Libraries (`/lib`)**: Essential shared libraries and kernel modules.

8. **Removable Media (`/media`)**: Mount point for removable storage devices.

9. **Temporary Mount Points (`/mnt`)**: Used for mounting filesystems temporarily.

10. **Optional Packages (`/opt`)**: Additional application software packages.

11. **Process Information (`/proc`)**: Virtual filesystem providing process and system information.

12. **Root Home Directory (`/root`)**: Home directory for the root user.

13. **Runtime Data (`/run`)**: Information about the system since last boot, like currently logged-in users.

14. **System Binaries (`/sbin`)**: Essential system administration binaries.

15. **Service Data (`/srv`)**: Data for services provided by the system.

16. **Temporary Files (`/tmp`)**: Temporary files often cleared on reboot.

17. **User Installed Software (`/usr`)**: Secondary hierarchy for user-installed software and utilities, includes `/usr/bin`, `/usr/local`, etc.

18. **Variable Data (`/var`)**: Variable files such as logs, spool files, and temporary e-mail files.

This concise summary captures the essential purpose and contents of key directories within the Filesystem Hierarchy Standard (FHS), providing a structured overview of a Unix-like system's directory layout.

## Filesystem Concepts and Types

1. **Virtual File System (VFS)**
   - Acts as an abstraction layer between applications and various filesystem types.
   - Ensures compatibility across different filesystems, allowing applications to operate uniformly.

2. **Journaling in Filesystems**
   - Protects against data corruption during unexpected shutdowns by logging changes before they're made.
   - A journaled filesystem maintains consistency and can recover quickly, reducing boot times after a crash.

3. **Common Desktop Filesystem Types**
   - **ext4**: Latest Linux filesystem, backward compatible with ext2 and ext3. Supports up to 1 exabyte volumes and 16 terabytes file sizes.
   - **Btrfs** (Better FS): Offers snapshots, incremental backups, and performance enhancements. Available but considered less stable.
   - **XFS**: High-performance journaling filesystem, suitable for large files (e.g., media servers).
   - **NTFS and FAT**: Primarily Windows filesystems.
   - **HFS+**: Used by Macintosh systems.

4. **Checking Filesystems on Linux**
   - Use `df -T` to view filesystem types and disk space usage.
     - Example output shows filesystem type (e.g., ext4, xfs), size, used space, available space, and mount points.

These notes summarize key filesystem concepts, the role of journaling for data integrity, common types of filesystems used in desktop environments, and how to check filesystem details on Linux.

## Anatomy of a Disk

1. **Partitioning Overview**
   - Hard disks can be divided into partitions (/dev/sda1, /dev/sda2), with /dev/sda representing the entire disk.
   - Partitions enhance data organization and allow for multiple filesystems on a single disk.

2. **Partition Table**
   - Defines disk partitioning, including start/end points, bootable partitions, and sector allocation.
   - Two main types: Master Boot Record (MBR) and GUID Partition Table (GPT).

3. **Partition Types**
   - **MBR**: Supports up to 4 primary partitions; additional partitions require an extended partition containing logical partitions. Limited to 2TB disk size.
   - **GPT**: Modern standard supporting numerous partitions with unique IDs. Commonly used with UEFI systems.

4. **Filesystem Structure**
   - **Boot Block**: Initial sectors containing boot information. Only one active boot block is needed.
   - **Super Block**: Follows the boot block; contains critical filesystem information like inode table size and filesystem size.
   - **Inode Table**: Manages files/directories, with each entry holding detailed file information.
   - **Data Blocks**: Contain the actual data for files and directories.

5. **Example of Partition Tables**
   - **MBR Example**:
     - Shows primary, extended, and logical partitions (e.g., ext4 primary partition, linux-swap, and xfs logical partitions).
 ```
 pete@icebox:~$ sudo parted -l
  
Model: Seagate (scsi)
  
Disk /dev/sda: 21.5GB
  
Sector size (logical/physical): 512B/512B
  
Partition Table: msdos

Number  Start   End     Size    Type      File system     Flags
  
 1      1049kB  6860MB  6859MB  primary   ext4            boot
  
 2      6861MB  21.5GB  14.6GB  extended
  
 5      6861MB  7380MB  519MB   logical   linux-swap(v1)
  
 6      7381MB  21.5GB  14.1GB  logical   xfs
 ```
 
   * **GPT Example**:
     - Partitions identified by unique IDs without the primary/extended/logical distinction (e.g., partitions named "first" and "second").
 ```
   
Model: Thumb Drive (scsi)
  
Disk /dev/sdb: 4041MB
  
Sector size (logical/physical): 512B/512B
  
Partition Table: gpt

Number  Start   End     Size     File system  Name        Flags
  
 1      17.4kB  1000MB  1000MB                first
  
 2      1000MB  4040MB  3040MB                second
```

This summary outlines the key components and concepts related to disk anatomy, partitioning schemes, and the structure of filesystems, providing a foundational understanding of how data is organized at the hardware level.

## Disk Partitioning

1. **Partitioning Tools**:
    
    - `fdisk`: Command-line tool for MBR partitioning; does not support GPT.
    - `parted`: Supports both MBR and GPT partitioning, usable via command line.
    - `gparted`: GUI version of `parted`, supporting both MBR and GPT.
    - `gdisk`: Similar to `fdisk` but supports GPT only.
    
2. **Using Parted for Partitioning**:
    
    - Start `parted` with `$ sudo parted`.
    - Select the device by running `select /dev/sdb2` within `parted`.
    
3. **Viewing Current Partitions**:
    
    - Use `print` command in `parted` to display the disk's partition table and existing partitions.
    
4. **Creating a Partition**:
    
    - Use `mkpart primary <start> <end>` to create a new primary partition between specified start and end points (in MB).
    
5. **Resizing a Partition**:
    
    - To resize, use `resize <partition number> <new start> <new end>` specifying the new range.
    
6. **Key Points**:
    - Partitions are created in unallocated space without overlapping existing partitions.
    - MBR allows up to four primary partitions; GPT does not have this limitation.
    - Care is needed to avoid data loss; `parted` is powerful and changes are immediate.

## Creating Filesystems

1. **Creating a Filesystem**:
    
    - Use the `mkfs` command to create a filesystem on a disk partition.
    - Example: `$ sudo mkfs -t ext4 /dev/sdb2` creates an ext4 filesystem on the `/dev/sdb2` partition.
2. **Usage Considerations**:
    
    - Appropriate for newly partitioned disks or when repartitioning.
    - Avoid creating a filesystem on a partition with existing data to prevent corruption.

## Mounting and Unmounting Filesystems

1. **Mounting a Filesystem**
    
    - Create a mount point: `mkdir /mydrive`.
    - Mount command: `sudo mount -t ext4 /dev/sdb2 /mydrive`.
        - `-t ext4` specifies the filesystem type.
        - `/dev/sdb2` is the device location.
        - `/mydrive` is the mount point directory.
2. **Unmounting a Filesystem**
    
    - Commands:
        - `sudo umount /mydrive`
        - Or: `sudo umount /dev/sdb2`
3. **Device Naming by Kernel**
    
    - Kernel assigns device names in the order it detects them, which can change.
4. **Using UUID for Mounting**
    
    - View UUIDs: `sudo blkid` shows UUIDs and filesystem types for devices.
    - Mount using UUID: `sudo mount UUID=130b882f-7d79-436d-a096-1e594c92bb76 /mydrive`.
    - Benefits: Ensures the correct device is mounted even if device names change.
5. **Advantages of UUIDs**
    
    - UUIDs are preferred for persistent or automatic mounts (e.g., in `/etc/fstab`) to ensure reliability across reboots or hardware changes.

## /etc/fstab

1. **Purpose of /etc/fstab**
    
    - The `/etc/fstab` file (filesystem table) contains a permanent list of filesystems and their mount options to be automatically mounted at system startup.
2. **Structure of an /etc/fstab Entry**
    
    - **UUID**: Universally Unique Identifier for the device.
    - **Mount Point**: Directory where the filesystem will be mounted.
    - **Filesystem Type**: Type of filesystem (e.g., ext4, xfs, swap).
    - **Options**: Mount options (e.g., `relatime`, `errors=remount-ro`).
    - **Dump**: Backup utility flag (usually set to 0).
    - **Pass**: Order for filesystem checks at boot (`fsck`); 0 disables checks.
3. **Modifying /etc/fstab**
    
    - To add a filesystem, directly edit `/etc/fstab` using the syntax above.
    - Caution is advised to avoid errors that could affect system startup.
4. **Example Entry**
    
    - For root (`/`): `UUID=130b882f-7d79-436d-a096-1e594c92bb76 / ext4 relatime,errors=remount-ro 0 1`
    - For `/home`: `UUID=78d203a0-7c18-49bd-9e07-54f44cdb5726 /home xfs relatime 0 2`
    - For swap: `UUID=22c3d34b-467e-467c-b44d-f03803c2c526 none swap sw 0 0`

## Swap

1. **Purpose of Swap**
    
    - Swap acts as virtual memory, allowing the system to use disk space for managing memory content from idle processes when RAM is low.
2. **Swap Partition Example**
    
    - A partition can be designated for swap, e.g., `/dev/sdb2` used as swap space shown in the partition table.
3. **Setting Up Swap Space**
    
    - **Initialization**: Use `mkswap /dev/sdb2` to set up the swap area on the partition.
    - **Activation**: Enable the swap space with `swapon /dev/sdb2`.
4. **Persisting Swap Usage**
    
    - To have swap available on system boot, add an entry to `/etc/fstab` with `sw` as the filesystem type.
5. **Disabling Swap**
    
    - Use `swapoff /dev/sdb2` to disable swapping on the specified partition.
6. **Swap Size Recommendation**
    
    - Historically, the recommendation was to allocate twice as much swap space as physical RAM. However, with modern systems having ample RAM, the required swap size may vary based on actual system usage and performance needs.

## Disk Usage

1. `df` command: 
  - Shows utilization of currently mounted filesystems.
  - Usage: `df -h` for human-readable format.
  - Displays device, used space, available space, and usage percentage.
  - Example output:
    ```
    Filesystem     1K-blocks    Used Available Use% Mounted on
    /dev/sda1       6.2G        2.3G  3.6G      40%  /
    ```
2. `du` command:
  - Shows disk usage of the current directory.
  - Usage: `du -h` for human-readable format.
  - Can be used to check disk usage of specific directories.
  - Example usage: `du -h /` to check root directory (may be cluttered).
3. Differentiate:
  - To check free disk space: Use `df`.
  - To check disk usage of files/directories: Use `du`.

## Filesystem Repair (fsck)

1. **Purpose of fsck**
    
    - `fsck` (filesystem check) is used to check the consistency of a filesystem and attempt repairs if needed.
2. **Automatic Execution**
    
    - Typically runs during system boot to ensure filesystem integrity before mounting disks.
3. **Manual Execution**
    
    - If needed, `fsck` can be manually invoked, especially in cases of filesystem corruption or unexpected shutdowns.
4. **Precautions**
    
    - It's recommended to run `fsck` from a rescue disk or when the filesystem is not mounted to avoid data corruption.
5. **Command Syntax**
    
    - Use `sudo fsck /dev/sda` to check and repair the filesystem on device `/dev/sda`.
6. **System Recovery**
    
    - Running `fsck` helps in bringing the filesystem back to a working state after errors or corruption, reducing data loss risk.

## Inode Overview

- **Definition**: An inode (index node) is a data structure in a Unix-based filesystem that stores information about a file except its name and actual data.
- **Contents**: It includes file type, owner, group, access permissions, timestamps (mtime, ctime, atime), number of hardlinks, file size, number of blocks allocated, and pointers to data blocks.

#### 1. Creation and Allocation

- **When Created**: Inodes are allocated when a filesystem is created, based on algorithms predicting inode space requirements.
- **Capacity Issues**: Similar to disk space, it's possible to run out of inodes, preventing new file creation.
- **Checking Inodes**: Use `df -i` to check available inodes.

#### 2. Inode Identification and Information

- **Identification**: Inodes are identified by numbers assigned in sequential order, reusable after deletion.
- **Commands**: 
  - `ls -li` displays inode numbers alongside files.
  - `stat` provides detailed inode information, including file size, owner, timestamps, and more.

#### 3. Function and Structure

- **Locating Files**: Inodes contain pointers to the data blocks of files, facilitating file location on the disk.
- **Structure**: Typically, an inode has 15 pointers; the first 12 are direct pointers to data blocks, and the remaining three point to blocks that contain more pointers, supporting files of various sizes efficiently.

## Symlinks Overview

#### 1. Symlinks

- **Description**: Symlinks (symbolic links) in Linux work like shortcuts in Windows, pointing to another file by filename. They don't link directly to an inode but to the file's name, allowing them to reference files across different filesystems.

#### 2. Creating Symlinks

- **How-To**: Use the command `ln -s myfile myfilelink` to create a symlink named `myfilelink` pointing to `myfile`. Symlinks have unique inode numbers and can reference files across different filesystems using filenames.

#### 3. Hardlinks

- **Definition**: Hardlinks link directly to the inode of a file, essentially creating another access point to the same data. They share the inode number, so changes to the file reflect across all hardlinks.
- **Limitation**: Hardlinks cannot span across filesystems due to the uniqueness of inodes within each filesystem.

#### 4. Creating Hardlinks

- **Procedure**: Execute `ln myfile2 myhardlink` to create a hardlink named `myhardlink` for `myfile2`. This action makes `myhardlink` another entry point to the same data as `myfile2`, reflecting changes across both but not allowing deletion to affect the data's accessibility as long as one hardlink remains.

#### 5. Link Count

- **Function**: The link count indicates the number of hardlinks pointing to the same inode. It is visible in the `ls -li` command output, showing how many access points a file has.
- **Mechanism**: Deleting one hardlink decreases the inode's link count, but the inode and its data are only removed when all associated hardlinks are deleted.

#### 6. Commands for Links

- **Symlink Command**: To create a symlink, use `ln -s target_file link_name`, creating a link named `link_name` to `target_file`.
- **Hardlink Command**: For a hardlink, the command is `ln source_file link_name`, linking `link_name` directly to `source_file`'s inode without the `-s` flag, signifying a direct inode link.