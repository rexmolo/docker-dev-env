server
{
    listen       80;
    server_name  wp.test;
    index index.html index.htm index.php;
    root  /data/httpd/wordpress/;

#     location / {
#         if (!-e $request_filename) {
#           rewrite  ^/(.*)$  /index.php?s=$1  last;
#           break;
#         }
#    }

    
    location ~ .*\.php.*
    {
	fastcgi_pass php-fpm72:9000;
        include php_fcgi_r.conf;
        include pathinfo.conf;
    }
    
    location ~ .*\.(gif|jpg|jpeg|png|bmp|swf)$
    {
        expires      30d;
    }
        
    location ~ /\.(svn|git|)/ {
       deny all;
    }

    location ~ .*\.(js|css)?$
    {
        expires      1h;
    }
    access_log /var/log/nginx/access.log;
    #access_log off;
}
