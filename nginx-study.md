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

1. 在 nginx.conf 里 有这个一段代码, 

   ```
   include  /etc/nginx/modules-enabled/*.conf;
   ```

   

