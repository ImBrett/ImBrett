FROM nginx:stable-alpine
ADD ./docker/dev/nginx/conf.d/nginx.conf /etc/nginx/
ADD ./docker/dev/nginx/conf.d/default.conf /etc/nginx/conf.d/
RUN mkdir -p /var/www/html
RUN addgroup -g 1000 imbrett && adduser -G imbrett -g imbrett -s /bin/sh -D imbrett
RUN chown imbrett:imbrett /var/www/html
