# you2php-heroku

## YouTube 镜像网站, 实现免翻墙访问。
点击使用: https://bot-yt-2.herokuapp.com/<br>
<i>*Heroku App 30 分钟内没有链接会进入休眠状态, 第一次访问时需要 5 秒左右来唤醒 App, 请耐心等待一会.</i>

在官方版的基础上加入的功能:<br> 
1. <b>国家/地区选择</b>, 可以根据地区切换热门内容。（此功能来源于官方文档中介绍的插件）<br>
2. <b>4K播放</b>, 遇到版权或其他问题无法播放的视频, 可以点击右下方的 "4K播放" 观看。（其实是一个 "Web代理" 服务）<br>
3. <b>密码验证</b>(可选), 此功能主要防止 GFW 的主动探测, 使网站更难被封, 使用人数不多时不需要这个功能。<br>

### 本 Fork 更新
3/22/2019<br>
更新了文件中的描述 PHP 版本, 较低的 PHP 版本会导致部署失败。<br>

### 使用方法 v2.0 简易版
1. Fork 项目<br>
在当前页面点击右上角的 Fork 将项目拷贝至自己的 Github 账号下。<br>
2. 登录 heroku<br>
<a href="https://dashboard.heroku.com/apps">点我跳转</a><br>
3. 新建 app<br>
在 heroku 控制台页面点击 右上角的 New 新建一个 app, app 名称将作为网站域名。<br>
4. 关联 Github<br>
创建完 app 后点击 app 进入 app 管理页面, 然后点击 Deploy(默认创建后跳转到这个页面)。<br>
点击页面中的 GitHub/Connect to Github, 会要求你登录 Github, 请登录刚刚 Fork 项目的 Github账号。<br>
5. 部署<br>
当前页面将会显示你关联的 Github 账号, 在 Search for a repository to connect to 选项中输入 you2php-heroku
并点击 Searh, 选择 repo 点击 Connect, 连接完成后, 在最下方点击 Deploy Branch 完成部署。<br>
6. 注意事项<br>
```
1. 域名(app name)起敏感词汇将更容易被封。
2. 越少人用, 越不容易被封, 请低调使用。
3. 可能会因各种原因导致 App 被封(DNS 污染), 这时候在 App 的详情页面处点击 Settings, 在 Name 选项处重新起一个不一样名字, 然后使用新的 URL 地址访问(如: newAppName.herokuapp.com)。
4. heroku 会定期停用对低版本的 PHP 的支持, 这个时候需要你根据错误提示, 修改 composer.lock 和 composer.json 中的描述。
5. 强烈建议使用自己的 API KEY 部署, 教程见下方"其他建议"。
6. 强烈建议启用密码保护, 教程见下方"其他建议"。
```

### 自定义网站配置(可选)
如果你想修改网站名等配置，直接在 Github 上编辑 web/config 文件。<br>
```
<?php
$gl=(isset($_COOKIE['gl']) && $_COOKIE['gl'])?$_COOKIE['gl']:'US';
define('ROOT_PART', Root_part());
define('APIKEY', 'please input your APIKEY');
define('GJ_CODE', $gl);
define('SITE_NAME', 'please input your SiteName');
define('TITLENAME', 'please input your SiteTitle');
define('EN2DEKEY', 'please input EncryptKey, randome generate');
define('EMAIL', 'please input your Email');
?>
```
APIKEY 的申请方法见下方的官方教程。

### 其他建议
官方教程(已被墙): <a href="https://you2php.github.io/doc/">https://you2php.github.io/doc/</a><br>
官方教程(通过 Web 代理访问)：<a href="https://proxy.littlepotato.tk/-----https://you2php.github.io/doc/">https://proxy.littlepotato.tk/-----https://you2php.github.io/doc/</a><br>
1. 使用自己的 Google API Key 防止网站达到每日请求上限。如何申请见 -> <a href="https://you2php.github.io/doc/">官方教程</a><br>
2. 当使用人数较多时, 建议设置密码阻止 GFW 的主动探测(不容易被封)。如何设置密码见 -> <a href="https://you2php.github.io/doc/">官方教程</a><br>
