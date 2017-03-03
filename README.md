Description
===========

A list of docker files to build specific images.

Enabling Docker Remote API on Ubuntu 16.04
-----------
Reference taken from [blog](https://www.ivankrizsan.se/2016/05/18/enabling-docker-remote-api-on-ubuntu-16-04/)

 - Edit the file /lib/systemd/system/docker.service

 `sudo gedit /lib/systemd/system/docker.service`
 - Modify the line that starts with ExecStart to look like this

 `ExecStart=/usr/bin/docker daemon -H fd:// -H tcp://0.0.0.0:4243`
 - Make sure the Docker service notices the modified configuration

  `systemctl daemon-reload`
 - Restart the Docker service

  `sudo service docker restart`
 - Test the REST api

  `curl -X GET http://localhost:4243/images/json`

