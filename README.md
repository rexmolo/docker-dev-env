Docker development environment for personal use
Collection of `mysql5.6`, `nginx`, `php-fpm56`, `php-fpm72`, `redis`, `rabbitmq`, `ftpd_server`

Installed the xdebug extension for `php-fpm56` and `php-fpm72`,

After configuring the `phpStorm debug`, you can debug directly, no other configuration is needed (maybe, the time is a bit long and hard to remember ~)

Works with Chrome extension Xdebug helper with address https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc

##Instructions:

`git clone https://github.com/rexmolo/docker-dev-env.git`

#### Container management
Start all: docker-compose up After installation you can use docker-compose -d up

Stop everything: `docker-compose down`

Restart one: `docker-compose restart php-fpm56`

Enter some: `docker exec -it php-fpm56 bash`

#### fastcgi:
Php56: fastcgi_pass php-fpm56: 9000;

Php72: fastcgi_pass php-fpm72: 9000;

#### ftpd_server: (execute subordinate commands in the container)
Add account command:

`useradd ftptest -g ftpgroup -d / home / ftpusers / ftptest -s / sbin / nologin`

Enter the following command, you will be prompted to set a password, and then you can use it normally

`pure-pw useradd ftptest -f /etc/pure-ftpd/passwd/pureftpd.passwd -m -u ftptest -d / home / ftpusers / ftptest`

Look at a few users:

`pure-pw list`

Reset the ttt user's password:

`pure-pw passwd ttt`

Data refresh:

`pure-pw mkdb`

RabbitMQ
Interface Management: http://127.0.0.1:15672 Account: `guest` Password: `guest`

Remarks:

Some mount paths in `docker-compose.yml` may require some simple adjustments, for example `~ / www /: / data / httpd` in volumes in `php-fpm56` may need to be modified to your own project storage path
