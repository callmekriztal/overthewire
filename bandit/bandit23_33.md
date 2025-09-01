lvl 23

The password for bandit24 is hidden in /etc/bandit_pass/bandit24, but bandit23 cannot read it directly.

A cron job runs every minute as bandit24 and executes any scripts placed in /var/spool/bandit24/foo/.

This means you can sneak in your own script, and it will be executed with bandit24’s powers.

cat /etc/bandit_pass/bandit24 > /tmp/bandit_24pass.txt

The script should copy the secret from /etc/bandit_pass/bandit24 into a file in /tmp/, which you can read.

made it executable 
chmod +x hack.sh

After you make the script executable and wait one minute, the cron job will run it and delete the script.

Finally, open the file in /tmp/ to see the bandit24 password and log in.

lvl 24

a daemon is listening in the port 30002
we need connect and enter in format
pass_24 pincode
the pincode is said to be a number under 10000

used a script 

for i in {1000..9999}; do echo $i; echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i; done | nc localhost 30002

| nc .. means give the outputs to that port

echo $i looks useless if you only read the problem statement, but in practice it’s mandatory because the binary checks input in two steps:

First line = PIN
Second line = <password> <PIN>

lvl 25

use have a private key for bandit26 
used it to enter bandit26

ssh -i bandit26.sshkey bandit26@localhost -p 2220
now we need to enter the vim 
for that we recuced the screen size and entered v when it showed more note this way is used to enter vim through more

now 
: set shell=/bin/bash
: shell
entered the  bandit26, but you need the password for bandit27, which is stored in /etc/bandit_pass/bandit27.
Normally, you can’t read that file because only bandit27 has permission.
There’s a special helper program in your home directory called bandit27-do, which runs commands as the bandit27 user.
For example, ./bandit27-do id shows you the identity of bandit27, proving it runs as that user.
By running ./bandit27-do cat /etc/bandit_pass/bandit27, you execute cat as bandit27, so the file becomes readable.
The output is the password you need to log in as bandit27 for the next level.

lvl 27

we need to clone a github repo and cat the readme 

made a temp folder using 
mktemp -d
 git clone  ssh://bandit27-git@localhost:2220/home/bandit27-git/repo

 entered the password for 27
 cd repo 
 cat README
 got the password

lvl 28

