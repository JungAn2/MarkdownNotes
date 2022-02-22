## Installabtion of metasploitable on proxmox

Youtube video by Koroma Tech
> https://www.youtube.com/watch?v=d9PD5KHTWgo

- create a vm(remember vmid), next
- Do not use any media, next
- System default, next
- harddrive changed bus IDE, next
- CPU default, next
- Memory default, next
- Network
> Ideally you don't want network on it since it is very vulnerable.
> If one does decide to turn on the network, turn off the vm when not in use.


- go to node shell
- cd /var/lib/vz/image/
- mkdir {vmid}
- cd {vmid}
- wget https://newcontinuum.dl.sourceforge.net/project/metasploitable/Metasploitable2/metasploitable-linux-2.0.0.zip
> if unzip is not installed
> do apt install unzip
- unzip metasploitable-linux-2.0.0.zip
- cd into unzipped Metasploitable folder

Convert Metasploitable.vmdk to qcow2 for proxmox to understand
- while inside the Metasploitable folder
> qemu-img convert -f vmdk Metasploitable.vmdk -O qcow2 Metasploitable.qcow2
- move one folder up
> mv Metasploitable.qcow2 ../

if a Error:storage 'local' does not support content-type 'images' appear,
- Go to datacenter, local or where vzdump file is
  - edit to accept disk image

At this point you can just detele the zip and the folder
- Sadly vim is not on there so you have to use nano to change config
> nano /etc/pve/qemu-server/{vmid}.conf
- in ide0: {harddrive}:vm-{vmid}-disk-0, size=32G
> ide0: file=local:{vmid}/Metasploitable.gcow2, size=32G
