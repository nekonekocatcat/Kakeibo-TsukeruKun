かけいぼつけるくん
===

# アプリ概要
日々の支出を、カレンダーやグラフを使って管理することができるWebアプリケーション

# 実行方法
このリポジトリをクローンして、ターミナルで、`$python main.py`で実行すると、以下のようなメッセージが表示されます。<br>
ターミナルに表示される http://127.0.0.1:8888 にアクセスすることで、実行確認ができます。
```
* Serving Flask app 'main'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:8888
Press CTRL+C to quit
```

また、VSCodeを使用する場合は、Run Codeで実行すると、出力に上記と同じメッセージが表示されます。<br>
出力に表示される http://127.0.0.1:8888 にアクセスすることでも実行確認ができます。

main.pyの場所は、このリポジトリのルートディレクトリに配置されています。`./main.py`<br>
詳細は、以降に記述されている「ディレクトリ構造」を参照してください。

# 環境構築

このWebアプリケーションは、2024年オブジェクト指向プログラミングの授業と全く同じ環境で開発されました。
2024年オブジェクト指向プログラミングを受講した人は、以下のディレクトリにこのリポジトリをクローンすることを推奨します。
```
.
└── work
    └──opp2
        └── ここに、このリポジトリをクローンすることを推奨します。
```

また、このWebアプリケーションは、CDNを利用したJavaScriptライブラリを使用しています。そのため、ネットがつながる環境で実行してください。
推奨ブラウザは、Google Chromeです。

- Python関連
  - python:3.11.5(pyenv)
  - flask
- javascript関連
  - Chart.js:2.7.2

# ディレクトリ構造

このリポジトリの簡単なディレクトリ構造です。

```
.
├── README.md　　このWebアプリの仕様が書いてあります。
├── modules  自作のpythonのプログラムが入っています。また、データ保存用のjsonファイルが作られます。
    ├── expenditure_data_manager.py  データ保存に関するプログラムです。
    └── (balance_of_account.json)  データ保存用のjsonファイルです。プログラムを実行すると作成されます。
├── static  静的ファイル(javasript, css, ファビコン画像)が入っています。
    ├── PieChart.js  円グラフ描画用のプログラムです。
    ├── calendar.js  カレンダー描画用のプログラムです。
    ├── calendar.css  カレンダー用のCSSです。
    └── style.css  全画面共通部分のCSSです。
├── templates  HTMLが入っています。
    ├── calendar.html　 カレンダー表示用のhtmlです。
    ├── graph.html　　円グラフ表示用のhtmlです。
    └── input.html データ入力のためのhtmlです。プログラムを実行すると、この画面が開きます。
└── main.py  実行確認の時は、このプログラムを実行してください。

```


# 画面遷移図
![kakeibo.png](https://github.com/2023AIT-OOP2-G14/Kakeibo/blob/main/kakeibo.png)

# 入力ページの説明
![input_md.png](https://github.com/2023AIT-OOP2-G14/Kakeibo/blob/main/input_md.png)
- 金額を入力(半角)
- カテゴリーを入力(食費、衣服など)
- 日付を選択
- 入力されたものを保存

# グラフページ 
![graph_md.png](https://github.com/2023AIT-OOP2-G14/Kakeibo/blob/main/graph_md.png)
- 入力ページで保存されたカテゴリーと金額を円グラフと表として表示
- カーソルをグラフに合わせるとそのカテゴリーの合計金額を表示
- グラフの上の入力された各カテゴリーをクリックするとそのカテゴリーを除いたグラフを表示する

# カレンダーページ
![calendar.png](https://github.com/2023AIT-OOP2-G14/Kakeibo/blob/main/calendar.png)
- 日付ごとや月ごとの合計支出が一目でわかる
- 日付を選択するとその日の各カテゴリー支出がわかる
- 月指定で年月の直接指定もできる 
