FROM nginx:1.10.1

ADD nginx.conf /etc/nginx/nginx.conf
ADD vhosts/* /etc/nginx/conf.d/
RUN mkdir -p /data/wwwroot && mkdir -p /data/log && mkdir -p /data/log/nginx
RUN chown -R www-data.www-data /data/wwwroot /data/log

EXPOSE 80
VOLUME ["/data"]