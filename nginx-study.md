# nginx 



## 1. location



| 模式                  | 含义                                                         |
| --------------------- | ------------------------------------------------------------ |
| `location = /uri`     | = 表示精确匹配                                               |
| `location ^~ /uri`    | ^ 进行前缀匹配，~ 表示区分大小写                             |
| `location ~ pattern`  | ~ 区分大小写的匹配                                           |
| `location ~* pattern` | ~* 不区分大小写的匹配                                        |
| `location /uri`       | 不带任何修饰符，也表示前缀匹配，但是在正则匹配之后           |
| `location /`          | 通用匹配，任何未匹配到其它 location 的请求都会匹配到，相当于 switch 中的 default |
| `location !~`         | 区分大小写不匹配                                             |
| `location !~*`        | 不区分大小写不匹配                                           |





## 2. ubuntu linux

1. 启动nginx

   ```sh
   service nginx start
   
   第二种
   ./nginx -c 配置文件位置
   ```

   在网页中 输入 localhost , 开是否启动成功

2. 位置

   ```
   /usr/sbin/nginx：主程序
   /etc/nginx：存放配置文件
   /usr/share/nginx：存放静态文件
   /var/log/nginx：存放日志
   ```

3. 卸载

   ```
   apt-get  --purge  autoremove  nginx
   ```

   

## 3. 配置

```

#user  nobody;
worker_processes  1;

#error_log  logs/error.log;
#error_log  logs/error.log  notice;
#error_log  logs/error.log  info;

#pid        logs/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       mime.types;
    default_type  application/octet-stream;
    
    #log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
    #                  '$status $body_bytes_sent "$http_referer" '
    #                  '"$http_user_agent" "$http_x_forwarded_for"';

    #access_log  logs/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    #keepalive_timeout  0;
    keepalive_timeout  65;

    #gzip  on;
	gzip on;
	gzip_comp_level 9;
	gzip_min_length 10k;
	gzip_proxied any;
	gzip_vary on;
	gzip_types
    	application/atom+xml
    	application/javascript
    	application/json
    	application/ld+json
    	application/manifest+json
    	application/rss+xml
    	application/vnd.geo+json
    	application/vnd.ms-fontobject
    	application/x-font-ttf
    	application/x-web-app-manifest+json
    	application/xhtml+xml
    	application/xml
    	font/opentype
    	image/bmp
    	image/svg+xml
    	image/x-icon
    	text/cache-manifest
    	text/css
    	text/plain
    	text/vcard
    	text/vnd.rim.location.xloc
    	text/vtt
    	text/x-component
    	text/x-cross-domain-policy;	


	client_max_body_size 1000M;
	server_tokens off;
	
    server {
        listen       80;
        server_name  localhost;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;

        location / {
            root   html;
            index  index.html index.htm;
        }

        #error_page  404              /404.html;

        # redirect server error pages to the static page /50x.html
        #
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }

        # proxy the PHP scripts to Apache listening on 127.0.0.1:80
        #
        #location ~ \.php$ {
        #    proxy_pass   http://127.0.0.1;
        #}

        # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
        #
        #location ~ \.php$ {
        #    root           html;
        #    fastcgi_pass   127.0.0.1:9000;
        #    fastcgi_index  index.php;
        #    fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
        #    include        fastcgi_params;
        #}

        # deny access to .htaccess files, if Apache's document root
        # concurs with nginx's one
        #
        #location ~ /\.ht {
        #    deny  all;
        #}
    }


    # another virtual host using mix of IP-, name-, and port-based configuration
    #
    #server {
    #    listen       8000;
    #    listen       somename:8080;
    #    server_name  somename  alias  another.alias;

    #    location / {
    #        root   html;
    #        index  index.html index.htm;
    #    }
    #}


    # HTTPS server
    #
    #server {
    #    listen       443 ssl;
    #    server_name  localhost;

    #    ssl_certificate      cert.pem;
    #    ssl_certificate_key  cert.key;

    #    ssl_session_cache    shared:SSL:1m;
    #    ssl_session_timeout  5m;

    #    ssl_ciphers  HIGH:!aNULL:!MD5;
    #    ssl_prefer_server_ciphers  on;

    #    location / {
    #        root   html;
    #        index  index.html index.htm;
    #    }
    #}

    server {
        listen       8090 443 ssl;
        server_name  xianmoer-frontend;
		
		ssl_certificate ./xianmoer.crt;
        ssl_certificate_key ./xianmoer.key;
		ssl_session_timeout 5m;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2; 
        ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE; 
        ssl_prefer_server_ciphers on;
	
		server_tokens off;
		proxy_hide_header Server;
		add_header Content-Security-Policy "default-src 'self';
                                 object-src 'self' ;
                                 style-src 'self' 'unsafe-inline';
                                 frame-src 'self' ;
                                 base-uri 'self'; 
                                 form-action 'self';
                                 script-src 'self'  'unsafe-eval' 'sha256-s9RoBFqqRTKEz03aMkaEGLy7X3nJuyOZ8mzkjwCekYA=' ;
								 connect-src 'self' https://api.iconify.design https://api.unisvg.com https://api.simplesvg.com;
                                 img-src 'self' data:";
		add_header X-Content-Type-Options "nosniff";
		add_header Set-Cookie "SameSite=Lax; Secure; HttpOnly; Path=/";
		add_header Referrer-Policy same-origin;
        
		root D:\xianmoer-assessment\front-end\20231121\dist;

        location /basic-api {
			
            proxy_pass http://127.0.0.1:9950/api;
        }

        location /file/xianmoer {
            proxy_set_header Host 127.0.0.1:9000;
            proxy_pass http://127.0.0.1:9000/xianmoer;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
		
		location ~ /\. {
			deny all;
		}
		
		location / {
            try_files $uri $uri/ =404;
        }
    }
}

```





1. 在 nginx.conf 里 有这个一段代码, 

   ```
   include  /etc/nginx/modules-enabled/*.conf;
   ```

2. 配置示例

   ```
   
   ```





### 1. 403->404

```
location / {
    try_files $uri $uri/ =404;
}
```

`try_files` 是 Nginx 中的一个指令，用于尝试逐个检查给定的一系列文件或 uri，并返回第一个存在的文件或 uri。对于你的问题中给出的配置片段：

Nginx

```nginx
1try_files $uri $uri/ =404;
```

这条指令的具体工作方式和详细解释如下：

- `$uri`：首先尝试匹配当前请求的 URI（统一资源标识符）所对应的文件是否存在。例如，如果请求的 URL 是 `/example/path`，那么 Nginx 会首先查找服务器根目录下的 `/example/path` 文件。
- `$uri/`：如果第一步尝试的文件不存在，那么 Nginx 将尝试把请求当作一个目录来处理，并在其后追加一个斜杠（`/`），再次尝试匹配。例如，如果 `/example/path` 不存在，它会查找 `/example/path/` 是否是一个目录，并试图访问该目录下的默认文件，如 `index.html` 或其他在 `index` 指令中定义的默认文件。
- `=404`：如果前两步尝试都无法找到匹配的文件或目录，Nginx 就会直接返回一个 404 错误（Not Found）给客户端，表明请求的资源在服务器上不存在。

综上所述，`try_files $uri $uri/ =404;` 这个配置是为了确保无论请求的是一个实际的文件还是一个目录，如果该资源不存在，Nginx 都会优雅地返回 404 错误，而不是其他可能误导用户的错误代码，如 403 Forbidden 或其他状态码。这对于提高用户体验和搜索引擎友好性非常重要。





# 1. 命令

| windows 系统                           |      |      |
| -------------------------------------- | ---- | ---- |
| nginx.exe                              | 开启 |      |
| nginx.exe -s stop    nginx.exe -s quit | 停止 |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |
|                                        |      |      |





