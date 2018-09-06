server
{
    listen       80 default;
    server_name  _;
    index index.html index.htm index.php;
    root  /data/httpd/;

    location ~ .*\.php.*
    {
        include php_fcgi.conf;
        include pathinfo.conf;
    }

    location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$
    {
        expires      30d;
    }

    location ~* \.(ini|sql|conf|bak)$ {
         return 404;
    }

    location ~* ^/(themes|images|logs|data|demo|wap_themes)/.*\.(php|php5)$ {
        deny all;
    }

    location ~ /\.(svn|git|)/ {
       deny all;
    }

    location ~ .*\.(js|css)?$
    {
        expires      1h;
    }
    access_log /var/log/nginx/access.log access;
    #access_log off;
}

