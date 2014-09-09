Waiting on [pull request on Ripple/gatewayd](https://github.com/ripple/gatewayd/pull/269) for build. Otherwise I can point the image to my fork of Ripple/gatewayd

# Install gatewayd with docker

This project breaks up the gatewayd app into two docker containers:
 - gatewayd
 - postgres


This is the docker way, ship the different pieces of your app in different containers and link them when running.

## Install Instructions

All of the building required is provided by the install.sh

    ./install

Most docker installations require `sudo ./install`

## Run that gateway

    docker run --link db:db -d -p 5000:5000 --name gatewayd_start adamcmiel/gatewayd

#### If you built with ./build

    docker run --link db:db -d -p 5000:5000 --name gatewayd_start gatewayd

# TODO:

 - refactor db data to separate storage container
 - put all images (storage, db, app) in another container behind nginx
