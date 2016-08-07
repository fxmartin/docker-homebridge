[![Docker Stars](https://img.shields.io/docker/stars/fxmartin/docker-homebridge.svg)](https://hub.docker.com/r/fxmartin/docker-homebridge/)
[![Docker Pulls](https://img.shields.io/docker/pulls/fxmartin/docker-homebridge.svg)](https://hub.docker.com/r/fxmartin/docker-homebridge/)
[![GitHub forks](https://img.shields.io/github/forks/fxmartin/docker-homebridge.svg?style=social&label=Fork)](https://github.com/fxmartin/docker-homebridge)
# docker-homebridge

Docker image for Homebridge

For details see https://github.com/nfarina/homebridge

This is simply wrapping the source in a runnable Docker image for everyone that cannot install the dev environment on his machine or everyone that wants a simple containerized solution.
If you intend to run this docker image on a Synology NAS, read this documentation:
http://chris.brandlehner.at/Brandlehner/cab_blog.nsf/d6plinks/CBRR-A6XQUY

## Supported plugins
homebridge-http-jeedom
(and you can extend this list by adding more plugins in the file package.json)
For example:
homebridge-ninjablock-temperature
homebridge-ninjablock-humidity
homebridge-ninjablock-alarmstatedevice
homebridge-luxtronik2
homebridge-mqttswitch
homebridge-edomoticz
homebridge-synology

## Configuration

Copy `config-sample.json` to `config.json` and adapt to your likings.

## Build

`./homebridge.sh build`

## Run

### run first time

`./homebridge.sh run`

### stop

`./homebridge.sh stop`

### start

(after stopping)

`./homebridge.sh start`

### remove

(needed before run is possible again)

`./homebridge.sh remove`

### rerun

Stops and removes the containers, then performs run again

`./homebridge.sh rerun`

### attach

Attaches to the running container

`./homebridge.sh attach`

### logs

Diplays stdout log of the running container

`./homebridge.sh logs`

## Changelog
###0.11
moved from nodesource/jessie:5.6.0 to nodesource/jessie:5.8.0
moved files that are copied into the image are in directory ./image
moved configuration samtes to ./config-sample
simplified Dockerfile and combined the previously two script files into a single script
implemented a way to install homebridge modules at runtime without the need to include them in the docker image
fixing a locale issue with C vs UTF-8
###0.12
git push problem - do not use this release
###0.13
should have fixed git push problem
###0.14
added link to blog and sample start script
###0.15
moved to jessie:latest
###0.16
added debug run command to homebridge.sh
