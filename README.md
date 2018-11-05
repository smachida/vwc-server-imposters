# 概要

Wine Mates アプリケーション - Virtual Wine Cellar(VWC) 仮想サービス:

このアプリケーションは、vwc-server-java (ワイン情報検索 API)のモック実装です。
mountebank(http://mbtest.org) - マウンティバンクを使用しています。

# What's New

2018/11/05: API 0.0.7 の一部に対応しました。
~~~
サポートするAPI
・ワイン
　・IDによる検索: GET /wines/{wineId}  // アメリカ及び日本のワインのみ
　・条件付き検索
　　・国: GET /wines?countryCode={countryCode}
~~~

# HowTo: Build & Run

~~~
# git clone https://github.com/smachida/vwc-server-imposters.git
# cd vwc-server-imposters/bin
~~~

~~~
# ./start-imposters.sh  // 起動

http://localhost:8080/api/v1/wine/wines?countryCode=CC0017 にアクセス

# ./stop-imposters.sh    // 停止
~~~

# 設定ファイル

~~~
bin/json 配下:
・importers.ejs  // 読み込む設定ファイルの指定
・wine-imposters-test.json  // メインの設定ファイル(開発時に使用)
・wine-imposters-full.json  // 多くのAPIを実装(参考)
・hello-imposters.json      // テスト用
~~~

# 依存関係

~~~
前提条件:
nodejs
npm
~~~

~~~
mountebank のインストール:
# npm install -g mountebank
~~~
