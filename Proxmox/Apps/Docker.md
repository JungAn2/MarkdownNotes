> Best practice is to do it inside vm instead of container due to being more secured

[Documentation](https://docs.docker.com/engine/install/debian/)

# Debian

## Pre install
This only needs to be done if you have previously installed docker to prevent conflicting packages
```console
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

## Set up apt respository
- Install required repository
  ```console
  sudo apt-get update
  sudo apt-get install ca-certificates curl gnupg
  ```
- Official GPG key
  ```console
  sudo install -m 0755 -d /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
  sudo chmod a+r /etc/apt/keyrings/docker.gpg
  ```
- Setup repo
  ```console
  echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```
- update index
  ```console
  sudo apt-get update
  ```

## Install docker
```console
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
