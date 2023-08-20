> Require docker to be installed

[Documentation](https://docs.portainer.io/start/install-ce/server/docker/linux)

# Debian

Require two simple console command
```console
docker volume create portainer_data
```

```console
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
