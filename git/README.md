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