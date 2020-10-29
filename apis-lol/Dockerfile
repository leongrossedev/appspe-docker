# Version 8.5 de tomcat / JDK 8
FROM openjdk:8-jre-alpine

# Déploiement des webapps par défaut tomcat
RUN mkdir -p /var/log/apps && mkdir -p /var/www/apps

# Copier le jar
COPY ./resources/leonline-api-rest.jar /var/www/apps/leonline-api-rest.jar

# On se positionne dans le dossier des apis
WORKDIR /var/www/apps

# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Ports exposés
EXPOSE 8085/tcp

# Lancer l'application
CMD ["/usr/bin/java", "-jar", "leonline-api-rest.jar", "--debug"]
