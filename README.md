### 个人使用的docker开发环境



集合了 `mysql5.6`、`nginx`、`php-fpm56`、`php-fpm72`、`redis`、`rabbitmq`、`ftpd_server`



对`php-fpm56` 和 `php-fpm72` 安装了`xdebug` 扩展，

配置好 `phpStorm debug` 后可直接进行`debug`, 无需做其他配置(maybe，时间有点久远有点记不清了~)，

可配合 Chrome 扩展 `Xdebug helper` 附地址 https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc





使用方法：

`git clone git@github.com:mh1988/develop-environment.git`



启动所有镜像： `docker-compose -d up`

停止所有镜像：`docker-compose down`

重启某个镜像：`docker-compose restart php-fpm56`

进入某个镜像：`docker exec -it php-fpm56 bash`


