# Kickstart
Kickstart templates

# Install steps
 1. Boot in rescue mode
 2. Connect on the rescue machine while sharing port 5900 (for VNC), eg. ssh root@remotehost -L 5900:localhost:5900
 2. On the rescue machine, download the image to install. eg. **curl -LO "https://download.fedoraproject.org/pub/fedora/linux/releases/29/Server/x86_64/iso/Fedora-Server-netinst-x86_64-29-1.2.iso"**
 3. Start qemu, eg. **qemu-system-x86_64 -net nic -m 1024M -localtime -enable-kvm -hda /dev/sda -hdb /dev/sdb -vnc 127.0.0.1:0 -cdrom Fedora-Server-netinst-x86_64-29-1.2.iso -boot d** 
 4. Connect on local machine with **vncviewer localhost:5900**
 5. Tap tab to see the command line, and use : **vmlinuz initrd=initrd.img inst.ks=https://raw.githubusercontent.com/devops-now/kickstart/master/f29-ovh.cfg**
