### migration

- マイグレーションにはupとdownメソッドがある
  - `up` : データベースに新しいテーブル、カラム、またはインデックスを追加する
  - `down` : upメソッドによって実行する操作と逆の操作を実装し、以前の状態へ戻す
- マイグレーションを実行するには`php artisan migrate`コマンドを実行する
- マイグレーションを元に戻すには`php artisan migrate:rollback`コマンドを実行する
- マイグレーションを使う理由は2つ
  - SQLを知らなくても、PHPコードでテーブル操作ができるため学習コストが不要
  - 現在のデータベースの状態を他の開発者に共有することができる


### MVC

- Model: DBとのやりとりを司る
- View: ユーザ (Client) に表示する画面の生成を司る
- Controller: ユーザからの入力 (送信データ) に基づき、 Model・Viewの制御を司る
- Routing: ユーザからの依頼（リクエスト）に応じてどの処理を動かすかの判断を司る

### ルート定義

- URIとHttpメソッドの組み合わせで実行する処理を指定することをルート定義という
  - ルート定義は、routes/web.phpに記述する
  - `Route::get()`はHTTPメソッドのGETを示しており、getメソッドの第一引数がURIを示している
    そして、第二引数にそのURIとHTTPメソッドの組み合わせで実行したい処理を記述することでルートを定義可能

### ORM (Object Relational Mapper)

- ORMとはオブジェクトと関連するものをマッピングするもの
  - つまりプログラミング言語でいうクラスとデータベースのテーブルをマッピングする
    - そうすることでSQLを直接操作することなくデータベースとマッピングされたClassのメソッドを用いることでDBとやり取りを行える
       - Laravelでは、データベースのテーブルとマッピングするClassがModelになる


### Eloquent

- ORMの１つであり、エロクエントという
  - Modelを使って関係するデータベースとの対応付けをうまく行ってくれる機能

### blade 分割と継承

- `@extends('ファイル名')`で継承する親のbladeを指定（親bladeは継承先の子bladeファイルで共通しているhtmlを記述）
  - 引数は`resources/views/`以降のパスを.区切りで指定し、拡張子は省略可能
- 継承先の子bladeの`@section('content') ~ @endsection`で囲われた部分を、親Bladeの`@yield('content')`の部分に挿入する
  - 引数に同じ文字列'content'を指定することで、@section()と@yield()を紐づけています

### ymlファイルの設定

- environmentにDBの設定を書いておけばコンテナ立ち上げで自動で作成される？

### Schema

- `php artisan db:seed`でなぜ`DatabaseSeeder`クラスの`call`メソッドが実行されるのか

### middlewareの重要性

- ミドルウェアとはリクエストがルート設定で割り振られた後のコントローラーの処理の前または後で処理で実行する

- 例）ログイン済みユーザーのみトップページを表示する（未ログインユーザーはログインページにリダイレクト）という処理
  - ミドルウェアが設定されていない場合：
    1. ルーターが処理を割り振る
    2. コントローラーに処理が受け渡される
  - ミドルウェアが設定されている場合：
    1. コントローラーで処理が実行される前にミドルウェアが実行される

Laravelでは`app/Http/Kernel.php`にミドルウェア情報が設定されている


### 名前付きルート

画面遷移する際にURLをhref属性に直指定するとURLに変更があった場合に関連する全ての記述を修正する必要があり保守性や可読性が低い
それを解消するのが名前付きルート

1. ルート定義に`->name('ルート名')`を定義
2. `href="{{ route('todo.create') }}"`のように`route('ルート名')`とすることでルート名からそのルートで設定したURLを生成することができる

つまり、`route('todo.create')`を実行した時の返り値は`http://localhost:8080/todo/create`という文字列になるということ


### メソッドインジェクション

- メソッドの引数の左側にクラス名を書くことでインスタンス化が自動で行われる
  - `public function store(Request $request)`


### 一括代入の脆弱性と$fillable

> 参考記事：https://qiita.com/monji586/items/58d91891caa51b514166

### Illuminate


### Interfaceとトレイトどっちがいいのか


### サービスコンテナ
- bindメソッドは`interface`をインスタンス化するルールを決めておくイメージ
`interface`はインスタンス化できないがサービスプロバイダを使うことでインスタンス化ができる


### DI


### artisanコマンド


### 遅延プロバイダ


### implements


### Carbon


### Memcached


### Redis


### phpunit


### resourceメソッド（ルート定義）


### Groupメソッド（ルート定義）
類似したルート定義を複数記述するときに使うと便利
イメージとしては分割代入みたいに「AA.~~~」のAAを何度も書かなくて良くなる



> 参考記事：https://qiita.com/shizen-shin/items/f20c550db5a70c86111f


### matchメソッド（ルート定義）


### @component @endcomponent  @slot @endslot  @push @endpush


### Factory


### Form::open, Form::hidden, Form::submit, Form::close


### ルート定義のparameterメソッド