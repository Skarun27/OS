
## Processes and Monitoring: `ps` and `top` Commands

**Processes Overview**
- **Definition**: Programs running on a system, managed by the kernel.
- **Process ID (PID)**: Unique identifier for each process.

**`ps` Command**
- **Usage**: Displays a snapshot of running processes.
- **Basic Output**:
  - `PID`: Process ID.
  - `TTY`: Terminal associated with the process.
  - `STAT`: Process status.
  - `TIME`: CPU usage time.
  - `CMD`: Executable/command name.
- **Popular Option**: `ps aux`
  - `a`: Shows processes from all users.
  - `u`: Detailed process information.
  - `x`: Processes without a controlling terminal (common in daemons).

**Key Fields in `ps aux`**
- `USER`: User running the process.
- `%CPU`: CPU usage percentage.
- `%MEM`: Memory usage percentage.
- `VSZ`: Virtual memory size.
- `RSS`: Physical memory used.
- `START`: Process start time.

**`top` Command**
- **Usage**: Provides real-time process monitoring.
- **Features**: Auto-refreshes (default every 10 seconds), showing resource-intensive processes.

**Summary**
- `ps` offers a static view of processes, useful for identifying running programs and their statuses. The `ps aux` variant is particularly helpful for a comprehensive overview.
- `top` provides dynamic, real-time monitoring of system processes, highlighting resource usage. It's invaluable for system administration and troubleshooting.

These tools are essential for managing system resources, diagnosing performance issues, and understanding system operation.

## Controlling Terminal

**Terminals Overview**

- **TTY**: Represents the terminal that executed a command, visible in the `ps` output.

**Types of Terminals**

1. **Regular Terminal Devices**: Native terminals that interface directly with the system, accessible via shortcuts like Ctrl-Alt-F1 (TTY1). They provide a non-graphical, terminal-only environment.
2. **Pseudoterminal Devices (PTS)**: Emulate terminal devices within graphical environments, like terminal windows in GUIs. This is what most users interact with in a desktop environment.

**Key Points**

- **Switching to TTY1**: Use Ctrl-Alt-F1 to access a regular terminal device (virtual console) for a pure terminal experience, devoid of graphical elements. Return to the graphical interface with Ctrl-Alt-F7.
- **Pseudoterminals**: Represent the terminal windows in a graphical user interface, showing processes with `pts/*` in the `ps` output.

**Controlling Terminal and Processes**

- **Binding**: Processes are typically tied to a controlling terminal. Closing this terminal will terminate the associated processes.
- **Daemon Processes**: Special background processes crucial for system operations, starting at boot and ending at shutdown. They do not have a controlling terminal (marked with a `?` in `ps` output), preventing them from being inadvertently terminated by closing a terminal.

**Summary** Understanding the distinction between regular and pseudoterminals is crucial for system navigation and managing processes. Regular terminals offer a direct, non-graphical interface to the system, while pseudoterminals provide a graphical emulation of terminals. Daemon processes' independence from controlling terminals ensures they remain uninterrupted during system operation.

## Process details

**Overview of Processes**

- **Definition**: A process is essentially a running instance of a program, which the system supports by allocating necessary resources such as memory, CPU, and I/O.

**Practical Demonstration**

- **Example**: Opening multiple terminal windows and running the `cat` command in two of them creates two separate processes for `cat`, even though they execute the same program. This can be verified by listing processes with `ps aux | grep cat` in a third terminal.

**Kernel's Role**

- The kernel orchestrates process management by:
    - Loading program code into memory.
    - Allocating resources (memory, CPU, I/O).
    - Monitoring process status and resource consumption.
    - Handling process ownership and signal processing.
- It ensures efficient resource distribution among processes and reclaims resources from terminated processes.

**Key Takeaways**

- **Process Instance**: Each process is an individual instance, with its own resource allocation, even if multiple instances of the same program are running.
- **Resource Management**: The kernel dynamically manages resources among processes, balancing system load and ensuring smooth operation.
- **Signals and Ownership**: The kernel also handles more intricate aspects like signal processing and identifying process owners.

**Summary** Processes are fundamental units of execution in the system, managed comprehensively by the kernel to ensure efficient operation. Understanding the lifecycle and management of processes is crucial for effective system administration and troubleshooting.

## Process Creation

**Process Creation and Management**

- **`fork` System Call**: Used by an existing process to create a new, mostly identical child process. The child inherits the parent's memory space but is assigned a unique Process ID (PID), while the original process becomes the parent with a Parent Process ID (PPID).
- **`execve` System Call**: Allows a child process to execute a new program, replacing its current memory space with a new setup tailored for the new program. This enables the child to diverge from the parent's task.

**Viewing Process Hierarchy**

- **Command**: `ps l`
    - **Output Includes**: PID (Process ID) and PPID (Parent Process ID), offering insight into process relationships.
- **Example**: Running `bash` spawns child processes (e.g., executing `ps l`). The `bash` process PID appears as the PPID of its child processes.

**System Initialization Process**

- **`init` Process**: The first process started by the kernel during boot (PID 1), acting as the ancestor of all other processes. It cannot be terminated until system shutdown and runs with root privileges, responsible for spawning essential system processes.

**Summary**

- Processes in Unix-like systems are hierarchically organized, starting from the `init` process.
- `fork` creates a new process as a clone of the parent, while `execve` allows it to execute different programs, essential for the dynamic operation of the system.
- The relationship between processes can be examined using commands like `ps l`, highlighting the structured management of tasks within the system.

## Process Termination, Orphan, and Zombie Processes

**Process Termination**

- Processes terminate using the `_exit` system call, releasing their resources back to the system.
- Termination status is provided to the kernel; `0` typically signifies success.
- Parent processes must acknowledge child termination via the `wait` system call to check the child's termination status.

**Orphan Processes**

- Occur when a parent process terminates before its child.
- The kernel assigns orphaned processes to `init` (the root of all processes), which then performs the necessary `wait` call, allowing these orphans to terminate properly.

**Zombie Processes**

- Arise when a child process terminates, but the parent has not yet executed a `wait` call.
- Although the child's resources are released, an entry remains in the process table, creating a "zombie."
- Zombies cannot be killed with signals as they are already "dead."
- Parent process `wait` calls or `init` adoption can clean up zombies by "reaping" them, removing their process table entries.
- Accumulation of zombie processes is problematic, as it fills the process table and can prevent new processes from starting.

**Key Points**

- Proper process termination and cleanup are crucial for system health, involving specific system calls like `_exit` and `wait`.
- Orphan and zombie processes are managed by the system(init) to ensure resource availability and maintain the process table's integrity.
- The `init` process plays a vital role in cleaning up orphans and zombies, acting as a fail-safe to prevent system resource exhaustion.

## Signals Overview

- **Purpose of Signals**: Signals serve as software interrupts, facilitating communication between processes or between the kernel and a process due to various events, such as user actions (e.g., Ctrl-C, Ctrl-Z), hardware issues, or software faults.

- **Signal Process**:
  - Generated: A signal is produced in response to an event.
  - Pending: Until delivered, the signal is in a pending state.
  - Delivery: Signals are delivered when the process is next scheduled to run.
  - Handling: Processes can ignore, catch (with a handler routine), terminate, or block signals based on their signal mask.

- **Common Signals**:
  - **SIGHUP (1)**: Hangup.
  - **SIGINT (2)**: Interrupt from keyboard (e.g., Ctrl-C).
  - **SIGKILL (9)**: Unconditionally terminate the process.
  - **SIGSEGV (11)**: Invalid memory access (segmentation fault).
  - **SIGTERM (15)**: Request process termination.
  - **SIGSTOP**: Pause the process.
  - *Note*: Signal numbers can vary, so names (SIGxxx) are preferred for reference.

- **Key Points**:
  - Signals are identified by integers and symbolic names (SIGxxx).
  - Some signals, like SIGKILL and SIGSTOP, cannot be blocked or ignored, ensuring they can always effectively signal the intended action to processes.

## kill Command and Termination Signals

### Kill (Terminate)

- **kill Command**: Used to send signals to terminate processes. Syntax: `$ kill [PID]`, where `[PID]` is the Process ID of the target process. By default, sends the `SIGTERM` signal.
  
  Example: `$ kill 12445` sends a `SIGTERM` to process with PID 12445.

- **Specifying Signals**: You can specify the signal to send with the kill command by using its signal number or name.
  
  Example: `$ kill -9 12445` sends a `SIGKILL` to forcefully terminate process 12445.

### Differences Between Common Termination Signals

- **SIGHUP** (`Hangup`): Sent to a process when its controlling terminal is closed. It indicates the process has been "hung up on".

- **SIGINT** (`Interrupt`): An interrupt signal, typically sent by pressing `Ctrl-C`. It requests the system to gracefully terminate the process.

- **SIGTERM** (`Terminate`): Requests a process to terminate, allowing it to perform cleanup operations before shutting down.

- **SIGKILL** (`Kill`): Forces a process to terminate immediately, without cleanup. This is the nuclear option for terminating processes.

- **SIGSTOP** (`Stop/Suspend`): Suspends a process's execution. The process can be resumed later.

## Niceness and Process Scheduling

- **Process Scheduling**: Although it appears multiple processes (e.g., Chrome, Word, Photoshop) run simultaneously, they actually share the CPU through time slices. The kernel schedules these slices in a round-robin fashion, ensuring each process gets CPU time.
    
- **Niceness**: A value that influences process scheduling priority. It's a numerical value associated with each process that indicates its priority level:
    
    - **High Niceness Value**: Indicates the process is "nice" to others, taking lower priority. Higher values mean lower priority for CPU time.
    - **Low/Negative Niceness Value**: Indicates the process is less "nice," seeking more CPU time. Lower values mean higher priority.
- **Viewing Niceness**:
    
    - Use the `top` command to view processes along with their niceness values (NI column).
- **Modifying Niceness**:
    
    - **To Set on New Process**: Use `nice -n [value] [command]` to start a new process with a specified niceness.
        - Example: `$ nice -n 5 apt upgrade` starts the `apt upgrade` process with a niceness of 5.
    - **To Adjust Existing Process**: Use `renice [value] -p [PID]` to change the niceness of an already running process.
        - Example: `$ renice 10 -p 3245` changes the niceness of the process with PID 3245 to 10.

Niceness allows users and system administrators to influence the kernel's scheduling decisions, optimizing the system's responsiveness and performance based on the priority of tasks.

## Process States in Linux

- **Viewing Process States**: Use `ps aux` to view processes along with their states, displayed in the STAT column.
    
- **Common State Codes**:
    
    - **R (Running or Runnable)**: The process is either currently running on the CPU or waiting to run.
    - **S (Interruptible Sleep)**: The process is sleeping, waiting for an event or input to complete. It can be woken up by signals.
    - **D (Uninterruptible Sleep)**: The process is in a sleep state that cannot be interrupted. Signals cannot wake it, often requiring a reboot to resolve issues causing this state.
    - **Z (Zombie)**: Represents a terminated process that has not yet been fully cleaned up, as its termination status has not been collected by its parent.
    - **T (Stopped)**: The process has been stopped or suspended, usually by receiving a signal. It remains in this state until it's specifically continued or terminated.

These states reflect a process's current condition in the system, ranging from active execution to various forms of inactivity, awaiting external events or intervention.

## /proc filesystem

* Remember everything in Linux is a file, even processes. Process information is stored in a special filesystem known as the /proc filesystem.

	`$ ls /proc`

* You should see multiple values in here, there are sub-directories for every PID. If you looked at a PID in the ps output, you would be able to find it in the /proc directory.

* Go ahead and enter one of the processes and look at that file:

	`$ cat /proc/12345/status`

* You should see process state information and well as more detailed information. The /proc directory is how the kernel is views the system, so there is a lot more information here than what you would see in ps.

## Job Control Notes

- **Running Commands in the Background**: Append an ampersand (`&`) to a command to run it in the background, allowing continued use of the shell.
  - Example: `sleep 1000 &`

- **Viewing Background Jobs**: Use the `jobs` command to list all background jobs.
  - Displays job ID, status, and command.
  - The job marked with `+` is the most recent, and `-` is the second most recent.

- **Sending Running Jobs to Background**:
  1. Suspend the job using `Ctrl-Z`.
  2. Use the `bg` command to continue it in the background.
     - Example: After suspending `sleep 1003`, run `bg` to move it to the background.

```
pete@icebox ~ $ sleep 1003
^Z
[4]+    Stopped     sleep 1003

pete@icebox ~ $ bg
[4]+    sleep 1003 &

pete@icebox ~ $ jobs
[1]    Running     sleep 1000 &
[2]    Running     sleep 1001 &
[3]-   Running     sleep 1002 &
[4]+   Running     sleep 1003 &
```

- **Moving Jobs to the Foreground**: Use `fg %jobID` to bring a background job to the foreground.
  - Running `fg` without specifying a job ID brings the most recent job to the foreground.

- **Killing Background Jobs**: Use `kill %jobID` to terminate a background job by its Job ID.