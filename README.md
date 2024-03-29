# Troubleshooting Guide

# Linux

#Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it
Enter following line to find the process ID:

lsof /var/lib/dpkg/lock-frontend
Then run this command with the PID that it revealed:

kill -9 PID

#The following signatures couldn't be verified because the public key is not available:

apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 505D97A41C61B9CD

# Zabbix
### postgresql missing chunk number
-->login to postgresql DB and query:

reindex index history_1;

reindex index history_uint_1;

reindex table pg_toast.pg_toast_2619;
