## バックエンド
- `NextResponse`
  - これはNext.jsが用意しているものでリクエストに対するレスポンスを返してくれる


基本的な使いかた
```
import { NextResponse } from "next/server";

export async function GET() {
  return NextResponse.json({ message: "こんにちは" });
}
```

## middleware
Next.jsではルート階層（フォルダの一番上）でファイルを作成するとアプリ全体に対して機能する

### matcher
- `matcher`とはmiddlewareを適用させるフォイルを指定する

```
export const config = {
  matcher: ["/api/item/create", "/api/item/update/:path*", "/api/item/delete/:path*"],
}
```
- Next公式：https://nextjs.org/docs/app/building-your-application/routing/middleware
- 参考記事：https://zenn.dev/hayato94087/articles/ec16174696a375

### ルートグループ
- Next.jsのappRouterはappディレクトリ配下がパスになる
そのためuserディレクトリ、adminディレクトリのようにグループ分けするときにパスが長くなってしまう。
これを回避するためにルートグループを作成することができる
使い方は簡単で(main)や(admin)のようにカッコをつけた名前でディレクトリを作成すればいい

> 参考動画：https://www.udemy.com/course/nextjs-fullstack/learn/lecture/42377760#overview

### ルートハンドラー

- ルートハンドラーとはexpressやNest.jsで開発されていたAPIをNext.js上で開発するためのもの

- デフォルトでは静的ビルドのため取得するデータが決まっている場合はいいが、SNSなどユーザーの動作によって取得するデータが変わる場合、データが更新されず古いデータが表示される問題が発生する