# Dernière version de nginx
FROM nginx

# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Ports exposés
EXPOSE 80/tcp
EXPOSE 443/tcp