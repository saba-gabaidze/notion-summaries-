# Chapter 6 Process Managment

# Viewing Processes

- **ps Command**: Displays the currently running processes on a system.
- **ps aux**: Shows all processes for all users, including background/system processes.
- **Key Columns in ps aux Output**:
    - **USER**: The user who started the process.
    - **PID**: Unique process ID assigned by the system.
    - **%CPU**: CPU usage percentage for the process.
    - **%MEM**: Memory usage percentage for the process.
    - **COMMAND**: The command that started the process.

# **Filtering Processes**

- Use the `ps aux` command to display processes, then pipe the output to `grep` to filter by a specific process name.
    - Example: `ps aux | grep msfconsole`
- **Output**:
    - Only processes that match the search term (e.g., `msfconsole`) are displayed.
    - The `grep` command itself will also appear in the output since it's part of the search query.
    - The column header from `ps` (e.g., USER, PID, %CPU) is not shown in the filtered output.
- **Resource Usage**:
    - You can check the resource usage for the filtered process, such as CPU and memory usage (e.g., 35.1% CPU, 15.2% memory).

# Prosses With Most Recourses

`top` - command 

**Interactive Commands**:

- Press **H** or **?** to display a list of commands.
- Press **Q** to quit `top`.

# Managing Processes

## `nice`

**nice Command**: Used to set the priority of a process when starting it.

- **Nice Value Range**: From **20** (highest priority) to **+19** (lowest priority).
- **Default Value**: The default priority is **0**.
- **Effect of Values**:
    - **Low Nice Value** (closer to -20): Higher priority (more resources).
    - **High Nice Value** (closer to +19): Lower priority (less resources).

- To start a process with a nice value of +10:`nice -n 10 command`
- To change the priority of a running process (e.g., PID 1234) to a nice value of -5:`renice -n -5 1234`

        Syntax: `nice -n [value] [command]`

 `renice [value] [PID]`

## `kill`

- `kill [signal] [PID]`
- **[signal]**: Optional signal to send to the process. If omitted, it defaults to `SIGTERM` (signal 15).

**Common Kill Signals:**

- **SIGHUP (1)**: Restart the process with the same PID (often used for reloading configuration files).
- **SIGINT (2)**: Interrupt the process (similar to pressing Ctrl+C). It’s a weak signal and may not always terminate the process.
- **SIGQUIT (3)**: Terminates the process and generates a core dump, saving process information to a file named `core`.
- **SIGTERM (15)**: Default signal used by the `kill` command. It gracefully terminates the process, allowing it to clean up.
- **SIGKILL (9)**: Strongest kill signal. Forces termination of the process without allowing it to clean up (useful for rogue or unresponsive processes).
- `kill -9 “pid”` - complitly kills process

o **terminate a process within `top`**:

- Press `K` in `top` and enter the PID of the process to kill.

## Running Processes in the Background

To run a command in the background, simply add an **ampersand (`&`)** at the end of the

If a process is running in the foreground and you want to send it to the background, use the `bg` command followed by the job number or PID

Moving a Process to the Foreground
If you want to move a process running in the background to the foreground, you can use the `fg` (foreground) command. The fg command
requires the PID of the process you want to return to the foreground, as
shown next.
kali >fg 1234

# Scheduling Processes with `at` and `crond`

The `at`

command accepts a variety of time formats. Some common examples are:

- `at 7:20pm` — Schedules the task for 7:20 PM today.
- `at noon` — Schedules the task for noon today.
- `at tomorrow` — Schedules the task for the same time tomorrow.
- `at now + 20 minutes` — Schedules the task to run in 20 minutes.
- `at now + 10 hours` — Schedules the task to run in 10 hours.
- `at 7:20pm June 25` — Schedules the task for 7:20 PM on June 25.

`kali >at 7:20am
at > /root/myscanningscript`

**Difference Between `at` and `crond`**:

- **at**: For one-time tasks at a specified time.
- **crond**: For recurring tasks (e.g., daily, weekly, monthly), typically handled with cron jobs (discussed in detail in Chapter 16).