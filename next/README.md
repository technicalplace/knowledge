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