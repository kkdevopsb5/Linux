## ✅ 1. Scenario: Find All Failed SSH Login Attempts

**Command Used:** `grep`

**Question:**  
You are asked to find all failed SSH login attempts from the logs. How would you do that?

**Answer:**
```bash
grep "Failed password" /var/log/secure
```

**Explanation:**  
This command filters lines from `/var/log/secure` that show failed login attempts. It's useful for security auditing and shows understanding of system logs and `grep` filtering.

---

## ✅ 2. Scenario: Get Only IP Addresses from Failed Logins

**Command Used:** `awk`

**Question:**  
From the failed SSH login entries, how do you extract just the IP addresses?

**Answer:**
```bash
grep "Failed password" /var/log/secure | awk '{print $11}'
```

**Explanation:**  
Here, `awk` is used to print the 11th field (which contains the IP). This scenario shows the power of `awk` in parsing structured text like log files.

---

## ✅ 3. Scenario: Replace a Configuration Parameter in a File

**Command Used:** `sed`

**Question:**  
You need to change `PermitRootLogin no` to `PermitRootLogin yes` in the ssh config. How would you do it?

**Answer:**
```bash
sed -i 's/^PermitRootLogin no/PermitRootLogin yes/' /etc/ssh/sshd_config
```

**Explanation:**  
This demonstrates real-world use of `sed` for in-place editing. It also reflects on secure configuration management, often part of sysadmin and DevOps tasks.

---

## ✅ 4. Scenario: Summarize Disk Usage from `df -h` Output

**Command Used:** `awk`

**Question:**  
You want to list all mount points along with their usage percentage. How would you do that?

**Answer:**
```bash
df -h | awk 'NR>1 {print $6, $5}'
```

**Explanation:**  
`awk` is used here to skip the header (`NR>1`) and print mount point (6th field) and usage (5th). This shows how `awk` can be used to filter and format output quickly.

---

## ✅ 5. Scenario: Count Occurrences of a Word in a File

**Command Used:** `grep`, `wc`

**Question:**  
You want to know how many times the word "error" appears in a log file. How?

**Answer:**
```bash
grep -i "error" /var/log/messages | wc -l
```

**Explanation:**  
Combining `grep` and `wc` counts the number of matching lines. Shows effective use of piping and log analysis — something interviewers love to hear.


