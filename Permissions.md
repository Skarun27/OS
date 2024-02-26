## Unix/Linux File Permissions

**File Permissions Overview**

- **Command to View:** `ls -l [directory/file]`
- **Example Output:** `drwxr-xr-x 2 pete penguins 4096 Dec 1 11:45 .`

**Filetype Indicator**

- **`d`**: Directory
- **`-`**: Regular file
- **Other indicators**: `l` (symbolic link), `c` (character devices), `b` (block devices), etc.

**Permissions Structure**

- **Format:** `[filetype][user permissions][group permissions][other permissions]`
- **Example:** `d | rwx | r-x | r-x`

**Permissions Explained**

- **`r`**: Readable - File can be read
- **`w`**: Writable - File can be modified
- **`x`**: Executable - File can be executed (for directories, it means the contents can be listed)
- **`-`**: No permission for the specific action

## Modifying File Permissions: `chmod` Command

**Overview**

- **Purpose**: Change file or directory permissions
- **Syntax**: `chmod [options] mode file`

**Adding and Removing Permissions**

1. **Add Permission**: `chmod u+x myfile`
   - **Explanation**: Adds executable permission for the user (owner) on `myfile`.

2. **Remove Permission**: `chmod u-x myfile`
   - **Explanation**: Removes executable permission for the user on `myfile`.

3. **Multiple Permissions**: `chmod ug+w myfile`
   - **Explanation**: Adds write permission for both user and group on `myfile`.

**Numeric (Octal) Permission Mode**

- **Numerical Representation**:
  - `4`: Read permission
  - `2`: Write permission
  - `1`: Execute permission

- **Example**: `chmod 755 myfile`
  - **Breakdown**:
    - `7` (User): Read (4) + Write (2) + Execute (1) = 7
    - `5` (Group): Read (4) + Execute (1) = 5
    - `5` (Others): Read (4) + Execute (1) = 5
  - **Permissions**: User gets full permissions; group and others get read and execute permissions.

## Ownership Permissions: `chown` and `chgrp` Commands

**Overview**

- **Purpose**: Change the user and/or group ownership of files and directories.

**Modify User Ownership**

- **Command**: `sudo chown patty myfile`
- **Explanation**: Changes the owner of `myfile` to the user `patty`.

**Modify Group Ownership**

- **Command**: `sudo chgrp whales myfile`
- **Explanation**: Changes the group ownership of `myfile` to `whales`.

**Modify Both User and Group Ownership**

- **Command**: `sudo chown patty:whales myfile`
- **Explanation**: Simultaneously changes the owner to `patty` and the group to `whales` for `myfile`.

**Key Points**

- **Root or Sudo Required**: Changing ownership typically requires root privileges or sudo access.
- **User and Group Separation**: Use `chown` to change user ownership, `chgrp` for group ownership, or `chown` with a colon (`:`) to adjust both simultaneously.
- **Security Consideration**: Altering file ownership affects access controls and permissions, impacting file security and accessibility.

## Umask: Setting Default Permissions

**Overview**

- **Purpose**: Defines the default permission set for newly created files and directories, influencing the initial access rights.

**How Umask Works**

- **Operation**: Unlike setting permissions, `umask` _subtracts_ permissions from the system's default creation settings.
- **Command Example**: `umask 021`
    - **Interpretation**: For new files,
        - **User**: Retains all permissions.
        - **Group**: Loses write permission.
        - **Others**: Loses execute permission.

**Default Umask**

- **Typical Default**: `022`
    - **Effect**: Grants full access to the user, while group and others lack write permissions.

**Modifying Umask**

- **Temporary Change**: Directly in the shell, affects only the current session.
- **Persistent Change**: Modify startup files (e.g., `.profile`, `.bashrc`, or `.bash_profile`) to apply the `umask` setting automatically on login.

## Setuid: Elevating User Permissions

**Overview**

- **Purpose**: `setuid` (Set User ID) is a special permission bit that allows users to run a program with the file owner's permissions, typically for tasks requiring elevated privileges.

**How Setuid Works**

- **Example Case**: Changing user passwords with the `passwd` command, which modifies `/etc/shadow`, a file owned by root.
- **Mechanism**: A file with `setuid` set (indicated by an `s` in the permission set) runs as if the file's owner is executing it, regardless of the user who actually launched the program.

**Identifying Setuid**

- **Command**: `ls -l /usr/bin/passwd`
- **Output**: `-rwsr-xr-x`
- **Key**: The `s` in the user's permission set (`rws`) indicates `setuid`. Without `setuid`, normal users couldn't modify files owned by root, such as `/etc/shadow`.

**Modifying Setuid**

- **Symbolic Method**: `sudo chmod u+s myfile` adds `setuid` to a file.
- **Numeric Method**: `sudo chmod 4755 myfile` also adds `setuid`, where `4` in the first position signifies the `setuid` bit.

**Significance of `S` vs. `s`**

- **Lowercase `s`**: Indicates `setuid` is set, and the file is executable.
- **Uppercase `S`**: Indicates `setuid` is set, but the file lacks execute permissions.

## Setgid: Group Permission Elevation

**Overview**
- **Purpose**: `setgid` (Set Group ID) is a permission bit allowing programs to run with the permissions of the file's group, enhancing collaboration and security.

**Example**
- **Command**: `ls -l /usr/bin/wall`
- **Output**: `-rwxr-sr-x`
- **Observation**: The `s` in the group permissions (`r-s`) indicates `setgid`.

**Modifying SGID**
- **Symbolic Method**: `sudo chmod g+s myfile` adds `setgid` to a file.
- **Numeric Method**: `sudo chmod 2555 myfile` applies `setgid`, where `2` signifies the `setgid` bit.

**Key Points**
- `setgid` mirrors `setuid`, but applies to group permissions.
- Essential for shared resources, ensuring files or directories use group permissions effectively.
- Use cautiously to avoid unintended access rights escalation.

## Process Permissions and UIDs: Key Concepts

**Overview of Process Permissions**

- **Effective User ID (EUID)**: Dictates the permissions for the process. Processes inherit the EUID from the user or group that initiated them, determining access rights during execution.
  
- **Real User ID (RUID)**: Identifies the actual user who launched the process. It's used for accountability and tracking purposes.

- **Saved User ID (SUID)**: Enables a process to switch between its EUID and RUID. This feature allows temporary elevation of privileges, typically utilized by processes requiring higher permissions at specific moments.

**Practical Example: The `passwd` Command**

- **SUID Bit**: When a command like `passwd` is executed with SUID set, it temporarily runs with the privileges of the file's owner (often root), allowing it to perform tasks (e.g., modifying `/etc/shadow`) that require elevated permissions.

- **Permissions Check**: Despite running with elevated EUID (root), actions are constrained to what the initiating user's RUID allows. For example, a regular user cannot modify another user's password unless their RUID has the necessary permissions.

- **Security Mechanism**: The separation of EUID and RUID, along with the use of SUID, provides a controlled way to elevate privileges for specific operations without granting unrestricted root access, enhancing security and minimizing risk.

**Key Takeaways**

- **UID Roles**:
  - **EUID**: Determines what resources a process can access.
  - **RUID**: Identifies the initiating user, ensuring accountability.
  - **SUID**: Facilitates privilege escalation for specific tasks.

##  The Sticky Bit: Understanding Its Role and Usage

**Overview**

- **Purpose**: The sticky bit is a special permission bit that, when set on a directory, restricts file deletion and modification to the file's owner, the directory's owner, or the root user, regardless of the directory's other permissions.

**Use Case Example: `/tmp` Directory**

- **Command**: `ls -ld /tmp`
- **Output**: `drwxrwxrwxt`
- **Explanation**: The `t` at the end of the permissions (instead of an `x`) indicates that the sticky bit is set. This setup allows any user to create, write, or modify files within `/tmp`, but only the file or directory owner (and root) can delete them.

**Modifying the Sticky Bit**

- **To Add Sticky Bit**: `sudo chmod +t mydir`
- **To Specify Numerically**: `sudo chmod 1755 mydir`
- **Numeric Representation**: The `1` in the `1755` chmod command represents the sticky bit.