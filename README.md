#Fxh.Go

### 克隆源 [oschina](http://git.oschina.net/fuxiaohei/fuxiaohei-go)

一款动态博客引擎，基于 golang语言 开发的 [GoInk](https://github.com/fuxiaohei/GoInk) Web框架开发。

[![Build Status](https://drone.io/github.com/luopengift/goblog/status.png)](https://drone.io/github.com/luopengift/goblog/latest)
[![GoWalker](http://b.repl.ca/v1/Go_Walker-API_Documentation-green.png)](http://gowalker.org/github.com/luopengift/goblog)

当前版本 **0.2.5** ( 2014.02.28 )

开发进度可以在  [Trello](https://trello.com/b/7AHrcQL8/fxh-go-with-goink) 面板查看。

### 概述

`Fxh.Go` 是一款golang开发的，简单快速的动态博客引擎，支持json数据保存，zip压缩备份和自动脚本升级。文章和页面支持markdown格式，支持ajax评论。

`Fxh.Go`带有后台管理页面，可以动态查看和操作站点。


### 安装

`Fxh.Go` 需要 **Go 1.2** 版本（进行安装）。

##### Gobuild.io

[Gobuild.io](http://gobuild.io/) 支持跨平台编译纯go项目。 点击图标可以下载对应版本的二进制包，并立刻直接运行。

[![Gobuild Download](http://gobuild.io/badge/github.com/luopengift/goblog/download.png)](http://gobuild.io/github.com/luopengift/goblog)

二进制文件不需要go语言编译环境。

##### 手动

使用 go get 命令:

    go get github.com/luopengift/goblog

可以编译出 `goblog(.exe)` ，保存在 `$GOPATH/bin`。

### 运行

创建一个新文件夹运行 `Fxh.Go`:

    cd new_dir
    goblog

博客将自解压静态文件到文件夹 `new_dir` , 初始化默认数据，并开始监听 `localhost:9001`。

##### 后台

访问 `localhost:9001/login/` 输入用户名`admin`和密码 `admin`。实际使用可以修改管理员帐户。

##### 部署

最好用nginx做前端代理。`nginx.conf`中的配置:

        server {
                listen       80;
                server_name  your_domain;
                charset utf-8;
                access_log  /var/log/nginx/your_domain.access.log;

                location / {
                    proxy_pass http://127.0.0.1:9001;
                }

                location /static {
                    root            /var/www/your_domain;  # binary file is in this directory
                    expires         1d;
                    add_header      Cache-Control public;
                    access_log      off;
                }
        }

### 建议

可以在这个项目提交issue和pull request。

### Products

* [抛弃世俗之浮躁，留我钻研之刻苦](http://wuwen.org)
* [FuXiaoHei.Me](http://fuxiaohei.me)

### Thanks

* [@Unknwon](https://github.com/Unknwon) 测试 [zip 库](https://github.com/Unknwon/cae) 支持。

### License

The MIT License
