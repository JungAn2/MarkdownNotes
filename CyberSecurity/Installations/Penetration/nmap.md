# Nmap notes

Learning youtube NetworkChuck:
https://www.youtube.com/watch?v=4t4kBkMsDbQ

used for scanning network
- find live host(hackable target)
- more information regarding targets
- process enumeration

easy way to check if one device is live
- ping {ip address}

Find whole network is live
- nmap -sP {network} (ex. 255.255.255.255/24)

sudo nmap -sT -p 80,443 {network}
- -st stands for TCP connect(full open scan)
- -p 80,443: port 80 and 443
> Note
> This provided little information for my system.
> All the ports were all filtered due to probably my router
> Filtered state: "Nmap cannot determine whether the port is open because packet filtering prevents its probes from reaching the port. The filtering could be from a dedicated firewall device, router rules, or host-based firewall software."

sudo nmap -sS -p 80,443 {network}
- Stealth scan
- Syn scan / Half-open scan