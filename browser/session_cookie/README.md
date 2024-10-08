## CookieとSessionの違い

**セッションは目的でありクッキーは手段である**

- セッション
**複数のリクエストをサーバーがブラウザから受け取ったときにサーバー側が同一ユーザーと認識すること**

1. httpプロトコルはステートレス（状態を持たない）のため同じユーザーが同じサイトを何度も訪れたとしても初めて訪問したことになってしまう
挨拶したことは何回もあるのに顔を覚えてくれないイメージ

2. それに対してセッションがあれば前回訪れたユーザーのことを覚えてくれる
3. なぜセッションを使うとサーバーは前回訪問したユーザーだとわかるのか
4. それはクッキーを使って判断する

**CookieでSessionを実現している**
1. 初回訪問時にサーバーにクッキーをあげる
2. サーバーがその味を覚える
3. ブラウザは2回目以降の訪問時も同じクッキーをあげる
4. サーバー側はクッキーを食べてあのときくれた味と同じだ！と判断しているイメージ

**ではそのクッキーって誰が作るの？**
- サーバーが作ってブラウザに渡す（サーバーサイドCookie）

> 参考動画
https://www.youtube.com/watch?v=EgUgmYLuLYE