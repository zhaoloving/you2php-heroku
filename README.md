### 本 Fork 更新:<br>

3/22<br>
1. 更新了文件中的描述 PHP 版本, 因为 hero 不支持较低的 PHP 版本会导致部署错误.<br>
2. 去掉了密码验证, 方便观看.<br>
3. 更新了 config 设置. 请在 confing.php 文件中自定义网站名字, 以及参考官方文档设置自己的 API key, 当部署此 Fork 人数过多, API 配额用尽时网站将不可用.<br>


<b>YouTube 镜像网站, 实现免翻墙访问.</b>
点击使用: https://youtubemirror-usa.herokuapp.com/<br>

### 使用方法

1. 下载 heroku CLI 客户端: https://devcenter.heroku.com/articles/getting-started-with-php#set-up <br>
2. 部署 <br>
$ heroku login<br>
$ git clone https://github.com/justsweetpotato/you2php-heroku.git <br>
修改 web/config.php 文件.<br>
$ cd you2php-heroku <br>
$ heroku create [You APP Name]<br>
$ heroku git:remote -a [You APP Name]<br>
$ git add .<br>
$ git commit -am "make it better"<br>
$ git push heroku master<br>
$ heroku ps:scale web=1<br>
$ heroku open<br>
 
<br>

