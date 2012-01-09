
Setup of Shared folders with Host OS
------------------------------------

 * Specify the shared folder in VirtualBox
   (either storage options, or in the Devices/Shared Folders menu in a
    VM instance)
 * In the VM, Set that folder to be automounted each login:
   * mkdir directory you want to mount to
   * Add relevant text to /etc/rc.local:
     mount -t vboxsf share /home/<username>/host
   * You might want to add relevant perms options at end of above lines, eg "
     -o uid=myuser,gid=myuser

Refs:
 * http://forums.virtualbox.org/viewtopic.php?t=15868

