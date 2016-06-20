Docker容器化PHP开发环境搭建-DVWA (含xdebug调试)
=

Docker容器化技术在过去的2015年得到了大面积的普及应用，特别是以灵雀云、数人云、阿里云以及阿里百川TAE2.0等为代表的服务商的推动，可以预见2016会是云服务大爆发的一年，会有越来越多的互联网企业将自己的业务部署到基于Docker容器的环境里来。

本文以[DVWA](https://github.com/MarkThink/DVWA)部署为例，来讲解PHP环境部署+基于XDEBUG调试环境的容器化解决方案。

[segmentfault参考链接](http://segmentfault.com/a/1190000002528341)

![PHP配置图](images/docker_php.png)


##创建目录

###基础目录

- ~/data/data  		存放MySQL数据库
- ~/data/wwwroot 	项目代码
- ~/data/log		存放所有输出log

###从代码仓库构建

```
cd ~
git clone https://github.com/MarkThink/DockerPHP.git data
```

##创建这些目录

```
mkdir ~/data ~/data/data ~/data/data/mysql ~/data/log ~/data/log/nginx ~/data/log/php ~/data/wwwroot
```

##下载镜像及构建

```
cd ~/data/wwwroot/lnmp
make pull
make dl
make build
```

##下载代码

```
cd ~/data/wwwroot
git clone https://github.com/MarkThink/DVWA.git data_app
```


##IDE调试配置

![IDE配置一](images/phpstrom_1.png)

![IDE配置二](images/phpstrom_2.png)


##绑定域名

```
sudo vi /etc/hosts

192.168.99.100	www.data.com
```

###Happly Enjoy!



