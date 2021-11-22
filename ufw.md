# Lets do a basic firewall for a server

### Typical ports (https://www.examcollection.com/certification-training/network-plus-overview-of-common-tcp-and-udp-default-ports.html)
    22 SSH
    25 SMTP
    53 DNS
    80 HTTP
    443 HTTS
    
    ? Mysql

### UFW basics https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands

_**UFW install**_

    sudo apt update && sudo apt install ufw

_**UFW status**_

    sudo ufw status
    sudo ufw status verbose
    
   _**Listing Rules in Number Sequence:**_
   
    Listing rules in number sequence makes it easier to manage rules.

    sudo ufw status numbered 
   
    
  _**Enabling UFW**_  
      
      sudo ufw enable
    
  _**Disabling UFW**_  
    
    sudo ufw disable
    
    

_**UFW command syntax**_

    _sudo ufw allow <port>/<optional: protocol>_
    sudo ufw allow 53
    sudo ufw allow 53/tcp
    sudo ufw allow 53/udp

_**Working with numbered rules**_
    
    sudo ufw status numbered

_**UFW App list**_

    sudo ufw app list
    sudo ufw allow “OpenSSH”


_**Allow Incoming SSH from Specific IP Address or Subnet**_

    sudo ufw allow from 203.0.113.103 proto tcp to any port 22
    sudo ufw allow from 203.0.113.0/24 proto tcp to any port 22


_**ABlock Outgoing SMTP Mail**_
    
    sudo ufw deny out 25



_**Simplefy UFW rules**_
    
    sudo ufw status numbered
    sudo ufw delete 1
