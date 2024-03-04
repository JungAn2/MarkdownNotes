> This is how to install dashy from portainer

[Documentation](https://www.addictedtotech.net/install-dashy-dashboard-using-portainer-and-docker-on-a-raspberry-pi-4-episode-30/)

## Inside shell
- Create a directory wherever you like
  > /root/docker/dashy
- Create a yml file
  ```console
  touch conf.yml
  ```
- add default info to the conf.yml
  ```
  ---
  # Page meta info, like heading, footer text and nav links
  pageInfo:
    title: Dashy
    description: Welcome to your new dashboard!
    navLinks:
    - title: GitHub
      path: https://github.com/Lissy93/dashy
    - title: Documentation
      path: https://dashy.to/docs
  
  # Optional app settings and configuration
  appConfig:
    theme: colorful
  
  # Main content - An array of sections, each containing an array of items
  sections:
  - name: Getting Started
    icon: fas fa-rocket
    items:
    - title: Dashy Live
      description: Development a project management links for Dashy
      icon: https://i.ibb.co/qWWpD0v/astro-dab-128.png
      url: https://live.dashy.to/
      target: newtab
    - title: GitHub
      description: Source Code, Issues and Pull Requests
      url: https://github.com/lissy93/dashy
      icon: favicon
    - title: Docs
      description: Configuring & Usage Documentation
      provider: Dashy.to
      icon: far fa-book
      url: https://dashy.to/docs
    - title: Showcase
      description: See how others are using Dashy
      url: https://github.com/Lissy93/dashy/blob/master/docs/showcase.md
      icon: far fa-grin-hearts
    - title: Config Guide
      description: See full list of configuration options
      url: https://github.com/Lissy93/dashy/blob/master/docs/configuring.md
      icon: fas fa-wrench
    - title: Support
      description: Get help with Dashy, raise a bug, or get in contact
      url: https://github.com/Lissy93/dashy/blob/master/.github/SUPPORT.md
      icon: far fa-hands-helping
  ```
- Get the absolute path
  ```console
  pwd
  ```

## Portainer
- Go to local and go to stack on the left side
- Add a new stack
- Enter the following
  ```
  ---
  version: "2.1"
  services:
    dashy:
      image: lissy93/dashy
      container_name: Dashy
      volumes:
        - /PATHTOAPPDATA/DASHY/conf.yml:/app/public/conf.yml
      ports:
        - 4000:80
      environment:
        - NODE_ENV=production
        - UID=1001
        - GID=100
      restart: always
  ```
  > /PATHTOAPPDATA/DASHY/ should be replace with the abolute path
- Deploy
