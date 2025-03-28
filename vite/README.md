### server host

defineConfigにて下記のように記述すると開発環境（ローカル）でもスマホなどの実機で確認できる
```
server: {
    host: true,
  },
 ```

実行すると下記のようになる

```
Local:   http://localhost:ポート番号/
Network: http://192.168.XXX.XXX:ポート番号/
```

NetworkのURLをスマホで見れば実機で確認できる

