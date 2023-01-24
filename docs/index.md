# Config Media Management With Plex

## Presentation

My setup is made of different types of tools. 
Each are presented bellow. 

### Automatic Finders  
Automatic finders are tools which can automatically find torrent files for movies and series. 
You initiate a search on these tools, they find a downloadable file from index managers (bellow) and send a request to your download utility. 
Once the file is downloaded, the tool will move the file to your media location and name it properly. 

- <a href="https://github.com/Radarr/Radarr" target="_blank">:camera: **Radarr**</a> Movie download utility
- <a href="https://github.com/Sonarr/Sonarr" target="_blank">:tv: **Sonarr**</a> TV Shows download utility


### Index Managers  
Index managers allow referencing various torrent providers. 
They are used by automatic finders to send requests to all configured providers easily. 

- <a href="https://github.com/Jackett/Jackett" target="_blank">:bar_chart: **Jackett**</a> Indexer manager for automatic download utilities
- <a href="https://github.com/Prowlarr/Prowlarr" target="_blank">:bar_chart: **Prowlarr**</a> Indexer manager for automatic download utilities


### Other  
Other types of tools are used in the setup. 

- <a href="https://github.com/haugene/docker-transmission-openvpn" target="_blank">:floppy_disk: **Transmission**</a> Download utility
- <a href="https://github.com/morpheus65535/bazarr" target="_blank">:speech_balloon: **Bazarr**</a> Subtitles manager
- <a href="https://github.com/sct/overseerr" target="_blank">:movie_camera: **Overseerr**</a> Request manager
- <a href="https://github.com/FlareSolverr/FlareSolverr" target="_blank">:mag: **FlareSolverr**</a> Cloudflare bypass


## Global setup  

For now, the whole system rests on a synology NAS. 

### Server Specs 

 - Synology NAS **DS920+**
 - 2x 8Go RAM Modules
 - 4x 8To Seagate IronWolf 

### Architecture 

 - **Plex** from Synology Package 
 - **Docker** from Synology Package 
 - **Other Tools** as Docker Containers 
 - **Nginx Proxy Manager** for proxy 


## Find the detailed configuration of each tool below

 - Plex
 - [Servarr containers](servarr-containers)
 - Jackett
 - Transmission with Open VPN
 - Overseer (?) 


## Roadmap

- [ ] 
- [ ] Add a section for each tool
- [x] Write global setup
- [ ] Write the roadmap
init
- [x] Init the project
