FROM nginx:1.21.6-alpine
ENV nginx_conf=/etc/nginx/conf.d/default.conf
RUN mkdir -p /app; \
    echo "server {" > $nginx_conf; \
    echo "listen       8000;" >> $nginx_conf; \
    echo "server_name  localhost;" >> $nginx_conf; \
    echo "" >> $nginx_conf; \
    echo "" >> $nginx_conf; \
    echo "location / {" >> $nginx_conf; \
    echo "    root   /app;" >> $nginx_conf; \
    echo "    index  index.html index.htm;" >> $nginx_conf; \
    echo "}" >> $nginx_conf; \
    cat $nginx_conf; cd /app; pwd; ls -la
