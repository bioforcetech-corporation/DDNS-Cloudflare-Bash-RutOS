# Configurare RutOS per lanciare lo script

ln -s /proc/self/fd /dev/fd
opkg update
opkg install nano
ln -s /usr/lib/libncurses.so /usr/lib/libncurses.so.5
ln -s /usr/lib/libncurses.so.6 /usr/lib/libncurses.so
opkg install bash
nano /etc/passwd                                    // cambiare root shell da /bin/ash a /bin/bash

nano update-cloudflare-dns.conf         // da settare con parametri corretti ogni volta
nano update-cloudflare-dns.sh
chmod +x update-cloudflare-dns.sh

nano ~/.bash_profile
// scriverci dentro: export VISUAL="nano"
. ~/.bash_profile                                      // ricarica il profilo opzioni bash

crontab -e
// appendere: * * * * * /bin/bash /root/update-cloudflare-dns.s