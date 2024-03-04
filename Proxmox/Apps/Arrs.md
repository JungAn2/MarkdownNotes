# Arrs setup

> My setup is using debian 12

[All the documentation on how to install Arrs](https://wiki.servarr.com/)

> Going in order of what should be installed.

> Prowlarr can be replaced with jackett (I have not tried)

# Prowlarr

[Instruction](https://wiki.servarr.com/prowlarr/installation)

IP of the server
```
http://{Your server IP Address}:9696
```

> Prerequisite
``` bash
sudo apt install curl sqlite3
```

> at this point create a user with prowlarr and a prowlarr.
> Depending no what debian you have you mght have to install adduser
``` bash
sudo apt-et install aduser
```

> This will automatically create a group called the user
``` bash
sudo adduser prowlarr
```

- You can determine your architecture with dpkg --print-architecture
- AMD64 use arch=x64
- ARM, armf, and armh use arch=arm
- ARM64 use arch=arm64

``` bash
wget --content-disposition 'http://prowlarr.servarr.com/v1/update/master/updatefile?os=linux&runtime=netcore&arch=x64'
```

``` bash
tar -xvzf Prowlarr*.linux*.tar.gz
```

``` bash
sudo mv Prowlarr/ /opt
```

``` bash
sudo chown prowlarr:prowlarr -R /opt/Prowlarr
```

- This will configure autostart at boot
``` bash
cat << EOF | sudo tee /etc/systemd/system/prowlarr.service > /dev/null
[Unit]
Description=Prowlarr Daemon
After=syslog.target network.target
[Service]
User=prowlarr
Group=prowlarr
Type=simple

ExecStart=/opt/Prowlarr/Prowlarr -nobrowser -data=/var/lib/prowlarr/
TimeoutStopSec=20
KillMode=process
Restart=on-failure
[Install]
WantedBy=multi-user.target
EOF
```

- reload the systemd
``` bash
sudo systemctl -q daemon-reload
```

- enable prowlarr
``` bash
sudo systemctl enable --now -q prowlarr
```



# Radarr
- Radarr is a movie automation downloader.