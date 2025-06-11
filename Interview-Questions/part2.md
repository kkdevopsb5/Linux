## ✅ 6. Scenario: Permission Denied When Running a Script

**Question:**  
A user runs a shell script but gets a "Permission denied" error. How would you resolve it?

**Answer:**
```bash
ls -l script.sh
chmod +x script.sh
```

**Explanation:**  
The issue is usually missing execute permission. I use `ls -l` to verify and `chmod +x` to fix. This shows basic but critical knowledge of Linux permissions and script execution.

---

## ✅ 7. Scenario: Port 80 is Already in Use

**Question:**  
You try to start Apache, but it fails because port 80 is already in use. How do you handle this?

**Answer:**
```bash
netstat -tuln | grep :80
lsof -i :80
kill -9 <PID>  # if safe to stop
```

**Explanation:**  
This shows the ability to identify conflicting services using `netstat` and `lsof`, and the judgment to safely terminate processes. It’s a real-world issue in multi-service environments.

---

## ✅ 8. Scenario: Root Password Forgotten

**Question:**  
You have physical access to a Linux machine but forgot the root password. How would you reset it?

**Answer:**
1. Reboot the machine.
2. In GRUB menu, edit the boot entry and add:
   ```
   init=/bin/bash
   ```
3. Once in shell:
   ```bash
   mount -o remount,rw /
   passwd root
   exec /sbin/init
   ```

**Explanation:**  
This is a critical recovery scenario. Shows knowledge of boot process, GRUB, single-user mode, and password recovery—great for proving deep system understanding.

---

## ✅ 9. Scenario: Swap Memory is Full

**Question:**  
The system is using too much swap memory and becoming slow. What would you do?

**Answer:**
```bash
free -h
swapon --show
top  # check swap-using processes
swapoff -a
swapon -a
```

**Explanation:**  
Demonstrates understanding of virtual memory, how to monitor it, and how to clear swap. You might also investigate the need for more RAM or optimize heavy applications.

---

## ✅ 10. Scenario: File Deleted Accidentally – Need Recovery

**Question:**  
A critical file was deleted accidentally from the system. Can it be recovered?

**Answer:**  
- If it's still open by a process:
  ```bash
  lsof | grep deleted
  cp /proc/<pid>/fd/<fd> /recovered_file
  ```
- Otherwise, restore from backup or snapshots (if available).

**Explanation:**  
This scenario shows creative use of `/proc` and `lsof` for emergency recovery. It also highlights the importance of having backup policies in place.

---
```

