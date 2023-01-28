# Transmission

For my setup, I deployed Transmission torrent downloader with a connection going through a VPN with NORD VPN. 

The setup used is from [Haugene Transmission OpenVPN repo](https://github.com/haugene/docker-transmission-openvpn){target=_blank}.  
The [docker Image](https://hub.docker.com/r/haugene/transmission-openvpn){target=_blank}. 

## Docker Compose 

```yaml 
version: '3.3'

services:
  transmission:
    image: haugene/transmission-openvpn:latest
    container_name: Transmission-OpenVPN # (1)!
    restart: unless-stopped
    cap_add:
      - NET_ADMIN
    ports:
      - 30001:9091  # (2)! 
      - 8888:8888 # web-proxy
    environment:
      LOCAL_NETWORK: 192.168.1.0/24
      OPENVPN_CONFIG: de15.nordvpn.com # (3)! 
      OPENVPN_USERNAME: # (4)! 
      OPENVPN_PASSWORD: # (5)! 
      OPENVPN_PROVIDER: NORDVPN # PIA or etc # (6)! 
      CREATE_TUN_DEVICE: true
      TRANSMISSION_WEB_UI: flood-for-transmission # (7)! 
      TZ: Europe/Paris
      # (8)! 
      TRANSMISSION_DOWNLOAD_DIR: /data/Data 
      TRANSMISSION_HOME: /data/transmission-home
      TRANSMISSION_INCOMPLETE_DIR: /data/Incomplete
      TRANSMISSION_WATCH_DIR: /data/TorrentFiles
    volumes: # (9)! 
      - /volume1/docker/transmission-openvpn/resolv.conf:/etc/resolv.conf:ro # use to stop dns-leak
      - /volume1/Downloads:/data
      - /volume1/docker/transmission-openvpn:/config
    network_mode: bridge
```

1.  :material-rename-outline: Enter here the name you want for your container   
    :warning: No spaces!  
2.  :material-access-point-network: Transmission web UI port is 9091  
    It is here mapped to 30001  
    Use http://nas-ip:30001 to access ui from local network  
3.  Name of the opvn config file for VPN connexion   
    File must be uploaded at: `/volume1/Docker/transmission-openvpn`  
    If the file name is `de15.nordvpn.com.ovpn` use `de15.nordvpn.com`  
4.  Enter your username
5.  Enter your password
6.  See [documentation page](https://haugene.github.io/docker-transmission-openvpn/supported-providers/){target=_blank}
7.  Choose your UI  
    Your options are:  
    - Combustion UI  
    - Kettu  
    - Transmission-Web-Control  
    - Flood for Transmission  
    - Shift  
    
    *Write the name replacing spaces with "-"*.   

8.  Set the folder mappings  
9.  Map your volumes  
    You need at least two:  
    - /data  
    - /config  

    