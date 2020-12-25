# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
RUN sed -i 's/LISTEN 80/LISTEN 8080/g' /etc/httpd/conf/httpd.conf
EXPOSE 8080
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd
USER 1001
ONBUILD cp ./src/index.html /var/www/html/index.html
