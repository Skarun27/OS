
### 1. Overview of the Kernel

- **Core Component**: The kernel is the central part of the operating system.
- **Levels of Abstraction**: Organized into hardware, kernel, and user space.
    - **Hardware**: Physical components like CPU, memory, and disks.
    - **Kernel**: Manages processes, memory, devices, system calls, and filesystem.
    - **User Space**: Includes shell, applications, and graphical interface.

### 2. Privilege Levels

- **Kernel Mode vs. User Mode**: Kernel has complete hardware access, while user space has limited access for safety.
- **Protection Rings**: Concept of privilege levels, with kernel mode (Ring #0) having full system control and user mode (Ring #3) having restricted access.
- **System Calls**: Mechanism allowing user space to perform privileged operations via the kernel.

### 3. System Calls

- **Function**: Provide a way for user space processes to request kernel services.
- **Implementation**: Through a fixed API with unique IDs for each call, involving a switch from user to kernel mode to perform the requested action.
- **Debugging**: `strace` command to view system calls made by a process.

### 4. Kernel Installation

- **Multiple Kernels**: Systems can have multiple kernels installed, selectable via the GRUB menu.
- **Checking Kernel Version**: `uname -r` command.
- **Installation Methods**: Compiling from source or using package managers like `apt`.
- **Updating Kernel**: Using `sudo apt dist-upgrade` for package updates, including the kernel.

### 5. Kernel Location

- **Installation Files**: New kernel files are added to the `/boot` directory, including `vmlinuz` (kernel itself), `initrd` (temporary filesystem), `System.map` (symbolic lookup table), and `config` (kernel configuration).
- **Space Management**: Old versions can be removed to free up space but require caution to avoid deleting the current kernel.

### 6. Kernel Modules

- **Concept**: Modules allow for extending kernel functionality without altering the core kernel code, similar to add-ons for a vehicle.
- **Management**: Modules can be loaded and unloaded on demand with `modprobe`, and configured to load at boot or be blacklisted in `/etc/modprobe.d`.
- **Examples**: Loading a `bluetooth` module with `sudo modprobe bluetooth`, or preventing a module from loading with a blacklist configuration file.