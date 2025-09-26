# Task 4 – Firewall Configuration with UFW

This task demonstrates basic firewall configuration on a Kali Linux VM using **UFW (Uncomplicated Firewall)**.

---

## Steps Performed

### 1. Check UFW status (before enabling)
`sudo ufw status numbered`

Output:

`Status: inactive`

### 2. Enable UFW
`sudo ufw enable`

Output:

`Firewall is active and enabled on system startup`

### 3. Verify status (after enabling)
`sudo ufw status numbered`

Output:

`Status: active`


### 4. Allow SSH (Port 22)
`sudo ufw allow 22/tcp`

Output:

`Rule added
Rule added (v6)`


### 5. Deny Telnet (Port 23)
`sudo ufw deny 23/tcp`

Output:

`Rule added
Rule added (v6)`


### 6. Test Telnet blocking with Netcat
`nc -vz 127.0.0.1 23`

Output:

`nc: connect to 127.0.0.1 port 23 (tcp) failed: Connection refused`


### 7. View firewall rules
`sudo ufw status numbered`

Output:

`[ 1] 22/tcp   ALLOW IN  Anywhere
[ 2] 23/tcp   DENY IN   Anywhere
[ 3] 22/tcp   ALLOW IN  Anywhere (v6)
[ 4] 23/tcp   DENY IN   Anywhere (v6)`


### 8. Remove the Telnet block rule
`sudo ufw delete 2`
`sudo ufw delete 3`


### 9. Final firewall rules
`sudo ufw status numbered`

Output:

`[ 1] 22/tcp   ALLOW IN  Anywhere
[ 2] 22/tcp   ALLOW IN  Anywhere (v6)`


## Summary

Enabled UFW firewall on Kali Linux.

Allowed SSH (22/tcp) to ensure remote access.

Denied Telnet (23/tcp) and verified with Netcat that connections were blocked.

Removed the Telnet block rule successfully.

This demonstrates the ability to configure, test, and manage firewall rules with UFW.
