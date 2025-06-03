
## 1. `who`
**Purpose:** Display users currently logged into the system.

```bash
who
who -H   # Displays the header
```
**Use case:** Check who is currently using the server.

---

## 2. `w`
**Purpose:** Display information about current users and their processes.

```bash
w
```
**Use case:** See who is logged in and what they're doing.

---

## 3. `cat /proc/cpuinfo`
**Purpose:** Displays CPU architecture and details.

```bash
cat /proc/cpuinfo
```
**Use case:** Useful to know the number of CPU cores, model name, and performance characteristics.

> If a single-core CPU is handling more than 1 load average, performance may degrade.

---

## 4. `uptime`
**Purpose:** Shows how long the system has been running and the load average.

```bash
uptime
```
**Use case:** Check system stability and performance over time.

> Load average: `0.08, 0.15, 0.16` represent the system load over 1, 5, and 15 minutes.

---

## 5. `whoami`
**Purpose:** Display the currently logged-in username.

```bash
whoami
```
**Use case:** Confirm user identity, especially in scripts.

---

## 6. `whereis`
**Purpose:** Find binary, source, and manual files for a command.

```bash
whereis mkdir
```
**Output:**
```
mkdir: /usr/bin/mkdir /usr/share/man/man1/mkdir.1.gz
```
**Use case:** Useful when troubleshooting or understanding where commands are stored.

---

## 7. `users`
**Purpose:** Lists currently logged-in users.

```bash
users
```

---

## 8. `date`
**Purpose:** Display or set the system date and time.

```bash
date
sudo date -s "20240617"
```
**Use case:**
- Log the start and end of a script with timestamps.
- Synchronize time manually in isolated systems.

---

## 9. `timedatectl`
**Purpose:** Display and control the system time and date settings.

```bash
timedatectl
```
**Use case:** Check timezone and NTP sync status.

---

## 10. `df`
**Purpose:** Shows disk space usage.

```bash
df       # Raw format
df -h    # Human readable
df -Th   # Show filesystem type with readable format
```
**Use case:** Monitor disk space to avoid application failure due to full partitions.

> NOTE: Clean up the `/tmp` directory weekly.

---

## 11. `du`
**Purpose:** Estimate file/directory space usage.

```bash
du -h Ansible/       # Shows size of each file/folder
du -sh Ansible/      # Shows only the total summary
```
**Use case:** Identify what's using space in a directory.

---

## 12. `hostname`
**Purpose:** Displays the system hostname.

```bash
hostname
hostname -i     # Show only IP address
```
**Use case:** Identify which server you're working on, especially in multi-server environments.

---

## 13. `whatis`
**Purpose:** Give a brief description of a command.

```bash
whatis ls
whatis mkdir
```
**Use case:** Quick help instead of full `man` page.

> `man` provides more details than `whatis`.

---

## 14. `systemctl` and `service`
**Purpose:** Manage services.

```bash
# List all services
systemctl list-unit-files   # Press 'q' to quit

# Service status
systemctl status sshd

# Start/Stop/Restart
service sshd start
service sshd stop
```
**Use case:** Used to control background services like Jenkins, Apache (`httpd`), Cron (`crond`), SSH (`sshd`).

> `systemctl` is for RHEL 7.x and newer. `service` is used in older systems.

---

## 15. `last`
**Purpose:** Show login history of users.

```bash
last
last -R ec2-user    # Show for specific user
last -F             # Show login/logout times
```
**Use case:** Audit login history. Find out who accessed the server and when.

---

## 16. `ps`
**Purpose:** View currently running processes.

```bash
ps
ps -a
ps -ef        # Full formatted list

# Filter by user or command
ps -ef | grep -i "ec2-user"
ps -ef | grep -i "jenkins"
```
**Columns:**
- PID: Process ID
- TTY: Terminal type
- TIME: CPU time consumed
- CMD: Launched command

**Use case:** Monitor system processes and troubleshoot stuck or unnecessary ones.

---

## 17. `kill`
**Purpose:** Terminate processes.

```bash
kill -l          # List available signals
kill -9 <PID>    # Force kill a process

# Example:
ps -ef | grep "tomcat"
kill -9 <tomcat-pid>
```
**Use case:** Kill hung or zombie processes.

> NOTE: `kill` can be used for other purposes like signaling.

---

## 18. `top`
**Purpose:** Monitor system resource utilization in real time.

```bash
top
```
**Use case:** View current CPU and memory usage. Identify resource-hungry processes.

> NOTE: Use `df -h` for disk usage. `top` is focused on CPU and memory.

---

## 19. `zip` and `unzip`
**Purpose:** Compress and extract directories/files.

```bash
zip -r ansible.zip Ansible/    # Compress
rm -r Ansible/                 # Remove original (optional)
unzip ansible.zip              # Extract
```
**Use case:** Create backups or transfer files efficiently.

---

## 20. `tar`
**Purpose:** Archive files and directories.

```bash
tar -cvf ansible.tar Ansible   # Create archive

tar -xvf ansible.tar           # Extract archive
```
**Use case:** Used for packaging and backups. Often used before compressing with gzip (`.tar.gz`).

---



