# web fuzz attack

对于传统的SQL注入、命令执行等漏洞，相信有很多扫描器已经有所集成。但是对于从中延伸出来的攻击，总会有所缺少，相信这些补充能提高渗透的成功几率。

- 比如参数中有存在json字符串，肯定有人是想利用fastjson、jackson等漏洞利用
- 再比如文件上传，现在仅仅只是一些解析脚本拿到webshell吗？背后可能还存在ImageTragick、Ghostscript等一些处理导致问题，亦或者可以上传html、pdf导致xss，或者是xls，docx导致xxe等等
- 或者是一些cookie中带来的问题，比如shiro反序列化等等

以后慢慢收集更新，欢迎大家在issue提交其他的一些攻击点，对fuzz将会有所帮助。

参考:
https://github.com/modzero/mod0BurpUploadScanner

