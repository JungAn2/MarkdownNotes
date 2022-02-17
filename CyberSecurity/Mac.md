## Installation of Mac on proxmox
Note: Only this this for catelina. The site has one for upto Monterey

Website:
> https://www.nicksherlock.com/2020/04/installing-macos-catalina-on-proxmox-with-opencore/

## Required
- Mac iso (Google for it. Pretty sure there is an iso out there or follow the step in the website to fetch macOS from actual mac)
- Mac OSK key
> osk=ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc
The OSK apparenly appeared in the legal filed paper so it is already public
public Court document page 3 lines 16-17
> https://www.rcfp.org/wp-content/uploads/imported/20120105_202426_apple_sealing.pdf
- opencore
> https://github.com/thenickdude/KVM-Opencore/releases/

## Installation
### General
> Name your vm
### OS
> Select opencore iso
> Type -> Other
### System
> Graphics -> VMWare Compatible
> BIOS -> OVMF
> Machine -> Q35
> Tick "add EFI Disk"(If not already)
> untick "pre-enroll key" (For proxmox 7 and up)
### Disk
> Bus/Device -> SATA
> Tick "Discard"
### CPU
> Do what you want
### memory
> Do what you want
### Network
> model -> VMware vmxnet3

## Inside VM
### Options
> Ensure "use tablet for pointer" is set to yes
### Hardware
> add cd/DVD drive
> IDE:0 and add catalina iso

## Node _shell
### Edit
> /etc/pve/qemu-server/{vmid}.conf (vim or nano) I wasn't able to get vim working on my proxmox
>args: -device isa-applesmc,osk=ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc -smbios type=2 -device usb-kbd,bus=ehci.0,port=2
> If running Intel
    > -cpu host,kvm=on,vendor=GenuineIntel,+kvm_pv_unhalt,+kvm_pv_eoi,+hypervisor,+invtsc
> If amd
    > -cpu Penryn,kvm=on,vendor=GenuineIntel,+kvm_pv_unhalt,+kvm_pv_eoi,+hypervisor,+invtsc,+pcid,+ssse3,+sse4.2,+popcnt,+avx,+avx2,+aes,+fma,+fma4,+bmi1,+bmi2,+xsave,+xsaveopt,check

### Still edit
> Find ide0 and ide2
> Delete ",media=cdrom" and add ",cache=unsafe"

## Back to vm
### Option
> Change bootdisk -> ide2 first

To be continued....