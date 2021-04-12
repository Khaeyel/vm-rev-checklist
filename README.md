#If your task is as undefined as "keep them running":

    * Work with what your stakeholders want from you or the VM, or from what you can find on the VM

    * Ask the previous admin, or "power" users that understand what the VM did

    * Recreate the VM from the most recent backup that exists. If there's no backup, then create one. If there is a backup, compare the differences between it and what is live. 

    * Ask your stakeholders about acceptable downtimes, and make sure to have ample down time during the first week; no one should rely too heavily on a 95% uptime for such a VM - disappoint those expectations early. 

    * Users: the contents of /home, /root, the bottom of /etc/group and /etc/passwd. Which users are able to login, or use sudo, or have interesting group memberships? Use last to see past logins. Age/expire/disable passwords to lock out inactive users. 

    * Services: netstat -a, iptables -L , nmap from a different host, ps axu. Disable servers and wait for people to complain (AKA scream test). And do look at servers and user as a potential attack vector. Additionally, check crontab. 

    * Forward all network traffic via a dedicated new machine and monitor what's going on. 

    * Installed software: dpkg -l, contents of /*/local, examine the $PATH of root and every interactive user. 

    * compare directory hierarchies to a freshly installed Debian/CentOS/flavor. Compare users' homer directories to /etc/skel. 

    * Find files with a recent modification or creation date 

    * Check the contents of /tmp, /var/run, /var/cache 

    * Communicate to the stakeholders that a pet/manually run VM is unsatisfactory, and explain the risks. If they don't bother too much, it may not be worth your time to replace the server, but you still need to communicate the risks and maybe cover your back. Do not accept too much responsibility for something you didn't set up, has no documentation, etc.
