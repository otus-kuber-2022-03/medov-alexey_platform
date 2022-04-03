FROM nginx:1.21.6-alpine
ENV nginx_conf=/etc/nginx/conf.d/default.conf
RUN deluser nginx; \
    adduser -u 1001 -h /var/cache/nginx -D -s /sbin/nologin nginx -g nginx; \
    addgroup nginx nginx
RUN chown -R nginx:nginx \
    /var/cache/nginx \
    /etc/logrotate.d/nginx \
    /etc/init.d/nginx \
    /etc/nginx \
    /var/log/nginx \
    /var/cache/nginx \
    /usr/share/licenses/nginx \
    /usr/share/nginx \
    /usr/lib/nginx \
    /usr/sbin/nginx \
    /var/run/
RUN mkdir -p /app; \
    chown -R nginx:nginx /app; \
    echo "server {"                         > $nginx_conf; \
    echo "listen       8000;"               >> $nginx_conf; \
    echo "server_name  localhost;"          >> $nginx_conf; \
    echo ""                                 >> $nginx_conf; \
    echo ""                                 >> $nginx_conf; \
    echo "location / {"                     >> $nginx_conf; \
    echo "    root   /app;"                 >> $nginx_conf; \
    echo "    index  index.html index.htm;" >> $nginx_conf; \
    echo "    }"                            >> $nginx_conf; \
    echo "}"                                >> $nginx_conf;
EXPOSE 8000
USER 1001
