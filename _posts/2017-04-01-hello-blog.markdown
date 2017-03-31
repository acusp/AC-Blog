---
layout:     post
title:      "使用 Github Pages 与Jekyll 搭建博客"
subtitle:   "Welcome to Acusp Blog
date:       2015-01-29 12:00:00
author:     "Acusp"
header-img: "img/post-bg-2015.jpg"
tags:
    - 教程
---


## 前言
[TOC]

## 0x00 准备工作

域名：https://www.godaddy.com/
域名解析：https://www.dnspod.cn/
百度分析：https://tongji.baidu.com/
Google Analystic：https://analytics.google.com


GitHub Pages gem：https://pages.github.com/
jekyll：http://jekyllcn.com/ , http://jekyllrb.com/


## 0x01 安装 Jekyll

**Step 1: Install [Bundler](http://bundler.io/)**:

Check whether you have [Ruby 2.1.0](https://www.ruby-lang.org/en/downloads/) or higher installed:
``
ruby --version
``

Install Bundler:
``
gem install bundler
``

**Step 2: Install Jekyll**:

create `Gemfile`, and add these lines to it:
``
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
``

Install Jekyll and other [dependencies](https://pages.github.com/versions/) from the GitHub Pages gem:
``
bundle install
``

>Tip: If you see a Ruby error when you try to install Jekyll using Bundler, you may need to use a package manager, such as RVM or Homebrew, to manage your Ruby installation. For more information, see [Jekyll's troubleshooting page](http://jekyllrb.com/docs/troubleshooting/#jekyll-amp-mac-os-x-1011).

**Step 3: Build your local Jekyll site**:

Run your Jekyll site locally:
``
bundle exec jekyll serve
``
Preview your local Jekyll site in your web browser at http://localhost:4000.

**Keeping your site up to date with the GitHub Pages gem**
``
bundle update github-pages // or bundle update
``


## 0x02 配置 Jekyll

> https://help.github.com/articles/configuring-jekyll/

You can configure most Jekyll settings by editing your _config.yml file.
