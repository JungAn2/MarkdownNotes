
# Installation of Windows on Proxmox

Youtube video by Techno Tim

> https://www.youtube.com/watch?v=6c-6xBkD2J4

## Best practices website
Read this, For each windows have different configuration (after windows 7)
> https://pve.proxmox.com/mediawiki/index.php?search=best+practices&title=Special%3ASearch&go=Go

For any windows before window 7,
On network make sure to set model to virtos and add cd drive to the vm to add virtos iso

## For windows 11
while making the vm
- System
> Enable Qemu agent
>	- Enable TPM(trusted platform module)
> 	- For more info on windows 11 for proxmox
>  		- https://www.youtube.com/watch?v=fupuTkkKPDU

## Need iso and virtio

- Download iso of the window version needed
- Download virtio
> website https://github.com/virtio-win/virtio-win-pkg-scripts/blob/master/README.md

# For windows8.1 following the best practices
## Proxmox create vm

- General
> Nothing to change. Just give name

- OS
> Choose the windows iso. Change Guest OS to windows and the version

- System
> Enable Qemu agent

- Harddrive
> bus/Device -> SCSI
> Cache option -> Write back
> Enable discard underneath Cache option

- CPU
> Nothing to change.

- Memory
> Nothing to change.

- Network
> Change Model -> Virtio(paravirtualization)

### configure vm for window

- From the node that is created
- go to hardware
- add CD/DVD Drive
- bus/device IDE
- put virtos iso image

## While installing

- While installing, no driver will be displayed (windows 7 & up??)
> windows xp detected the driver on its own

- Browse to cd drive: virtso win

- Folder vioscsi(scsi)
- 8.1 amd64

- Folder NetKVM(network)
- 8.1 amd64

- Folder Balloon(memory)
- 8.1 amd64
  

With this method was able to install windows xp and windows 8.1

Not sure if it's my windows 7 iso, but the virtio driver for vioscsi/balloon did not work for 64 and using balloon 84 gave me the blue screen.