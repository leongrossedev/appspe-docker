# Version 8.5 de tomcat / JDK 8
FROM openjdk:8-jre-alpine

# Déploiement des webapps par défaut tomcat
RUN mkdir -p /var/log/apps && mkdir -p /var/www/apps

# Copier le jar
COPY ./resources/referentiel-api-rest.jar /var/www/apps/referentiel-api-rest.jar

# On se positionne dans le dossier des apis
WORKDIR /var/www/apps

# Ports exposés
EXPOSE 8082/tcp

# Lancer l'application
CMD ["/usr/bin/java", "-jar", "referentiel-api-rest.jar", "--debug"]
