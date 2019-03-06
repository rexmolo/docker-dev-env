### 个人使用的docker开发环境



集合了 `mysql5.6`、`nginx`、`php-fpm56`、`php-fpm72`、`redis`、`rabbitmq`、`ftpd_server`



对`php-fpm56` 和 `php-fpm72` 安装了`xdebug` 扩展，

配置好 `phpStorm debug` 后可直接进行`debug`, 无需做其他配置(maybe，时间有点久远有点记不清了~)，

可配合 Chrome 扩展 `Xdebug helper` 附地址 https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc





使用方法：

`git clone https://github.com/rexmolo/docker-dev-env.git`



启动所有镜像： `docker-compose up` 安装之后可以用 `docker-compose -d up`

停止所有镜像：`docker-compose down`

重启某个镜像：`docker-compose restart php-fpm56`

进入某个镜像：`docker exec -it php-fpm56 bash`



fastcgi：

Php56：`fastcgi_pass php-fpm56:9000;`

Php72:`fastcgi_pass php-fpm72:9000;`



ftpd_server:（容器内执行下属命令）

添加账号命令:

` useradd ftptest -g ftpgroup -d /home/ftpusers/ftptest -s /sbin/nologin`

输入下面命令，会提示你设置密码，之后就可以正常使用了

`pure-pw useradd ftptest -f /etc/pure-ftpd/passwd/pureftpd.passwd -m -u ftptest -d /home/ftpusers/ftptest`



备注：

`docker-compose.yml` 中一些挂载路径可能需要做一些简单调整，例如 `php-fpm56` 中 `volumes` 里面的 `~/www/:/data/httpd` 可能需要修改成你自己的项目存放路径
