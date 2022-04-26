# Newsboatの使い方

NewsboatはRSS/Atomフィードリーダーです。端末で軽快に動きます。

* OS:Linux Mint 20.03
* Ver.:newsboat 2.18-2
* 公式HP
https://newsboat.org/releases/2.27/docs/newsboat.html 
## インストール
```
sudo apt-get install newsboat
```

インストールが終わると次のデレクトリーとファイルができています。
```
~/.newsboat
    cache.db
    config
```


### 稼働確認 エラーメッセージでるか？
urlsを作ってくださいとのメッセージがでます。
イントールが終わった時点ではありません。
```
$ newsboat

newsboat2.18.0を起動中…
設定を読み込み中…完了しました。
キャッシュを読み込み中…完了しました。
/home/hoge/.newsboat/urlsからURLを読み込み中…完了しました。
Error: no URLs configured. Please fill the file /home/hoge/.newsboat/urls with RSS feed URLs or import an OPML file.
```

## urlsというファイルを作成する。

２つ方法があります。

### 直接フィードのリンク先を書き込みする。

urls ファイルの内容    
```urls
https://b.hatena.ne.jp/hotentry.rss
https://news.yahoo.co.jp/rss/topics/world.xml
https://news.yahoo.co.jp/rss/topics/domestic.xml
https://news.yahoo.co.jp/rss/topics/business.xml
```

### OPMLファイルを読み込んでフィードのリンク先を書き込みする。
OPMLファイルはRSSで使用する汎用ファイルです。
このファイルは他のプログラムで作成します。現在使用しているRSSプログラムがあったら作れるどうか調べてください。

```
$ newsboat -i hoge.opml
Import of hoge.opml finished.
```

OPMLファイルの内容
```
<?xml version="1.0" encoding="UTF-8"?>
<opml version="2.0">
    <head>
        <title>QuiteRSS</title>
        <dateModified>日 4月 24 14:08:07 2022</dateModified>
    </head>
    <body>
        <outline text="QuiteRSS" type="rss" htmlUrl="http://quiterss.org/en/frontpage" xmlUrl="https://quiterss.org/en/rss.xml"/>
        <outline text="はてなブックマーク - 人気エントリー - 総合" type="rss" htmlUrl="https://b.hatena.ne.jp/hotentry/all" xmlUrl="https://b.hatena.ne.jp/hotentry.rss"/>
        <outline text="ライブドアニュース - 主要トピックス" type="rss" htmlUrl="https://news.livedoor.com" xmlUrl="https://news.livedoor.com/topics/rss/top.xml"/>
        <outline text="【海外の反応】 パンドラの憂鬱" type="rss" htmlUrl="http://kaigainohannoublog.blog55.fc2.com/" xmlUrl="http://kaigainohannoublog.blog55.fc2.com/?xml"/>
        <outline text="海外反応！ I LOVE JAPAN" type="rss" htmlUrl="http://blog.livedoor.jp/zzcj/" xmlUrl="http://blog.livedoor.jp/zzcj/index.rdf"/>
        <outline text="Yahoo!ニュース・トピックス - 科学" type="rss" htmlUrl="https://news.yahoo.co.jp/topics/science?source=rss" xmlUrl="https://news.yahoo.co.jp/rss/topics/science.xml"/>
        <outline text="Yahoo!ニュース・トピックス - 経済" type="rss" htmlUrl="https://news.yahoo.co.jp/topics/business?source=rss" xmlUrl="https://news.yahoo.co.jp/rss/topics/business.xml"/>
        <outline text="Yahoo!ニュース・トピックス - 国内" type="rss" htmlUrl="https://news.yahoo.co.jp/topics/domestic?source=rss" xmlUrl="https://news.yahoo.co.jp/rss/topics/domestic.xml"/>
        <outline text="Yahoo!ニュース・トピックス - 国際" type="rss" htmlUrl="https://news.yahoo.co.jp/topics/world?source=rss" xmlUrl="https://news.yahoo.co.jp/rss/topics/world.xml"/>
        <outline text="All About（オールアバウト） [恋愛]" type="rss" htmlUrl="https://rss.allabout.co.jp/aa/latest/ch/relationship/" xmlUrl="https://rss.allabout.co.jp/aa/latest/ch/relationship/"/>
        <outline text="朝日新聞デジタル" type="rss" htmlUrl="http://www.asahi.com/" xmlUrl="http://www.asahi.com/rss/asahi/newsheadlines.rdf"/>
        <outline text="All About（オールアバウト） [人気記事ランキング]" type="rss" htmlUrl="https://rss.allabout.co.jp/aa/ranking/" xmlUrl="https://rss.allabout.co.jp/aa/ranking/"/>
        <outline text="ライフハッカー［日本版］" type="rss" htmlUrl="https://www.lifehacker.jp" xmlUrl="https://www.lifehacker.jp/feed/index.xml"/>
    </body>
</opml>

```
## 画面レイアウト
### メイン画面 
![01](https://user-images.githubusercontent.com/4030737/165195630-a35d9bdc-7afd-49d7-b729-08467670f5ce.png)


|キー|機能|
| ------ |------|
|q|閉じる：終了  |
|ENTER |そのフィードの一覧を開く。|
|n|次のフィードの一覧へ移動する。    |
|r|そのフィードの更新を行う。     |
|R|全部のフィードの更新を行う。     |
|A|そのフィードを既読する。     |
|C|全部のフィードの既読する。     |
|/|全部のフィードの検索する。    |
|?|ヘルプ     |



### 記事の一覧
![02](https://user-images.githubusercontent.com/4030737/165195665-afd99bb1-f493-40a4-94f7-d344237bfa33.png)


|キー|機能|
| ------ |------|
|q|閉じる  |
|ENTER |その記事を開く。|
|s|その記事を保存する。    |
|r|その記事の更新を行う。（わかりません。）     |
|n|次の未読の記事へ移動する。    |
|A|フィードを既読する。     |
|/|全部のフィードの検索する。    |
|?|ヘルプ     |


* ここで'o'を押しブラウザーでデータを読むことができる。 

### 記事の内容
![03](https://user-images.githubusercontent.com/4030737/165195706-46205b03-2f9a-4015-a79e-c560e5462e20.png)


|キー|機能|
| ------ |------|
|q|閉じる |
|s|この記事を保存する。    |
|o|ブラウザーで開く。     |
|e|コンテンツをダウンロードする。（わかりません。）     |
|?|ヘルプ     |

## configを書いてみる。

```
browser w3m %u
#browser firefox %u

auto-reload yes

bind-key k prev
bind-key j next

color background          white   black
color listnormal          white   black
color listfocus           yellow  blue   bold
color article             white   black

```
サンプルです。ブラウザーはw3mにしています。
画像が見たいときにはw3mで'ｍ'のコマンドを使います。別のブラウザーが開きます。


ここに参考になる物があります。
```
/usr/share/doc/newsboat/contrib/

```
## 起動時オプション

```
ニュースボート2.22
使用法：./ newsboat [-i <file> | -e] [-u <urlfile>] [-c <cachefile>] [-x <command> ...] [-h]
    -e、-export-to-opmlOPMLフィードをstdoutにエクスポートします
    -r、-refresh-on-start開始時にフィードを更新します
    -i、-import-from-opml =<file>OPMLファイルをインポートします
    -u、-url-file =<urlfile><urlfile>からRSSフィードURLを読み取ります
    -c、-cache-file=<cachefile>は<cachefile>をキャッシュファイルとして使用します
    -C、-config-file =<configfile><configfile>から構成を読み取ります
    -X、-vacuumはキャッシュを圧縮します
    -x、-execute =<command>...コマンドのリストを実行します
    -q、-静かな静かなスタートアップ
    -v、-versionバージョン情報を取得します
    -l、-log-level = <loglevel>特定のログレベルでログを書き込みます（有効な値：1〜6）
    -d、-log-file=<logfile>出力ログファイルとして<logfile>を使用します
    -E、-export-to-file=<file>既読記事のリストを<file>にエクスポートします
    -I、--import-from-file =<file><file>から読んだ記事のリストをインポートします
    -h、-helpこのヘルプ
        --cleanup参照されていないアイテムをキャッシュから削除します

```



