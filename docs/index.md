# Config Media Management With Plex

## Presentation

My setup is made of: 

Automatic Finders:
- <a href="https://github.com/Radarr/Radarr" target="_blank">:camera: **Radarr**</a> Movie download utility
- <a href="https://github.com/Sonarr/Sonarr" target="_blank">:tv: **Sonarr**</a> TV Shows download utility

Index Managers:
- <a href="https://github.com/Jackett/Jackett" target="_blank">:bar_chart: **Jackett**</a> Indexer manager for automatic download utilities
- <a href="https://github.com/Prowlarr/Prowlarr" target="_blank">:bar_chart: **Prowlarr**</a> Indexer manager for automatic download utilities

Other: 
- <a href="https://github.com/haugene/docker-transmission-openvpn" target="_blank">:floppy_disk: **Transmission**</a> Download utility
- <a href="https://github.com/Bazarr/Bazarr" target="_blank">:speech_balloon: **Bazarr**</a> Subtitles manager
- <a href="https://github.com/Overseerr/Overseerr" target="_blank">:movie_camera: **Overseerr**</a> Request manager
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
 - **Ngninx Proxy Manager** for proxy 


## Find the detailed configuration of each tool below
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
