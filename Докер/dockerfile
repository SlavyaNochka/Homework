FROM debian
ADD debian.list /etc/apt/sources.list.d/
RUN apt-get update && \
    apt-get -y upgrade && \
    apt -y install nginx && \
    apt-get clean && \
    rm -rf /var/www/* && \ 
    mkdir -p /var/www/leila999.com/img && \
    chmod -R 754 /var/www/leila999.com/ && \
    useradd leila999 && groupadd Dockumova &&\
    usermod -aG Dockumova leila999 && \
    chown -R leila999:Dockumova /var/www/leila999.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/leila999.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user leila999/g' /etc/nginx/nginx.conf
ADD index.html /var/www/leila999.com/
ADD img.jpg /var/www/leila999.com/img/
CMD ["nginx", "-g", "daemon off;"]
