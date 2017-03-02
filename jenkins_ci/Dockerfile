FROM jenkins:2.32.2
ADD apache-maven-3.3.9-bin.tar.gz /home/
COPY plugins.txt /usr/share/jenkins/ref/
#RUN /usr/local/bin/install-plugins.sh $(cat /usr/share/jenkins/ref/plugins.txt | tr '\n' ' ')
# plugins.sh has been depreciated but install-plugins.sh fails then download is unsuccessful. Hence use back plugins.sh
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/ref/plugins.txt