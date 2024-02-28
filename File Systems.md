
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