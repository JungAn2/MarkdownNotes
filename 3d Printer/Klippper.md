# Getting klipper on proxmox

## [youtube instruction by modbot](https://www.youtube.com/watch?v=Ib1Dd3rIE2I)

## Steps
- Start up Ubuntu-22 container
- Install git: ```apt install git```
- login to root and create new user: ```adduser <username>```
- enter password and just enter through rest or fill out
- give user sudo```usermod -aG sudo <username>```
- logout and login as the user (the installation tool has to be non root account)
- Clone the installation tool from th33xitus 
```
cd ~
git clone https://github.com/th33xitus/kiauh.git
./kiauh/kiauh.sh
```

- first install klipper by 1, 1, and install with python 3.x (ubuntu-22 comes with python 3.10)
- the instance depends on how many printers you have

- Once done install the moonracker by entering 2
  - make sure to remember the IP address it returns when it finishes installing

- Then choose one of the three mainsail, moonracker, octoprint and install
