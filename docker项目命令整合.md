## GitLab
```
docker run --detach \
  --hostname gitlab \
  --publish 443:443 --publish 80:80 --publish 22:22 \
  --name gitlab \
  --restart always \
  --volume /E/docker/gitlab/config:/etc/gitlab \
  --volume /E/docker/gitlab/logs:/var/log/gitlab \
  --volume /E/docker/gitlab/data:/var/opt/gitlab \
  gitlab/gitlab-ce:latest


docker run --detach   --hostname gitlab --publish 8443:443 --publish 8080:80 --publish 2222:22   --name gitlab   --restart always   --volume /F/docker/gitlab/config:/etc/gitlab   --volume /F/docker/gitlab/logs:/var/log/gitlab   --volume /F/docker/gitlab/data:/var/opt/gitlab --privileged=true   gitlab/gitlab-ce:latest
```

## Jenkins
```
docker run -d -p 8086:8080 -v /E/docker/jenkins:/var/jenkins_home --name forhomejenkins --restart=always jenkins/jenkins:lts
```

## MySQL
```
docker run --name dpmp-mysql -v /docker/mysql:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=123456 -p 3306:3306 -d mysql:tag

docker run -p 3306:3306 --name dpmp-mysql -v /docker/mysql/conf/my.cnf:/etc/mysql/my.cnf -v /docker/mysql/logs:/var/lib/mysql -v /docker/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql

docker run -d -p 3306:3306 -e MYSQL_USER=dujiadi -e MYSQL_PASSWORD=dujiadi -e MYSQL_ROOT_PASSWORD=dujiadi -e MYSQL_ROOT_HOST=% -v F:/docker/mysql/config/my.cnf:/etc/my.cnf  -v F:/docker/mysql/data:/var/lib/mysql --name mysql01 mysql

docker run -d -p 3306:3306 -e MYSQL_USER=dujiadi -e MYSQL_PASSWORD=dujiadi -e MYSQL_ROOT_PASSWORD=dujiadi -e MYSQL_ROOT_HOST=% -v /F/docker/mysql/config/my.cnf:/etc/my.cnf  -v /F/docker/mysql/data:/var/lib/mysql --name mysql01 mysql
```

## Nginx
```
docker run -p 8080:80 --name mynginx -v /F/docker/nginx/www:/www -v /F/docker/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v /F/docker/nginx/logs:/wwwlogs -d nginx
```

## Quartz
```
docker run -v /F/docker/quartz:/app/File  --restart=unless-stopped --privileged=true --name quartzui -dp 5088:80 bennyzhao/quartzui
```

## Consul
```
docker run -d -p 8500:8500 --restart=always --name=consul consul agent -server -bootstrap-expect=1 -node=consul_server_1 -client='0.0.0.0' -ui
```
