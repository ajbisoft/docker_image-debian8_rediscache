# Docker image: debian9_rediscache

## Description

Official Debian 9 (debian:9) + redis docker image with some customization:
* /etc/apt/sources.list modified to include stretch-updates
* CMD set to autostart redis service

## Usage

There are two main run-time settings that may be passed to newly created container from this image:
* Port must be published when starting container by adding `-p 6379:6379` to your `docker run` statement if you want mysql service to be binded to host interfaces

## Example

To successfully start a new container using this image please specify port and volume options as in following example:
`docker run -dp 6379:6379 --name <your-app-name> ajbisoft/debian9_rediscache`
This will expose and publish mysql container on port 6379 on all host interfaces, but you may skip `-p 6379:6379` option and use container linking instead.

## Summary

This docker image is best suited for applications that would benefit from centralized Redis cache service. 
There are other docker images in my github repos that you might find useful.

