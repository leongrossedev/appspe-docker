# Dernière version de nginx
FROM nginx

# Timezone
ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

WORKDIR /etc/nginx/

# Config
COPY ./resources/conf.d/apps-oid.conf ./conf.d/
COPY ./resources/conf.d/apps.conf ./conf.d/
COPY ./resources/conf.d/appsapca.conf ./conf.d/
COPY ./resources/conf.d/appsagpe.conf ./conf.d/
COPY ./resources/conf.d/appsasgr.conf ./conf.d/
COPY ./resources/conf.d/appsacau.conf ./conf.d/
COPY ./resources/conf.d/appsacdc.conf ./conf.d/
COPY ./resources/conf.d/appsarlg.conf ./conf.d/
COPY ./resources/conf.d/appssirh.conf ./conf.d/
COPY ./resources/conf.d/prisme.conf ./conf.d/
COPY ./resources/conf.d/default.conf ./conf.d/default.conf
COPY ./resources/nginx.conf ./nginx.conf
COPY ./resources/ssl/xxx.leon-grosse.fr.cer ./ssl/
COPY ./resources/ssl/xxx.leon-grosse.fr.key ./ssl/

# Ports exposés
EXPOSE 80/tcp
EXPOSE 443/tcp
