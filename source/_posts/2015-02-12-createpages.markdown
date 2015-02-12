---
layout: post
title: "OctopressとGitHubでブログ作成"
date: 2015-02-12 17:40:47 +0900
comments: true
categories: memo
---
### 経緯  
Github.io ってかっこよくね?  
  
### 作成 
1.  Octopressを用いてローカル上にブログ設置  
``` Bash  
$ git clone git://github.com/imathis/octopress.git octopress  
$ bundle install —-path vendor/bundle  
$ rake install  
$ rake generate #staticサイト作成  
$ rake preview #ローカル確認　localhost:4000  
``` 
  
2. username+github.io を用いてGitHubPagesを作成  
``` Bash  
$rake setup_github_pages #gitのSSHキー入力  
$rake generate #staticサイト作成  
$rake deploy #GitHubにデプロイ(コミット)  

``` 

