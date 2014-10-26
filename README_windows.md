Problems you might have when trying this with Windows 7 64
==========================================================
[1]: http://www.microsoft.com/en-us/download/details.aspx?id=40855 "Powershell"
[2]: https://www.virtualbox.org/wiki/Download_Old_Builds "VirtualBox Old Builds"
[3]: https://plus.google.com/u/0/+MichaelBladowski/about "A desperate windows user"

1. If "vagrant up" hangs at "checking if box if up to date..." or while trying to setup the port forwardings,
install latest [Powershell][1]. 

2. If vagrant is unable to connect to VM via SSH, try install an older version of VirtualBox, e.g. [VirtualBox-4.3.12-93733-Win.exe][2]

3. If you have probems building the tutorial, like "nmp install", you might have problems with symlinks inside your mounted folders. In this case, *don´t use the shared folders by vagrant!* 
  - create a new folder inside the vm, e.g. /home/vagrant/plan9local
  - put all code here, do all checkouts, builds, whatever only here!
  - install samba (aptitude install samba)
  - add samba user (smbpasswd -a vagrant)
  - add share: edit /etc/samba/smb.conf, add:

```
[home]
public = no
create mode = 0777
writeable = yes
path = /home/vagrant/
browsable = yes
```

  - add windows network drive, use IP of your VM (eth1, host-only), e.g. \\192.168.42.2\home\ username: vagrant, password: you have choosen with smbpasswd
  
so after this, you should have a mounted linux folder inside you windows host, and *NOT* a windows folder, mounted inside the VM, beause thats the way you should do it when working with windwows ;)

Best regards,
[Michael Bladowski][3]
