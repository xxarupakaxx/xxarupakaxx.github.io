## アルパカのブログ

こんにちは～
ブログをはじめました。最初に[ポートフォリオ](https://xxarupakaxx.github.io/info/2021/05/23/introduction.html)を見てもらえると嬉しいです。

[https://trap.jp/author/xxarupakaxx/](https://trap.jp/author/xxarupakaxx/)の方でも記事を投稿しているのでぜひ～

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
