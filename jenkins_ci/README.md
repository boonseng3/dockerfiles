Description
===========

This image pulls from *jenkins:2.32.2* as base image.
Install the default list of plugins.

Requirements
-----------

 - apache-maven-3.3.9-bin.tar.gz
 - plugins.txt
 - a volume that maps to container /var/jenkins_home
 - the volume must have a .ssh folder that contains the public/private keys. Register the delpoy key in GitLab so that you can pull the codes.

Sample commands
---------------

Build the image

    docker build -t jenkins_ci .

Start a container

    docker run --name myjenkins --link cme-sql:mysql -p 8080:8080 -p 50000:50000 -v $JENKINS_VOLUME:/var/jenkins_home jenkins_ci
