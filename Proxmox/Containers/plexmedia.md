# Table of content
- [Installation](#installation)
- [plugin](#plugin)

<a id='installation'></a>
# Installation of Plex in container

## This instruction is same as intalling in debian or ubuntu linux
- Website Instruction at [Here](https://pimylifeup.com/ubuntu-plex-media-server/)

## Setup plex repo
### Root account
```
apt update
apt install curl
curl https://downloads.plex.tv/plex-keys/PlexSign.key | gpg --dearmor | tee /usr/share/keyrings/plex-archive-keyring.gpg >/dev/null
echo deb [signed-by=/usr/share/keyrings/plex-archive-keyring.gpg] https://downloads.plex.tv/repo/deb public main | tee /etc/apt/sources.list.d/plex.list
apt update
apt install plexmediaserver
```

---

### sudo account
```
sudo apt update
sudo apt install curl
curl https://downloads.plex.tv/plex-keys/PlexSign.key | gpg --dearmor | sudo tee /usr/share/keyrings/plex-archive-keyring.gpg >/dev/null
echo deb [signed-by=/usr/share/keyrings/plex-archive-keyring.gpg] https://downloads.plex.tv/repo/deb public main | sudo tee /etc/apt/sources.list.d/plex.list
sudo apt update
apt install plexmediaserver
```

---

<a id='plugin'></a>
# Add plugin
```
cd /var/lib/plexmediaserver/Library/Application Support/Plex Media Server/Plug-ins
```
- move the folder with plug-in to the file
- cp /mnt/media/zPlexPlugin/DaumMovie.bundle ./
