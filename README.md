# Filebeat-7.x-Privilege-Escalation
It has been quite few times I have seen Filebeat running as root and capable of running it as root (suid or NOPASSWD).  In fact, the documentation suggests to run filebeat as sudo. https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-starting.html

Here the steps to leverage the filebeat to obtain a shell as root. (arbitrary write in the filesystem).

The following exploit.yml is meant to add the "attacker ssh" key to the authorized_keys file.


Dowload the file exploit.yml.

1) Save your public key in the following file /tmp/attackerkey. 
2) Run the follwowing command  sudo ./filebeat -c exploit.yml
3) Enjoy your key added to /root/.ssh/authorized_keys


Thank you.

