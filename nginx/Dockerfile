FROM macbre/nginx-brotli:latest

RUN mkdir -p /etc/nginx/ssl
RUN mkdir -p /home/mctw
RUN rm -rf /etc/nginx/conf.d/default.conf

COPY my.conf /etc/nginx/conf.d/my.conf
COPY gzip.conf /etc/nginx/conf.d/gzip.conf
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

COPY ssl/你的ＳＳＬ憑證.pem /etc/nginx/ssl/你的ＳＳＬ憑證.pem
COPY ssl/你的ＳＳＬ憑證.key /etc/nginx/ssl/你的ＳＳＬ憑證.key