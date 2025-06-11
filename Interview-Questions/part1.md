

## ✅ 1. Scenario: Server Disk Full Suddenly

**Question:**  
A production server suddenly stops responding. You try to SSH but it’s very slow. After logging in, you notice the disk is 100% full. How would you resolve this?

**Answer:**
```bash
df -h
du -sh /* 2>/dev/null | sort -hr | head -10
> /var/log/messages
yum clean all
```

**Explanation:**  
This scenario is common in production. I follow a structured approach—check space, trace file growth, clean or archive. It shows my awareness of file systems, log management, and system recovery.

---

## ✅ 2. Scenario: CPU Usage is High

**Question:**  
A developer reports the application is very slow. You suspect high CPU usage. How do you investigate?

**Answer:**
```bash
top
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head
systemctl restart <servicename>
```

**Explanation:**  
I check system metrics using `top`, `ps`, and act based on the issue (e.g., looping process). This reflects hands-on troubleshooting and good decision-making in performance issues.

---

## ✅ 3. Scenario: Service Fails to Start

**Question:**  
A web service (e.g., Apache) fails to start on boot. How will you troubleshoot?

**Answer:**
```bash
systemctl status httpd
journalctl -xe
apachectl configtest
netstat -tuln | grep :80
```

**Explanation:**  
I approach this step-by-step: verify the service state, examine logs, validate config, and check port conflicts. It proves structured problem-solving with knowledge of systemd and networking.

---

## ✅ 4. Scenario: User Cannot Login via SSH

**Question:**  
A team member cannot SSH into a server. What steps would you take to resolve the issue?

**Answer:**
```bash
systemctl status sshd
id username
passwd -S username
ls -ld ~/.ssh
ls -l ~/.ssh/authorized_keys
tail -f /var/log/secure
```

**Explanation:**  
This checks for SSH service issues, user account problems, file permissions, and logs. It shows in-depth SSH knowledge and ability to handle real-time access issues securely.

---

## ✅ 5. Scenario: Crontab Not Working

**Question:**  
A scheduled backup script in crontab isn’t running. How do you debug it?

**Answer:**
```bash
crontab -l
systemctl status crond
grep CRON /var/log/cron
# Example cron job with logging
0 1 * * * /path/to/script.sh >> /tmp/backup.log 2>&1
```

**Explanation:**  
I verify cron syntax, service status, and logs. Adding logs to the script helps in debugging silently failing jobs. This shows my command over automation and job scheduling.


