#Kill anything still running
pkill -f playit

#Create a local working directory
mkdir -p ~/playit-local && cd ~/playit-local

#Start the daemon with a local socket
/usr/bin/playitd --socket-path=./playit.sock --secret-path=./playit.toml &

#Wait 2 seconds, then connect the client
sleep 2
playit --socket-path=./playit.sock