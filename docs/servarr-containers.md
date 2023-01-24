# Servarr Containers 

Radarr, Sonarr, Bazarr, Prowlarr and FlareSolverr are tools collectively refered to as "*Arr" or "*Arrs". 
They are maintained under the Github organization [Servarr](https://github.com/Servarr). 

As they are all maintained by the same team, the process for installation is very similar. 

## General Idea 

## Docker deployment 

### Deploy with docker-compose 

```yml 
version: "3.9"  

services:
  
  bazarr: # Bazarr
    image: [image]
    container_name: [Your-Container-Name]
    ports:
      - "[out-port]:[app-port]"
    volumes:
        # Examples: 
      - "/volume1/Medias Lib/Movies:/movies"
      - "/volume1/Medias Lib/TV Shows:/tv"
      - "/volume1/docker/bazarr:/config"
    environment:
      PUID: 1026
      GUID: 100
      HOME: /root
      LANG: en_US.UTF-8
      LANGUAGE: en_US.UTF-8
      PATH: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
      PS1: $$(whoami)@$$(hostname):$$(pwd)\$$
      S6_CMD_WAIT_FOR_SERVICES_MAXTIME: 0
      TERM: xterm
      TZ: Europe/Paris
      XDG_CONFIG_HOME: /config/xdg
    network_mode: bridge

```


## App configuration 

## Global 