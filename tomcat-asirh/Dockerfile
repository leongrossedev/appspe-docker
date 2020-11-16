# Version 8.5 de tomcat / JDK 8
FROM tomcat:8.5.57-jdk8-adoptopenjdk-openj9

# Répertoire de travail
WORKDIR /usr/local/tomcat/

# Déploiement des webapps par défaut tomcat
RUN cp -r webapps.dist/* webapps/

# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Ports exposés
EXPOSE 8080/tcp

# Démarrer tomcat
ENV JAVA_OPTS "${JAVA_OPTS} -Dfile.encoding=UTF8"
CMD ["catalina.sh", "run", "1>>/usr/local/tomcat/logs/catalina.out", "2>>/usr/local/tomcat/logs/catalina.out"]
