---
title: PostgreSQL
date: 2021-05-24
author: xxarupakaxx
layout: default
description: PostgreSQLをインストールした際につまづいた
categories:
    - programming
tags:
    - PostgreSQL
    - GO
    - traP
---
## PostgreSQLをインストールした話
最近GO言語の勉強をしていまして、読んでいる[GOプログラミング実践入門](https://www.amazon.co.jp/Go%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E5%AE%9F%E8%B7%B5%E5%85%A5%E9%96%80-%E6%A8%99%E6%BA%96%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E3%81%A7%E3%82%BC%E3%83%AD%E3%81%8B%E3%82%89Web%E3%82%A2%E3%83%97%E3%83%AA%E3%82%92%E4%BD%9C%E3%82%8B-impress-gear%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA-Sheong-Chang-ebook/dp/B06XKPNVWV?tag=maftracking264432-22&linkCode=ure&creative=6339)で詰まった話をします
### 手順
第二章でChitChatというwebアプリケーションを作成する際にPostgreSQLをインストールします.
まずupdateをしなければ
```
sudo apt update
```
その次にPostgreSQLをインストールします
```
sudo apt install postgresql postgresql-contrib
```
ここでPostgreSQLにログインし、psqlとコマンドを打つと
```
sudo -i -u postgres
postgres@DESKTOP-A482EOT:~$ psql
psql (12.7 (Ubuntu 12.7-1.pgdg18.04+1)、サーバ 12.6 (Ubuntu 12.6-0ubuntu0.20.04.1))
"help"でヘルプを表示します。

postgres=#

```
と出るはずが
```
psql: error: could not connect to server: No such file or directory
        Is the server running locally and accepting
        connections on Unix domain socket "/var/run/postgresql/.s.PGSQL.5432"?     
```
とエラーを吐かれてしまい、なにやらサーバーが稼働していないようです。
そこで`exit`をし、次のコマンドを入力します
```
sudo service postgresql start
```
この後普通に先ほどのコマンドを打つとうまくいきます。

うまくいったあと
```
createuser --interactive
createdb xxarupakaxx
```
を打ち無事データベースの作成完了です。

### 最後に
これからGO言語勉強してちょくちょく気づいたことをブログにしていきたいと思います。


