# Version 8.5 de tomcat / JDK 8
FROM tomcat:8.5.57-jdk8-adoptopenjdk-openj9

# Répertoire de travail
WORKDIR /usr/local/tomcat/

# Déploiement des webapps par défaut tomcat
RUN cp -r webapps.dist/* webapps/

# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Déploiement des applications
COPY ./resources/webapps/apca.war ./webapps/apca.war
COPY ./resources/webapps/acau.war ./webapps/acau.war
COPY ./resources/webapps/acdc.war ./webapps/acdc.war
COPY ./resources/webapps/arlg.war ./webapps/arlg.war
COPY ./resources/webapps/asgr.war ./webapps/asgr.war
COPY ./resources/webapps/agpe.war ./webapps/agpe.war

# Ports exposés
EXPOSE 8080/tcp

# Démarrer tomcat
CMD ["catalina.sh", "run", "1>>/usr/local/tomcat/logs/catalina.out", "2>>/usr/local/tomcat/logs/catalina.out"]
