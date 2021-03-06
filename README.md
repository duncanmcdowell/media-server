# media-server
Turn-key media server including Plex, Transmission, Radarr and Sonarr deployed via docker


## Config

- The docker-compose file currently assumes that media storage is mounted on `/media/external`
- Sonarr and radarr currently depend on accessing tranmission through its external network ip (and not the internal docker ip of 0.0.0.0). This will need to be tested and adjusted on each new server deploy.

## First run

- install [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-using-the-repository/)
- create a [Plex accout](https://www.plex.tv/)
- clone this repository
- create a user for the media server, add `$USER_ID` and `$GROUP_ID` variables to the appropriate place in the included `.env` file. (or use user id)
- create a media folder in docker-compose's folder with $USER_ID:$GROUP_ID ownership
- get your Plex claim token at https://www.plex.tv/claim/ (optional, if using, add to `.env` file as `PLEX_TOKEN`, and add `PLEX_CLAIM="${PLEX_TOKEN}"` to the environment variables under the plex configuration in `docker-compose.yaml`)
- run `docker-compose up -d`
- enjoy :)

## Pi-hole and Unifi

- In Pi-hole, under Settings -> DNS, turn on Conditional Forwarding with the IP of your router as the USG, and Local domain name your local domain name (localdomain).
- Let the USG continue to do DHCP as before, but set DHCP Name Server to the Pi-hole IP.
- In USG, under Services -> DHCP -> DHCP Server, be sure Register client hostname from DHCP requests in USG DNS forwarder is On.

