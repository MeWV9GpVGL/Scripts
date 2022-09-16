
## Recce Script



## Hardening Script

~~~
#!/bin/bash

flag="/home/debian/flag.txt"
user="debian"

dummy_functions=
"

sudo(){ exit ; }

netcat(){ exit ; }

nc(){ exit ; }

whoami(){ exit ; }

curl(){ exit ; }

wget() { exit ; }

fetch(){ exit ; }

ab(){ exit ; }

" 

echo $dummy_functions >> /home/$user/.bashrc

chattr +i /home/$user/.bashrc
chattr +i $flag


mv /bin/sudo /bin/lssu

mv /bin/netcat /dev/xcu1
mv /bin/whoami /dev/xcu2
mv /bin/chattr /dev/xcu3
~~~

## PowerShell FIM

~~~
# find the path to the desktop folder:
$Path = "C:\Users\e108093\Desktop\flag.txt"
$Flag = "blue"

while($true){
    $test = Get-Content -Path $Path
    if ($test -ne $Flag)
    {
        $Timestamp = Get-Date 
        Write-Host "BAD $Timestamp"
        $Flag | Out-File -FilePath $Path 
    }
}
~~~
