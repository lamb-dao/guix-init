# guix-init
This is a guix full system install speedrun. From standard guix iso, install
a pure GNU guix workstation with libre kernel which allows wired internet only,
from that base, onward to non-free full kernel (forgive me Stallman), wifi enabled nonguix lisp
based machine. The whole setup takes about 1 hour of effort, and 3-5 hours of
download. Be free!

# boot from USB
       reboot with standard guixSD iso flashed to stick
       at boot: [F12] to one time boot menu
       choose usb, uefi, secure boot off, (don't legacy boot, it ends badly)
       at blue language choice screen: [ctl][alt][F3] to TTY

# setup eth connection
       ifconfig -a #maybe eno1 or enp0s25
       ifconfig <the good one> up
       dhclient -v <the good one>
       ping -c 3 gnu.org

# clone init files
       guix install git vim screen
       cd ~
       git config --global http.sslVerify false
       git clone "https://github.com/lamb-duh/guix-init"
       #follow instructions.txt
