FROM fabiocicerchia/nginx-lua:alpine

WORKDIR /var/www/html

RUN (curl -s https://api.github.com/repos/magiclen/nginx-cache-purge/releases/latest | sed -r -n 's/.*"browser_download_url": *"(.*\/nginx-cache-purge_'$(uname -m)')".*/\1/p' | wget -i -)  \
    && mv nginx-cache-purge_$(uname -m) /usr/local/bin/nginx-cache-purge \
    && chmod +x /usr/local/bin/nginx-cache-purge

COPY docker/nginx/conf.d/nginx.conf /etc/nginx/
COPY docker/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf

COPY ./images /var/www/html/image
