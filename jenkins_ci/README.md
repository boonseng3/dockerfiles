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


Setup
---------------

1. After the Jenkins is fully running, take note of the default adminstrator password.
1. Install the recommend list of plugins, it will finish immediately because it has already been installed.
1. Setup the administrator account.
1. Set up the maven location in Tool configuration.
1. Set up the SSH credentials for Git.