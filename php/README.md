### declare(strict_types=1)

- ファイルの先頭に記述することでファイルごとにstrictモードにすることができる
  - 暗黙的型変換を許容しない


### namespace

- phpは同じ名前の関数を定義できないので、関数名が同じ場合は名前空間を分ける必要がある

> 参考記事：https://qiita.com/7968/items/1e5c61128fa495358c1f

### requireとrequire_once

- requireは複数回ファイルの読み込みが可能
- それに対してrequire_onceは一度読み込んだファイルは2回目以降は読み込まないという違いがある

### query() と prepare(),bindValue(),execute() の違い

- `query()`は簡易版
  - 具体的には下記をまとめてやってくれる
    1. 実行したいSQL文をセットする。
    2. SQLに対してパラメーターをセットする。【任意】
    3. 実際にSQLを実行する。

- `prepare()`, `bindValue()`, `execute()`は上記の3手順を1つずつ実行する

- この2つは実行したいSQL文の中に「変動値」が入るかどうかで使い分ける


> 参考記事：https://blog.senseshare.jp/query-prepare.html