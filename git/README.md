# 設定

## SSH

### キーの設定
`ssh-keygen -t rsa -b 4096 -C "任意の文字列"`
`-t`：typeのtで種類を表す
`-b`：byte
`-C`：CommentのC

キーはsshファイルに生成される
`cd ~/.ssh`
移動後に`ls`をすると`id_rsa`（秘密鍵）と`id_rsa.pub`（公開鍵）がある
`cat`コマンドで中身が確認できる

### originの意味 確認方法
`cat .git/config`でgitのコンフィグを見ると下記のような記述があり、リモートリポジトリのurlを示している
`[remote "origin"]
  url = https://github.com/technicalplace/c2c-commerce-app.git
`


# ブランチ操作

## ブランチ名変更
`git branch -m 新しいブランチ名`
変更したいブランチに移動してから実行する
`-m`はmodify（変更）の`m`

## 色々書いたけどやっぱり元に戻したい
`git checkout ファイル名`でファイルを元に戻す
> https://arc.net/l/quote/ercogrsf

# クローン

## .の意味

`git clone リポジトリ名 .`
上記の「.」の意味はクローンしてきたときにリポジトリ名のフォルダを作らないようにする
つまり`project`という名前のフォルダを作成してそこに`project`のリポジトリ名をクローンしてくると`project`フォルダが2つできてしまう。
だが、.をつけてクローンするとコードだけクローンしてこれる

> 参考：https://orfool.com/programing/git-clone-without-dir/



### git pull と git fetch merge の違い
- `git fetch`はリモートからローカルに情報を引っ張ってくるがローカルのブランチまではいかない
- `git fetch`したあとに`git merge`しないとローカルブランチには反映されない

- 上記2つの手順を1回でやるのが`git pull`

> 参考記事：https://qiita.com/wann/items/688bc17460a457104d7d
