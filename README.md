### 本 Fork 更新:<br>

3/22<br>
1. 更新了文件中的描述 PHP 版本, 因为 heroku 现在不支持较低的 PHP 版本, 会导致部署错误.<br>
2. 去掉了密码验证, 方便观看.<br>
3. 更新了 config 设置. 请在 confing.php 文件中自定义网站名字, 以及参考官方文档设置自己的 API key, 当部署此 Fork 人数过多, API 配额用尽时网站将不可用.<br>


<b>YouTube 镜像网站, 实现免翻墙访问.</b><br>
点击使用: https://good--job.herokuapp.com/<br>

<br>

### 使用方法

1. 下载 heroku CLI 客户端: https://devcenter.heroku.com/articles/getting-started-with-php#set-up <br>
2. 部署 <br>
```
$ heroku login
$ git clone https://github.com/justsweetpotato/you2php-heroku.git 
# 修改 web/config.php 文件.
$ cd you2php-heroku 
$ heroku create [You APP Name]
$ heroku git:remote -a [You APP Name]
$ git add .
$ git commit -am "make it better"
$ git push heroku master
$ heroku ps:scale web=1
$ heroku open
 ```
3. 修改 web/config 文件.<br>
```
<?php
$gl=(isset($_COOKIE['gl']) && $_COOKIE['gl'])?$_COOKIE['gl']:'US';
define('ROOT_PART', Root_part());
define('APIKEY', '你的 APIKEY');
define('GJ_CODE', $gl);
define('SITE_NAME', '你的网站名');
define('TITLENAME', '你的网站title');
define('EN2DEKEY', '一个随机字符串, 用于加密');
define('EMAIL', '你的邮箱, 用于处理版权纠纷');
?>
```
<br>

### 其他建议: <br>
1. 建议使用自己的 Google API Key 防止网站达到每日请求上限.<br>
2. 建议设置密码, GFW "似乎"加大了对 You2Php 的检测力度, 建议使用密码保护.<br>

以上均可以参考这篇教程: https://you2php.github.io/doc/ <br>

<br>
