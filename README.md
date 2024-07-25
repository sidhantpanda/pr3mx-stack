# pr3mx's Home Server Stack

### Prequisites:
1. Valid VPN subscription (via PIA or NordVPN)
2. docker and docker compose installed
3. At least 20GB of free storage (this includes 1 FHD movie)

---

### Instructions:
1. Clone the repository
2. Copy the `.env.example` file to `.env` and fill in the required values
2. Run `docker compose up -d` in the root directory of the repository

---

### Set up:

#### Radarr:
1. Open radarr on `http://localhost:7878` or on a host on your network you deployed to
2. Set up default login access
3. Go to Settings -> Media Management -> Root Folders and add a new root folder with the path you selected in $COMMON_PATH in the `.env` file

#### Sonarr:
1. Open sonarr on `http://localhost:8989` or on a host on your network you deployed to
2. Set up default login access
3. Go to Settings -> Media Management -> Root Folders and add a new root folder with the path you selected in $COMMON_PATH in the `.env` file

#### Jellyfin:
1. Open jellyfin on `http://localhost:8096` or on a host on your network you deployed to
2. Set up default login access
3. Add the movies and shows libraries pointing the the volumes defined in docker compose

#### Jellyseerr:
1. Open jellyseer on `http://localhost:5055` or on a host on your network you deployed to
2. Use the Jellyfin login you set up in the Jellyfin step and use any email that you use. (Not sure what this is for, but is mandatory during set up)
3. Add radarr and sonarr services. The API keys for each of the service is in Settings -> General in the respective services.

#### Prowlarr:
1. Open prowlarr on `http://localhost:9696` or on a host on your network you deployed to
2. Set up default login access
3. Add the indexers you want to use
4. Set up radarr and sonarr in Settings -> Apps. Use `radarr` and `sonarr` has the respective host names.

#### References:
1. https://github.com/Morzomb/All-jellyfin-media-server
2. https://github.com/AdrienPoupa/docker-compose-nas/
3. https://www.reddit.com/r/docker/comments/14lbvth/servarr_one_docker_compose_file_to_rule_them_all/

