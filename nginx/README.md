# nginx brotli 版本

請先將 my.conf 修改為你需要的環境

建立 image
```
docker build -t mctw_nginx:latest .
```

Run container
```
docker run -it --name mctw_nginx -p 443:443  \
    -p 80:80 -d \
    --link mc_php_fpm:php \
    --volumes-from /mctw_code \
    -d mctw-nginx:latest
```
link 功能為將另一個 php container 與 nginx config fastcgi_pass php:9000; 裏設定的連結
```
--link mc_php_fpm:php
```
mount 數據卷容器
```
--link mc_php_fpm:php
```
Port 開啟
```
-p 443:443 -p 80:80
```
連線進去看你的nginx 狀況
```
docker exec -it mctw_nginx /bin/sh
```