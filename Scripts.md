
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
#$Path = "C:\Users\e108093\Desktop\flag.txt"
#$Flag = "blue"
$Path = $args[0]
$Flag = $args[1]
# $WriteDir = "C:\Windows\WinSxS\amd64_c_smartcardpd.inf.resources_31bf3856ad364e35_10.0.17763.1_en-us_6470c67a0dd3127b"
$WriteDir = "C:\Users\e108093\Documents\log\"
$WriteFile = "c_smartcardpd.inf_loc"

New-Item $WriteDir -Type Directory
New-Item -Path $WriteDir -Name $WriteFile -ItemType "file"

while($true){
    $test = Get-Content -Path $Path
    if ($test -ne $Flag)
    {
        $Timestamp = Get-Date 
        Write-Host "$Timestamp"
        Add-Content -Path $WriteDir$WriteFile -Value "$Timestamp"
        $Flag | Out-File -FilePath $Path 
    }
}
~~~
