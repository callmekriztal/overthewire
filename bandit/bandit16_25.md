lvl 16

thhe password of 16 shoulld be submitted to a port 
on the localhost in thee rangge 31000 to 32000

out of them find the one speaks ssl which will give credentials 
others will  just send back we send

nmap localhost -p 31000-32000
PORT      STATE SERVICE

31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

 nmap localhost -p 31046,31518,31691,31790,31960 -sV -T4

 PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo

ie.315158 and 31790 speaks ssl

openssl s_client -connect localhost:31518
openssl s_client -connect localhost:31790

openssl didn't worked sue to some  reasons

used 
ncat --ssl localhost 31790

entered the password 
gor private key 

loged to lvl 17
with 
ssh -i private.key  bandit17@bandit localhost -p 2220

lvl 17

we  have two files passwords.new and passwords.old
the pswd for next level is the only line which is different in both the files

used 
diff passwords.old passwords.new
got lvl 18 password

lvl 18

couldnt login 
did ssh command injection to find 

sshpass -p $(cat 18) ssh bandit18@bandit.labs.overthewire.org -p 2220 ls

and read readme

sshpass -p $(cat 18) ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

got the pswd  for 19 

lvl 19

We got a setuid file owned by bandit20.
Because of the s (setuid) permission, when we run ./bandit20-do, it executes with bandit20’s privileges instead of our own.

That’s why running 
./bandit20-do cat /etc/bandit_pass/bandit20 
lets us read the file, even though normally bandit19 could not.

Notice the s in the owner’s execute bit → setuid.

That means:

When bandit19 executes this file, it doesn’t run with bandit19’s privileges.

Instead, it runs with the owner’s privileges (bandit20).

So the program runs as if bandit20 is executing it.

lvl 20


