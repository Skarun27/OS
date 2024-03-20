
## `top` command (Tracking processes)

```
top - 18:06:26 up 6 days,  4:07,  2 users,  load average: 0.92, 0.62, 0.59
  
Tasks: 389 total,   1 running, 387 sleeping,   0 stopped,   1 zombie

==============================CPU Info===========================
  
%Cpu(s):  1.8 us,  0.4 sy,  0.0 ni, 97.6 id,  0.1 wa,  0.0 hi,  0.0 si,  0.0 st
  
KiB Mem:  32870888 total, 27467976 used,  5402912 free,   518808 buffers
  
KiB Swap: 33480700 total,    39892 used, 33440808 free. 19454152 cached Mem

==============================Process Info===========================

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                             
  
 6675 patty    20   0 1731472 520960  30876 S   8.3  1.6 160:24.79 chrome                             
  
 6926 patty    20   0  935888 163456  25576 S   4.3  0.5   5:28.13 chrome
```


`top` is a powerful utility for real-time system monitoring, providing a dynamic view of process activity and system resource utilization. Understanding `top`'s output helps in diagnosing performance issues and managing system resources efficiently.

#### Key Sections of `top` Output:

1. **System Overview:**
   - **Current Time:** Shows the current system time.
   - **Uptime:** Duration the system has been running.
   - **Users:** Number of users logged in.
   - **Load Average:** 1, 5, and 15-minute averages of the load on the system.

2. **Task Summary:**
   - Shows the total number of processes and their states: running, sleeping, stopped, or zombie.

3. **CPU Usage Breakdown:**
   - **us (user):** CPU time used by non-niced user processes.
   - **sy (system):** CPU time used by system/kernel processes.
   - **ni (nice):** CPU time used by niced user processes.
   - **id (idle):** CPU time spent idle.
   - **wa (I/O wait):** CPU time waiting for I/O completion.
   - **hi (hardware interrupts):** Time spent handling hardware interrupts.
   - **si (software interrupts):** Time spent handling software interrupts.
   - **st (steal time):** Time virtual CPU waited while the hypervisor serviced other processes.

4. **Memory and Swap Usage:**
   - Displays total, used, and free amounts of physical memory and swap space.

5. **Per-Process Information:**
   - **PID:** Process ID.
   - **USER:** Owner of the process.
   - **PR:** Priority.
   - **NI:** Nice value.
   - **VIRT:** Virtual memory used.
   - **RES:** Resident (physical) memory used.
   - **SHR:** Shared memory size.
   - **S:** Process status (e.g., S=sleeping, R=running).
   - **%CPU:** CPU usage percentage.
   - **%MEM:** Memory usage percentage.
   - **TIME+:** Cumulative CPU time.
   - **COMMAND:** Process name/command.

#### Tracking Specific Processes:

- To monitor specific processes, use `top` with the `-p` option followed by the PID: `$ top -p <PID>`

#### Practical Tips:

- Regularly monitoring system resources with `top` can help identify processes consuming excessive resources.
- Pay particular attention to the `%CPU`, `%MEM`, and `wa` fields to understand CPU and memory usage, as well as potential I/O bottlenecks.
- Use the information provided by `top` to make informed decisions about system optimizations, process prioritization, and resource allocation.


## `lsof` and `fuser` for Tracking File Usage

When you encounter a "Device or Resource Busy" error, it often means a file or device is still in use, preventing operations like unmounting a USB drive. Two essential tools to diagnose and resolve such issues are `lsof` and `fuser`.


#### `lsof` - List Open Files

- **Purpose:** Identifies files opened by processes. Useful for finding which processes are using specific files or devices.
- **Usage:** `lsof [options] [file]`
  - Without options, `lsof` lists all open files.
  - Specifying a file or directory (e.g., `lsof /path/to/usb`) shows all processes accessing that location.

- **Example Output:**
  ```
  COMMAND    PID  USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
  xterm     2205 pete  cwd    DIR    8,6     4096  131 .
  ```
  - **COMMAND:** The command (process) name.
  - **PID:** Process ID.
  - **USER:** User running the process.
  - **FD:** File descriptor, indicating the type of access (e.g., `cwd` for current working directory).
  - **TYPE:** The type of file (e.g., `DIR` for directory).
  - **DEVICE:** Device number.
  - **SIZE/OFF:** Size of the file or offset.
  - **NAME:** File or directory name.

#### `fuser` - File User

- **Purpose:** Identifies processes using a specific file or file system, handy for pinpointing what's blocking a device from being released.
- **Usage:** `fuser [options] [file]`
  - The `-v` option provides verbose output, showing details about each process using the specified file or directory.

- **Example Output:**
  ```
                     USER        PID ACCESS COMMAND
  /home/pete:         pete  1491 ..c.. lxsession
  ```
  - Lists the user, PID, type of access, and the command name for processes using the `/home/pete` directory.

#### Key Differences and Use Cases

- **`lsof` vs. `fuser`:** 
  - `lsof` provides a comprehensive list of all open files and the processes that opened them. It's versatile, allowing you to filter by file, PID, user, and more.
  - `fuser` is more focused, primarily used to find processes using a specific file or file system, making it ideal for troubleshooting "busy" resources.

- **When to Use:**
  - Use `lsof` when you need a detailed overview of file usage across the system.
  - Use `fuser` when you know the specific file or directory in question and want to quickly identify processes that are using it.


## Process Threads

Threads, often considered lightweight processes, play a crucial role in executing programs efficiently. Understanding the distinction between single-threaded and multi-threaded processes, alongside their operation and management, is essential for developing and managing software applications.

#### Threads Explained

- **Threads vs. Processes:**
  - **Processes** are independent execution units containing their own state information, memory space, and system resources. Each process is executed in isolation by the operating system.
  - **Threads** are components of a process that can run concurrently, sharing the process's resources such as memory and file handles, but each thread maintains its own instruction pointer, stack, and local variables.

- **Single-threaded vs. Multi-threaded Processes:**
  - A **single-threaded** process contains only one thread of execution, meaning tasks are completed one at a time, sequentially.
  - A **multi-threaded** process contains multiple threads, allowing for the execution of separate tasks simultaneously, enhancing efficiency and performance, especially on multi-core processors.

#### Advantages of Multi-threading

- **Resource Sharing:** Threads within the same process share memory and resources, facilitating easier and more efficient communication and data exchange between them.
- **Performance:** Multi-threading can significantly improve the performance of an application by utilizing parallel processing capabilities of modern CPUs.
- **Responsiveness:** Multi-threaded applications can remain responsive to user input by dedicating a thread to UI interactions while other threads perform background tasks.

#### Viewing Process Threads with `ps`

- The `ps m` command displays processes and their associated threads.
  - **PID:** Process ID.
  - **TTY:** Terminal type.
  - **STAT:** Process state.
  - **TIME:** CPU time taken by the process.
  - **COMMAND:** Command name or command line (path of the executed program).
- Threads of a process are shown beneath their parent process, distinguished by dashes (`- -`), indicating they belong to the same process group.

#### Example and Interpretation

- In the example output of `ps m`, each process listed is single-threaded as indicated by a single thread entry under each process.
- Multi-threaded processes would show additional thread entries (with dashes) under the main process PID, reflecting the concurrent execution paths within the same application.

Understanding and managing threads is fundamental for optimizing application performance and resource utilization, especially in complex, resource-intensive, or real-time applications. Developers often use multi-threading to exploit the full potential of modern multi-core processors, achieving parallelism and improving application responsiveness.


## CPU Monitoring using `uptime`

CPU monitoring is crucial for assessing the performance and health of your system. The `uptime` command provides a snapshot of your system's operational status, including the load average, which is a key indicator of CPU load over time.

#### Understanding `uptime`

- **Command Output:** `uptime` displays the current time, system uptime, the number of logged-in users, and the load average over 1, 5, and 15-minute intervals.
  
- **Example:** `17:23:35 up 1 day, 5:59, 2 users, load average: 0.00, 0.02, 0.05`

#### Deciphering Load Average

- **Definition:** Load average represents the average number of processes waiting for CPU time over 1, 5, and 15-minute periods.
  
- **Interpretation:**
  - **Single-Core CPU:** A load average of 1.0 means the CPU is fully utilized. Above 1.0 indicates overutilization (processes are waiting), and below 1.0 means underutilization.
  - **Multi-Core CPU:** Divide the load average by the number of CPU cores to determine the per-core utilization. For example, a load of 2 on a quad-core system means each core is, on average, under 50% load.

#### Significance of Load Averages

- **System Performance:** High load averages indicate that processes frequently wait for CPU time, potentially slowing down the system.
  
- **Core Count Impact:** Modern systems with multiple cores can handle higher load averages without degradation in performance. It's essential to consider the core count when evaluating load averages.
  
- **Troubleshooting:** Consistently high load averages can signal issues such as resource-heavy applications, insufficient CPU resources for the workload, or system misconfigurations.

#### Checking CPU Cores

- To accurately assess load averages, know the number of CPU cores:
  - **Linux:** `cat /proc/cpuinfo` provides detailed CPU information, including the number of cores.
  - **macOS:** `sysctl -n hw.ncpu` shows the number of logical CPU cores.

#### Practical Tips

- **Load Average Context:** Always consider load averages in the context of your CPU's core count. A load average equal to the core count indicates full utilization without excess waiting.
  
- **System Monitoring:** Regularly check `uptime` alongside other monitoring tools to get a comprehensive view of system health and identify potential bottlenecks or performance issues.

Understanding and monitoring CPU load through `uptime` and considering the number of cores is vital for maintaining optimal system performance and ensuring that resources are appropriately allocated to meet demand.


## I/O Monitoring using `iostat`

`iostat` is a valuable tool for monitoring system input/output (I/O) statistics for devices and partitions, providing insights into CPU utilization and disk I/O. It helps in identifying bottlenecks in disk-intensive applications and optimizing system performance.

```
pete@icebox:~$ iostat
  
Linux 3.13.0-39-lowlatency (icebox)     01/28/2016      _i686_  (1 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
  
           0.13    0.03    0.50    0.01    0.00   99.33

Device:            tps    kB_read/s    kB_wrtn/s    kB_read    kB_wrtn
  
sda               0.17         3.49         1.92     385106     212417
```

#### Key Metrics Reported by `iostat`

- **CPU Utilization:**
  - `%user`: Percentage of CPU utilization at the user level (applications).
  - `%nice`: Percentage of CPU utilization at the user level with nice priority.
  - `%system`: Percentage of CPU utilization at the system level (kernel).
  - `%iowait`: Percentage of time CPUs were idle with outstanding disk I/O requests.
  - `%steal`: Percentage of time in involuntary wait by virtual CPUs while the hypervisor serviced another processor.
  - `%idle`: Percentage of time CPUs were idle without outstanding disk I/O requests.

- **Disk Utilization:**
  - `tps`: Transfers per second to the device. Represents the number of I/O requests processed.
  - `kB_read/s`: Kilobytes read from the device per second.
  - `kB_wrtn/s`: Kilobytes written to the device per second.
  - `kB_read`: Total kilobytes read.
  - `kB_wrtn`: Total kilobytes written.

#### Interpretation and Use Cases

- **CPU Metrics:**
  - High `%user` and `%system` values indicate significant time spent on application and kernel activities, respectively.
  - High `%iowait` suggests I/O bottlenecks, where CPU is waiting for disk operations to complete.
  - High `%idle` indicates underutilized CPU resources.

- **Disk Metrics:**
  - High `tps` indicates a high number of read/write operations, useful for gauging disk activity.
  - `kB_read/s` and `kB_wrtn/s` provide insights into the read and write throughput of the disk.
  - Cumulative `kB_read` and `kB_wrtn` values help understand long-term disk usage patterns.

#### Practical Applications

- **Performance Tuning:** Identifying I/O bottlenecks and CPU usage patterns to optimize system performance.
- **Capacity Planning:** Assessing disk throughput and CPU load for future resource allocation.
- **Troubleshooting:** Diagnosing high load issues, understanding disk and CPU demand of applications.

Using `iostat`, system administrators and performance analysts can gain a comprehensive overview of the system's I/O and CPU performance, enabling informed decisions for troubleshooting, optimization, and planning.


## Memory Monitoring using `vmstat`

`vmstat` is a tool for monitoring system performance, focusing on memory, swap, I/O, and CPU activity. It provides a snapshot of system's current state, helping identify bottlenecks and performance issues.

#### Key `vmstat` Metrics:

- **Processes (`procs`):**
  - `r`: Runnable processes (waiting for run time).
  - `b`: Processes in uninterruptible sleep.

- **Memory:**
  - `swpd`: Virtual memory used.
  - `free`: Free memory available.
  - `buff`: Memory used as buffers.
  - `cache`: Memory used as cache.

- **Swap:**
  - `si`: Memory swapped in from disk (KB/s).
  - `so`: Memory swapped out to disk (KB/s).

- **I/O:**
  - `bi`: Blocks received from a block device (blocks/s).
  - `bo`: Blocks sent to a block device (blocks/s).

- **System:**
  - `in`: Interrupts per second, including the clock.
  - `cs`: Context switches per second.

- **CPU:**
  - `us`: Time spent running non-kernel code. (user time, including nice time)
  - `sy`: Time spent running kernel code. (system time)
  - `id`: Time spent idle.
  - `wa`: Time spent waiting for I/O.
  - `st`: Time stolen from a virtual machine.

#### Practical Use:

- **Performance Analysis:** Detect memory and swap usage trends, assess system's I/O and CPU load.
- **Bottleneck Identification:** High `wa` values indicate I/O wait, `swpd` and `si/so` suggest swapping activity, impacting performance.
- **System Tuning:** Insights into memory consumption (`free`, `buff`, `cache`) and process activity (`r`, `b`) for optimization.

`vmstat` offers valuable insights for system administrators and performance analysts, aiding in the efficient management and optimization of memory resources and overall system performance.


## Continuous Monitoring with `sar`

`sar` (System Activity Reporter) is a comprehensive tool for historical and real-time monitoring of system performance. It's part of the `sysstat` package and provides detailed insights into various system resources over time.

#### Installing `sar`

- **Package Installation:** Ensure `sar` is installed on your system by installing `sysstat`:
  ```
  sudo apt install sysstat
  ```

#### Setting Up Data Collection

- **Automatic Data Collection:** Typically, `sysstat` begins collecting data automatically post-installation.
- **Manual Enablement:** If automatic collection isn't active, enable it by editing `/etc/default/sysstat` and setting `ENABLED` to "true".

#### Using `sar` for Monitoring

- **Load Average:** Use `sar -q` to view load averages since the start of the day.
- **Memory Usage:** `sar -r` displays memory usage details.
- **CPU Usage:** `sar -P` shows CPU usage statistics. Adding `ALL` after `-P` provides details for all CPUs.
- **Historical Data:** Historical data can be viewed by specifying the log file from `/var/log/sysstat/`, e.g., `sar -q -f /var/log/sysstat/sa02` for load averages on a specific day.

#### Practical Applications

- **Performance Trends:** `sar` helps identify long-term trends in system performance, useful for capacity planning and troubleshooting.
- **Real-time Analysis:** Besides historical data, `sar` can monitor real-time system performance, aiding in immediate diagnostics.
- **Resource Utilization:** Detailed reports on CPU, memory, and I/O utilization help pinpoint bottlenecks and optimize system configurations.

`sar` is an essential tool for system administrators and performance analysts, providing a granular view of system behavior over time, facilitating effective monitoring, and enhancing decision-making regarding system maintenance and optimization.





