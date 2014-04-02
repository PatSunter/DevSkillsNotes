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
 * One quick way to get access to automounted folders in /media:
   run "sudo usermod -a -G vboxsf username" where username is your username on the VM,
   to get added to the appropriate group.

Refs:
 * http://forums.virtualbox.org/viewtopic.php?t=15868

Need to re-initialise network stuff before/after cloning
--------------------------------------------------------

For Ubuntu machines - otherwise its very slow to boot and is waiting on network stuff...

Either:
 * before cloning:
    sudo rm -f /etc/udev/rules.d/70-persistent-net.rules
 * Or after cloning, on the clone, do the same.

Refs:
 * http://askubuntu.com/questions/82322/how-do-i-fix-broken-networking-in-cloned-virtual-machines

Setting up a new Ubuntu server in Vbox:
---------------------------------------

My preferred sources of pre-built VirtualBoxes
""""""""""""""""""""""""""""""""""""""""""""""

http://virtualboxes.org/images/ubuntu-server/


Basic Ubuntu server setup
"""""""""""""""""""""""""

To make more user-friendly, keyboard, mouse stuff:-
 * sudo dpkg-reconfigure keyboard-configuration

Refs:
 * http://askubuntu.com/questions/155424/changing-tty-keyboard-layout-on-a-server

