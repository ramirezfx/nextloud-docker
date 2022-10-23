# nextloud-docker

## Install Dependencies:

Install docker and docker-compose:

`sudo apt-get install docker.io docker-compose`

Install GIT:

`sudo apt-get install git`

## Clone this repo

Clone this repo by typing:

`git clone https://github.com/ramirezfx/nextloud-docker.git`

## Setup/Install nextcloud

Navigate to the source-directory:

`cd nextcloud-docker`

Install nextcloud:

`docker-compose up -d`

Nextcloud should now be accessible from your webbrowser (http://localhost:8080)

## Configuration

If you use a reverse-proxy you must do some modifications:

In the console type:

`docker exec --user www-data $owncloud-container-name php occ config:system:set overwriteprotocol --value=https`
`docker exec --user www-data $owncloud-container-name php occ config:system:set trusted_domains 1 --value nextcloud.speedypreneur.com`
`docker exec --user www-data $owncloud-container-name php occ config:system:set overwrite.cli.url https://nextcloud.speedypreneur.com`

Replace $owncloud-container-name with your owncloud-container-name
