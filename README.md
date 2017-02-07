# Docker image: debian8_rediscache

## Description

Official Debian 8 (debian:8) + redis docker image with some customization:
* /etc/apt/sources.list modified to include jessie-updates and to use Polish mirror by default
* Redis configured as cache only service
* CMD set to autostart redis service

## Usage

//There are two main run-time settings that may be passed to newly created container from this image:
//* Port must be published when starting container by adding `-p 5432:5432` to your `docker run` statement if you want mysql service to be binded to host interfaces
//* There is no VOLUME statement in Dockerfile, so data volume must be attached when starting container by adding `-v <path_to_your_datadir>:/var/lib/postgresql` to your `docker run` statement. Please check permissions as container will not start if those are wrong.

## Example

To successfully start a new container using this image please specify port and volume options as in following example:
//`docker run -dp 5432:5432 -v <path_to_your_datadir>:/var/lib/postgresql --name <your-app-name> ajbisoft/debian8_pgsql`
//This will expose and publish mysql container on port 5432 on all host interfaces, but you may skip `-p 5432:5432` option and use container linking to access PostgreSQL container from within your app.

## Summary

This docker image is best suited for applications that would benefit from centralized Redis cache service. 
There are other docker images in my gitlab repos that you might find useful.

