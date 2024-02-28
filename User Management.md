
## Users and Groups

* Each user has their own home directory where their user specific files get stored, this is usually located in /home/username, but can vary in different distributions.
* The system also uses groups to manage permissions, groups are just sets of users with permission set by that group, they are identified by the system with their group ID (GID).

## Root

### sudo Command

- **Purpose:** Executes commands with the security privileges of another user, by default the superuser (root).
- **Usage:** `sudo [command]` allows a permitted user to run a command as root or another user, as specified in the `sudoers` file.
- **Features:** Provides fine-grained control over user privileges, logs commands for auditing, and requires the user's password for authentication.

### su Command

- **Purpose:** Switches the current user context to another user, typically to the superuser (root) without specifying a username.
- **Usage:** `su [options] [username]` switches to the specified user account. Without a username, it defaults to root.
- **Features:** Grants full access to the user's environment and commands, requires the target user's password, and is less granular in permission control compared to `sudo`.

### sudoers File

- **Location:** `/etc/sudoers`
- **Purpose:** Configures privileges for `sudo` users, specifying who can run what commands on which hosts.
- **Editing:** Should only be edited with `visudo` to prevent syntax errors and ensure file integrity.
- **Syntax:** `user HOST=(run_as) COMMANDS` defines what commands a user can run, on which hosts, and as which users.
- **Features:** Supports aliases for users, commands, and hosts for easier management. Offers options like `NOPASSWD` for passwordless execution.

### visudo Command

- **Purpose:** Safely edits the `sudoers` file.
- **Usage:** `sudo visudo` opens the `sudoers` file in the default editor set in the environment, applying syntax checking to prevent errors.
- **Features:** Locks the `sudoers` file to prevent simultaneous edits and ensures that only valid configurations are saved, protecting against lockout from `sudo` access.

### Key Points

- **sudo vs. su:** `sudo` executes a single command with elevated privileges, ideal for administrative tasks without full root access. `su` switches the entire user context, including environment variables, to another user, often used for sessions as another user.
- **sudoers Configuration:** Critical for defining and controlling `sudo` access. Use `visudo` for editing to avoid misconfigurations.
- **Best Practices:** Use `sudo` for day-to-day administrative tasks to leverage its granular control and auditing capabilities. Reserve `su` for scenarios where complete user environment switching is necessary. Always edit the `sudoers` file with `visudo` to maintain system integrity and security.

## /etc/passwd

The `/etc/passwd` file is a crucial component in Unix-like operating systems that stores essential information about users. Here's a breakdown of its contents and structure:

- **Purpose**: Lists user accounts, providing a mapping between usernames and their details.
    
- **Command to View**: `cat /etc/passwd`
    
- **Structure**: root:x:0:0:root:/root:/bin/bash
  Each line in the file represents one user account, with fields separated by colons (`:`), as follows:
    
    1. **Username**: The name used to log in.
    2. **Password Indicator**:
        - An `x` signifies that the encrypted password is stored in `/etc/shadow`.
        - A `*` means the account does not have login access.
        - A blank field indicates no password (rare, usually insecure).
    3. **User ID (UID)**: A unique number identifying the user. The root user traditionally has a UID of 0.
    4. **Group ID (GID)**: The primary group ID for the user.
    5. **GECOS Field**: Optional info about the user (real name, phone, etc.), comma-separated.
    6. **Home Directory**: The path to the user's home directory.
    7. **Shell**: The command interpreter or shell assigned to the user, often `/bin/bash`.

### Key Points

- **UIDs**: The system uses UIDs, not usernames, for user identification.
- **Password Storage**: Actual passwords are not in `/etc/passwd` but in `/etc/shadow` for security.
- **User/Group IDs**: UID 0 is reserved for the root user, showcasing its unique system-wide permissions.
- **GECOS Field**: Provides a place for additional user information, though its usage varies.
- **Home & Shell**: Determines where the user lands upon login and what shell they use for command interpretation.

This file, alongside `/etc/shadow`, plays a vital role in user management and security in Unix-like systems

## /etc/shadow

* The /etc/shadow file is used to store information about user authentication. It requires superuser read permissions.
* $ sudo cat /etc/shadow

## /etc/group
* Another file that is used in user management is the /etc/group file. This file allows for different groups with different permissions.
* $ cat /etc/group
* root:*:0:pete
* Very similar to the /etc/password field, the /etc/group fields are as follows:

	1. Group name
	2. Group password - there isn't a need to set a group password, using an elevated privilege like sudo is standard. A "*" will be put in place as the default value.
	3. Group ID (GID)
	4. List of users - you can manually specify users you want in a specific group

## User Management Tools

**Adding Users**

* $ sudo useradd bob
* You'll see that the above command creates an entry in /etc/passwd for bob, sets up default groups and adds an entry to the /etc/shadow file.

**Removing Users**

* $ sudo userdel bob
* To remove a user, you can use the userdel command.

**Changing Passwords**

* $ passwd bob
* This will allow you to change the password of yourself or another user (if you are root).







