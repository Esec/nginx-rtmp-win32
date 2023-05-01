nginx-rtmp-cygwin64
================

* [Nginx](http://nginx.org/): 1.18.0
* [nginx-rtmp-module](https://github.com/arut/nginx-rtmp-module): master-20201202-git-afd350e
* [openssl](https://www.openssl.org/)：1.1.1i

# 分支说明
libcrypt-4.4.4、pcre-8.44和zlib-1.2.11使用包管理器安装  
不使用cl编译，改用cygwin64，理论上不支持32位系统  
使用了更偷懒的配方，够用即可

# 使用方法
从网盘下载https://wwvz.lanzoue.com/iwXczkcxf3i
密码:3c9h
双击nginx.exe或双击foreground.bat前台运行

# 简要说明
conf/nginx.conf 为配置文件实例  
RTMP监听 1935 端口，启用live和hls两个application  
推到rtmp://127.0.0.1/hls，密码demo时拉流地址为http://127.0.0.1:8080/hls/demo.m3u8  
推到rtmp://127.0.0.1/live，密码demo时拉流地址为rtmp://127.0.0.1:8080/live/demo
HTTP监听 8080 端口
* :8080/stat 查看stream状态  
* :8080/ [hls.js](https://github.com/video-dev/hls.js) v0.14.17 demo播放hls

# 注意
由于未测试，尚不明确是否支持exec，但是上游明确说明不支持  
由于缺少实验方式，未测试H265的支持情况  
播放工具推荐使用VLC，支持pc和安卓。推流工具推荐OBS

# configure arguments
```
nginx version: nginx/1.17.10
built by gcc 10.2.0 (GCC)
built with OpenSSL 1.1.1i  8 Dec 2020
TLS SNI support enabled
configure arguments:
--prefix=. 
 --with-openssl=../openssl-1.1.1i/ 
 --with-http_ssl_module 
 --add-module=../nginx-rtmp-module-20201202 
```
