---
layout: post
title: Kill containers in Docker
tags: docker
---
After using Docker for a while, you may find out there are so many containers in stopped status, and they are not deleted. You can delete them one by one with `docker rm`, but we are developers, how can we bear this?

Thank god Docker provides a parameter named `-q` in `docker ps` command to just print container IDs on console.

* Delete all stopped containers

    `docker rm $(docker ps -f status=stopped -q)`

* Delete all containers

    `docker rm -f $(docker ps -a -q)`

Isn't it cool? If not, make some alias for this, like `alias drma=docker rm -f $(docker ps -a -q)`, that's how it's done!
