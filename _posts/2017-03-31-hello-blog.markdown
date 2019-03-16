---
layout:     post
title:      "Github Pages + Jekyll 搭建博客"
subtitle:   " \"Hello World, Hello Blog\""
date:       2017-03-31 01:00:00
author:     "Acusp"
header-img: "img/post/20170331/post-bg-2017-03-31.jpg"
catalog: true
tags:
    - blog
---



>
这篇文章是为了记录自己搭建博客的过程，同时也希望能给新手一点指导作用；
阅读这篇文章之前，希望读者有基本的计算机操作技能，如：在 macOS/Linux 下会使用简单的终端命令;
如果在阅读的过程中遇到一些文章中没有详细介绍的细节，希望读者可以多利用搜索引擎，提高自己解决问题的能力



## 0x01 Github Pages


#### 1.1 准备工作


因为我们的博客是搭建在 Github 上的，所以首先需要读者拥有自己的 Github 账号。

如果没有请先到[官网](https://github.com/)进行注册，注册方法与一般的网站注册方法类似，这里不进行细说。


#### 1.2 创建仓库


登录到自己的 Github 账号后，点击右上角头像旁边的加号，选择 `New repository` 创建一个新的仓库；

在填写仓库的信息时，需要注意：`Repository name` 必须为：`USERNAME.github.io`，其中 USERNAME 为你的 Github 用户名, 请修改为自己的名字；

如：我的仓库名为 `acusp.github.io` (因为我的仓库已经存在，所以有红色的提示信息，请忽略)：

![创建新仓库](/img/post/20170331/17-03-31-01-create-new-repository.png)


#### 1.3 克隆仓库到本地电脑


读者需要根据自己的操作系统，安装相应的 git 工具，然后在命令行执行下列命令:


> 下列命令中的 username 需要修改为自己的 Github 用户名


```
git clone https://github.com/username/username.github.io

cd username.github.io
echo "Hello World" > index.html

git add --all
git commit -m "Initial commit"
git push -u origin master
```


上面的操作需要读者有一定的命令行操作经验，如果不会使用命令行，可以在 Github 官网下载图形化的客户端，具体操作请自行搜索。


#### 1.4 浏览网页


不出意外的话，这时候我们就可以在浏览器中输入: `http://USERNAME.github.io` 访问自己的网站了；只是这个时候我们看到的只有 `Hello World` 这一句话而已。



## 0x02 使用 Jekyll 主题

使用 Jekyll 主题可以让我们免去很多复杂的配置，而且可以根据自己的喜好，选择不同的风格；

用现成的主题可以让我们在最短的时间里搭建起一个漂亮且实用的博客，可以为你省去不少宝贵的时间。

你可以在[这里](https://github.com/jekyll/jekyll/wiki/Themes)找到很多好看的主题，进入到主题对应的 Github 仓库，你可以根据说明，将主题运用的自己的博客当中。

大部分的主题只需要你将其下载到你的 username.github.io 文件夹下，然后修改 `_config.yml` 文件中的配置；其他细节责需要根据其 README.md 中的说明进行修改即可。




## 0x03 安装 Jekyll


> Jekyll 的官网 http://jekyllcn.com/ , 中文网站: http://jekyllrb.com/

为了方便写作，同时也为了让我们的博客看起来更高大上，我们可以使用 Jekyll。

Jekyll 不但可以自动将我们写的 markdown 格式的文章转换为静态 html 网页，而且还有很多好看的主题可供选择。

为了使用 Jekyll，我们必须在电脑上安装命令行工具，macOS/Linux 系统已经自带了命令行工具可直接使用，而 Windows 用户需要自己安装 [git](https://git-for-windows.github.io/) ，安装完成后便会有一个 git bash 命令行。具体的操作读者可自行搜索。


#### 3.1 安装 [Bundler](http://bundler.io/)


首先查看是否已经安装了 Ruby 2.1.0 以上的版本: `ruby --version`

如果没有安装 ruby，或安装的版本低于 2.1.0，请到[官网](https://www.ruby-lang.org/en/downloads/)根据说明自行安装。

安装 ruby 后，使用 gem 安装 Bundler: `gem install bundler`


#### 3.2 安装 Jekyll


在 username.github.io 目录中创建一个名为 `Gemfile` 的文件, 并且在文件中写入下列内容:



```
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
```


然后使用命令 `bundle install` 自动安装 Jekyll 及其依赖。


> 注意：如果安装过程中出现了错误，请在搜索引擎中搜索错误的关键字，自己解决问题。


#### 3.3 生成本地网站预览


执行下列命令，Jekyll 会在本地生成一个网站服务器，你可以在浏览器中输入地址 `http://localhost:4000` 查看自己的博客。

```
bundle exec jekyll serve
```


#### 3.4 更新 Github Pages 插件

为了保证本地预览的效果与上传到 Github 上的效果保持一致，我们需要经常跟新 github pages 的插件

```
bundle update github-pages
```

github pages 官网版本：https://pages.github.com/versions/



## 0x04 自定义域名


Github Pages 还有一个好处就是支持用户自定义域名，而不是只能使用默认的 username.github.io。


#### 4.1 配置域名


在使用自定义域名之前，我们需要自己购买域名。购买域名的网站很多，读者可以自行搜索选择适合自己的。

我的域名是在 [godaddy](https://www.godaddy.com/) 上购买的，它支持支付宝付款，还是挺方便的。

购买了自己的域名之后，我们可以将域名添加到自己的 username.github.io 仓库中配置中去。

首先进入到 username.github.io 仓库页面，点击右上角的 `Settings`:

![Settings](/img/post/20170331/17-03-31-02-settings.png)

然后在 Github Pages -> Custom domain 中填入自己的域名：

![add custom domain](/img/post/20170331/17-03-31-03-add-custom-domain.png)


#### 4.2 域名解析

填写完域名后，还不能直接通过自定义的域名访问自己的博客，我们需要通过域名服务器帮我们把自定义的域名与 username.github.io 关联起来。

这里我使用的是 [DNSPOD](https://www.dnspod.cn/)。注册登录后，我们可以添加一个域名解析服务:

![domain parser](/img/post/20170331/17-03-31-04-domain-parser.png)

创建完毕后，进入到添加的域名中进行如下配置：

![domain parser](/img/post/20170331/17-03-31-05-domain-parser.png)

> 注意：新创建的域名解析中会默认包含两条记录，我们只需要添加红框中的三个，其中最后一个的记录值填写自己的 username.github.io


#### 4.3 DNS 管理

最后再回到购买域名的网站，登录自己的账号，找到域名设置中的 DNS 管理功能。

将 [4.2] 域名解析中的默认的两条记录的记录值加入到域名服务器，如:

![dns managemeng](/img/post/20170331/17-03-31-06-dns-management.png)

> 注意：不同的域名网站，DNS 的管理功能可能会有所不同，可以通过搜索引擎查找符合自己的方法



## 0x05 总结

到目前为止，我们已经有了一个属于自己的博客。希望大家可以坚持写作，记录自己在学习、生活中的点点滴滴，不断提升自己。

在搭建博客的过程中，大家可能会或多或少的遇到各种问题，我这里不可能做到面面俱到，所以希望大家可以多利用搜索引擎，学会自己解决问题。

最后谢谢您的阅读。
