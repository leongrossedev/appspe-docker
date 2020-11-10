# Version 8.5 de tomcat / JDK 8
FROM tomcat:8.5.57-jdk8-adoptopenjdk-openj9

# Répertoire de travail
WORKDIR /usr/local/tomcat/

# Déploiement des webapps par défaut tomcat
RUN cp -r webapps.dist/* webapps/

# Fonts MS
ENV http_proxy "http://10.1.33.254:8888"
RUN echo "deb http://us-west-2.ec2.archive.ubuntu.com/ubuntu/ trusty multiverse" > /etc/apt/sources.list.d/multiverse.list
RUN echo "deb http://us-west-2.ec2.archive.ubuntu.com/ubuntu/ trusty-updates multiverse" >> /etc/apt/sources.list.d/multiverse.list
RUN echo "deb http://us-west-2.ec2.archive.ubuntu.com/ubuntu/ trusty-backports main restricted universe multiverse" >> /etc/apt/sources.list.d/multiverse.list
RUN apt-get update
RUN apt-get install -y --no-install-recommends ttf-mscorefonts-installer


# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Ports exposés
EXPOSE 8080/tcp

# Démarrer tomcat
CMD ["catalina.sh", "run", "1>>/usr/local/tomcat/logs/catalina.out", "2>>/usr/local/tomcat/logs/catalina.out"]
