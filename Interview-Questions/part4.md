## ✅ 1. Scenario: Check if Server Was Recently Rebooted

**Command Used:** `uptime`

**Question:**  
How can you check how long a server has been running, or if it was recently rebooted?

**Answer:**
```bash
uptime
```

**Explanation:**  
The `uptime` command shows how long the system has been running, number of users, and load averages. Useful in troubleshooting to confirm if a server was rebooted unexpectedly or recently patched.

---

## ✅ 2. Scenario: Investigate High Load Averages

**Command Used:** `uptime`

**Question:**  
A developer says the server is slow. You suspect high load. How do you confirm it?

**Answer:**
```bash
uptime
```

**Explanation:**  
The load averages at the end of `uptime` output indicate the system load in the last 1, 5, and 15 minutes. High values compared to CPU cores can indicate overuse. Interviewers like candidates who can correlate performance issues with load.

---

## ✅ 3. Scenario: Check Disk Space on All Mounted Filesystems

**Command Used:** `df`

**Question:**  
How do you check disk usage on all file systems in human-readable format?

**Answer:**
```bash
df -h
```

**Explanation:**  
`df -h` gives an overview of disk usage in GB/MB. It's essential for detecting full partitions, especially `/`, `/var`, or `/home`. Commonly used in troubleshooting “disk full” errors.

---

## ✅ 4. Scenario: Check Which Directory is Taking Up Most Space

**Command Used:** `du`

**Question:**  
The `/var` partition is nearly full. How do you find out which subdirectory is using the most space?

**Answer:**
```bash
du -sh /var/* | sort -hr | head -10
```

**Explanation:**  
This command summarizes each subdirectory’s size, sorts them in human-readable format, and lists the top 10 largest. Perfect for space audits and finding logs or backups consuming storage.

---

## ✅ 5. Scenario: Check Disk Usage of Current Directory Recursively

**Command Used:** `du`

**Question:**  
You're inside a directory and want to see size of all subfolders recursively. How do you do that?

**Answer:**
```bash
du -h --max-depth=1
```

**Explanation:**  
This shows a readable breakdown of folder sizes one level deep. Very helpful when analyzing which folders are growing in size within applications, backups, or user directories.

---
```
