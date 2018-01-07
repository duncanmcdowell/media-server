# media-server
Turn-key media server including Plex, Transmission, Radarr and Sonarr deployed via docker

## Prep

- Assmemble NUC
- install Ubuntu (flash USB stick if necessary)
- install SSH: `sudo apt-get install openssh-server`
- partition and format external drive [(if applicable)](https://askubuntu.com/questions/384062/how-do-i-create-and-tune-an-ext4-partition-from-the-command-line#answer-811954)

## Config

- The docker-compose file currently assumes that media storage is mounted on `/media/external`
- Sonarr and radarr currently depend on accessing tranmission through its external network ip (and not the internal docker ip of 0.0.0.0). This will need to be tested and adjusted on each new server deploy.

## First run

- install [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-using-the-repository/)
- create a [Plex accout](https://www.plex.tv/)
- clone this repository
- create a user for the media server, add `$USER_ID` and `$GROUP_ID` variables to the appropriate place in the included `.env` file. (or use user id)
- create a media folder in docker-compose's folder with $USER_ID:$GROUP_ID ownership
- get your Plex claim token at https://www.plex.tv/claim/ (optional)
- run `docker-compose up -d`
- enjoy :)

