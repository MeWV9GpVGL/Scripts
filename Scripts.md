
## Recce Script



## Hardening Script

~~~
#!/bin/bash

flag=/home/debian/flag.txt

chattr +i flag

dummy_functions=

"

function sudo () 
{ 
	exit
}

function netcat ()
{
	exit
}

function nc ()
{
	exit
}

function whoami
{
	exit
}

" 

dummy_chattr=

"
function chattr
{
	exit
}

"


echo bash_functions >> /home/$user/.bashrc


chattr +i /home/$user/.bashrc
chattr +i /home/


mv /bin/sudo /proc/3/lssu
mv /bin/netcat /proc/3/xstat
mv /bin/whoami /proc/3/itr
mv /bin/chattr /proc/3/uconv
~~~
