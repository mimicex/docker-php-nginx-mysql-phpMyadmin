# docker-compose 建立 PHP 8.0 + Nginx + Mysql + phpMyadmin
建立 php image
```
cd php
```

```
docker build -t my_code:latest .
```

```
cd nginx
```
建立 nginx image
```
docker build -t my_nginx:latest .
```

```
cd mysql
```
建立 Mysql image
```
docker build -t my_nginx:latest .
```
建立 network
```
docker network create my_net
```
建立 volume
```
docker volume create my-datavolume
```
啟動 docker-compose
```
docker-compose up -d
```

phpMyadmin
```
http://localhost:8081
```