# Servarr Containers 

Radarr, Sonarr, Bazarr, Prowlarr and FlareSolverr are tools collectively refered to as "*Arr" or "*Arrs". 
They are maintained under the Github organization [Servarr](https://github.com/Servarr). 

As they are all maintained by the same team, the process for installation is very similar. 

## General Idea 

## Docker deployment 

### Deploy with docker-compose 

``` yaml
version: "3.9"  

services:
  
  bazarr: # Bazarr
    image: [image] # (1)!
    container_name: [Your-Container-Name] # (2)!
    ports:
      - "[out-port]:[app-port]"  # (3)!
    volumes: # (4)!
        # Examples: 
      - "/volume1/Medias Lib/Movies:/movies"
      - "/volume1/Medias Lib/TV Shows:/tv"
      - "/volume1/docker/bazarr:/config"
    environment: 
      PUID: 1026 # (5)!
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

1.  :man_raising_hand: Enter here the name of the image you need  
    Find bellow the different available images!  
2.  :material-rename-outline: Enter here the name you want for your container   
    :warning: No spaces!  
3.  :material-access-point-network: Enter the port mappings  
    **On the left** the port your container will have on your server   
    **On the right** the port the app inside the container is using     
4.  :material-server: Here are examples of volumes mappings  
    Find bellow which volume are needed for your image!  
5.  :fontawesome-solid-user: You need to map user credentials with your account   
    In ssh console type in `id` and get the values for **PUID** and **GUID**  


### Docker Images & Volume Mappings

Find here a list of all the Docker images: 

- **Radarr**: [linuxserver/radarr](https://hub.docker.com/r/linuxserver/radarr){target=_blank} 
  > Required mappings:  
  >
  > - `/path/to/data:/config`
  > - `/path/to/movies:/movies` #optional  
  > - `/path/to/downloadclient-downloads:/downloads` #optional  
- **Sonarr** 


## App configuration 

## Global 