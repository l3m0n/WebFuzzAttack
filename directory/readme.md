在信息收集中，目录扫描也是必不可少的，因为它能够让你更好的了解一个应用的结构，当然运气好的话，则会遇到具有价值的页面，比如phpinfo、未授权高危操作页面、他人的webshell等。

但是在扫描目录的时候，其实还可以尝试做其他的测试，比如目录穿越

1、CVE-2007-0450: apache mod_proxy
Apache HTTP Server and Tomcat 5.x before 5.5.22 and 6.x before 6.0.10
利用%5c: /josso/%5C../web-console

https://hackerone.com/reports/502758

2、nginx配置不当
location /static {
    alias /var/www/static/;
    autoindex on;
}

当访问/static../就是访问static的上一级目录
https://www.cnblogs.com/iamstudy/articles/2016_hctf_web_writeup.html

3、mod_jk
/..;/

https://github.com/orangetw/My-CTF-Web-Challenges#blackbox

4、django
/static/../../../../../etc/passwd

http://www.anquan.us/static/drops/papers-5040.html

