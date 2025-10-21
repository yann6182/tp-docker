FROM httpd:2.4

COPY index.html /usr/local/apache2/htdocs/

RUN sed -i '/^#LoadModule proxy_module/s/^#//' /usr/local/apache2/conf/httpd.conf && \
    sed -i '/^#LoadModule proxy_http_module/s/^#//' /usr/local/apache2/conf/httpd.conf

RUN echo '\
<VirtualHost *:80>\n\
    ProxyPreserveHost On\n\
    ProxyPass / http://backend:8080/\n\
    ProxyPassReverse / http://backend:8080/\n\
</VirtualHost>\n' >> /usr/local/apache2/conf/httpd.conf
