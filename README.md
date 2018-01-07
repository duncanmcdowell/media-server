# media-server
Turn-key media server including Plex, Transmission, Radarr and Sonarr deployed via docker

## Prep

- Assmemble NUC
- install Ubuntu (flash USB stick if necessary)
- install SSH: `sudo apt-get install openssh-server`
- partition and format external drive [(if applicable)](https://askubuntu.com/questions/384062/how-do-i-create-and-tune-an-ext4-partition-from-the-command-line#answer-811954)

## First run

- install [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-using-the-repository/)
- create a [Plex accout](https://www.plex.tv/)
- clone this repository
- create a user for your media server, export its `$USER_ID` and `$GROUP_ID`. (or use user id)
- create a media folder in docker-compose's folder with $USER_ID:$GROUP_ID ownership
- get your Plex claim token at https://www.plex.tv/claim/ (optional?)
- run `docker-compose up -d`
- enjoy :)

