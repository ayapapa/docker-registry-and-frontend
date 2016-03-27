# docker image
FROM nginx:latest

# maintainer information
MAINTAINER ayapapa ayapapajapan@yahoo.co.jp

# copy resources 
COPY nginx.conf /etc/nginx/nginx.conf
COPY registry.conf /etc/nginx/conf.d/registry.conf
COPY server.crt /etc/nginx/server.crt
COPY server.key /etc/nginx/server.key
COPY .htpasswd /etc/nginx/.htpasswd
