### displayの違いによるwidthとheightの決まり方

- ブロック要素
  - 横幅
    - デフォルトwidth100%が設定されている為、横幅を指定しない場合親要素の横幅が要素の横幅になる
  - 高さ
    - 高さを指定しない場合、子要素の合計値が高さ

- インライン要素
  - 横幅
    - 中身の大きさや長さによって決まるため指定はできない
  - 高さ
    - 中身の大きさや長さによって決まるため指定はできない

- インラインブロック要素
  - 横幅
    - 並び方がinline的になり指定可能
  - 高さ
    - 並び方がinline的になり指定可能

### position fixedとstickyの違い

- fixedは画面（ビューポート）に対して常に固定される、そのため最初から指定された位置に配置される

- stickyはスクロールして指定した位置に達したときに初めて固定される


### 文字コード utf-8について
- htmlの文字コード（utf-8）とそれを表示するブラウザの文字コードが異なると文字化けが発生する、そのためmeta情報に文字コードの指定をする


### scss @content

- `@include sp {}`の部分が`@content`の部分に挿入される

> 参考記事：https://qiita.com/annaaida/items/a0794a6d38fc1327085a#content-%E3%81%AE%E4%BD%BF%E3%81%84%E6%96%B9

```scss
@mixin hoge {
  @media screen and (max-width: ◯◯px) {
    @content;
  }
}
```

`使用側`

```scss
@use "mixin(ファイルまでのパス)" as mixin;
@include mixin.hoge {
  // スタイル
}
```

### pointer-events none の効果
- 要素に対してクリックイベントを無効にする
- 上記だけではなく親要素をクリック不可にして子要素をクリック可能にすることができる
> 参考記事：https://tips-web.net/how-to-clickable-only-child-elements/


### line-clamp

-  n 行目移行が非表示にすることができる

> 参考記事：https://zenn.dev/aew2sbee/articles/tailwind-css-line-clamp
> 参考記事：https://blog.to-ko-s.com/tailwind-css-truncate-line-clamp/


### テキストのカラーにグラデーションを入れる

> 参考記事：https://kingsite.jp/blog/0188


### 画像が横スクロールし続ける無限ループ

> 参考記事：https://rita-plus.com/blog/css-animation-scroll-infinity/