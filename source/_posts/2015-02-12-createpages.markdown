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

*[1]Octopressを用いてローカル上にブログ設置*  
- - - 

```  Bash  
$ git clone git://github.com/imathis/octopress.git octopress  
$ bundle install —-path vendor/bundle  
$ rake install  
$ rake generate #staticサイト作成  
$ rake preview #ローカル確認　localhost:4000  
``` 
  
*[2]username+github.io を用いてGitHubPagesを作成*  
- - -

```  Bash  
$ rake setup_github_pages #gitのSSHキー入力  
$ rake generate #staticサイト作成  
$ rake deploy #GitHubにcommitされる.
``` 

*[3]ブログの設定/投稿/OctopressのTheme変更*  
- - -  
[設定]  
``` 
$ vim _config.yml #各自弄ってください.  
```  
[投稿]  
```  
$ bundle exec rake new_post['記事のナンバー(英語)']  # 記事のタイトルは記事書くときに日本語タイトルに変更可  
$ rake gen_deploy #rake generate , rake deploy  
```  
[Theme変更]  
```  
$ git clone themeの保存されているssh .themes/テーマ名  
$ rake install['テーマ名']  
$ rake generate  
```   
  
    
*[4]参考/引用ページ*  
- - -
・[3rd Party Octopress Themes](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes,"3rd Party Octopress Themes")  
・[GitHub Pages + Octopress カスタマイズ](http://qiita.com/syui/items/07365ed24eef63602233,"GitHub Pages + Octopress カスタマイズ")  
・[Octopress簡単スタートガイド](http://www.slideshare.net/yizawa/octopress,"Octopress簡単スタートガイドWorking at 株式会社クルウィット")  
・[GitHub pages + Octopressの導入](http://rcmdnk.github.io/blog/2013/03/07/setup-octopress/,"GitHub pages + Octopressの導入")


