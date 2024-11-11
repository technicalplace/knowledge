### declare(strict_types=1)

- ファイルの先頭に記述することでファイルごとにstrictモードにすることができる
  - 暗黙的型変換を許容しない


### namespace

- phpは同じ名前の関数を定義できないので、関数名が同じ場合は名前空間を分ける必要がある

> 参考記事：https://qiita.com/7968/items/1e5c61128fa495358c1f

### requireとrequire_once

- requireは複数回ファイルの読み込みが可能
- それに対してrequire_onceは一度読み込んだファイルは2回目以降は読み込まないという違いがある