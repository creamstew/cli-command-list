ec2からローカル
```bash
$ rsync -ar -e 'ssh -i ~/.ssh/.pem' --exclude '/path'  user-name@ec2-ip-address:/ec2-path /local-path
```
-a: 「-rlptgoD」と指定したのと同様の効果。(--recursive --links --perms --times --group --owner --devices)
とりあえず基本つけておく
-r:再帰的にコピー
--exclude: 	除外対象を指定
-e ssh: ssh経由での同期

ローカルからec2
```bash
rsync -ar -e 'ssh -i ssh -i ~/.ssh/.pem' /local-path user-name@ec2-ip-address:/ec2-path
```

ファイルの中身にある文字列を探す
```bash
grep -rn '{検索したい文字列}' {ディレクトリパス}
```
-rn: ディレクトリを再帰的にたどり、見つかった行は行番号を付して表示するオプション

すべてのユーザーにスクリプトの実行権限を付与
```bash
chmod +x myscript
```

所有者のみに秘密鍵の読み書き権限を付与
```bash
chmod 600 secret.key
```

テキストファイルを編集
```bash
sed --in-place --regexp-extended --expression
```
--in-place(-i): ファイルを直接編集する
--regexp-extended(-r): スクリプトで拡張正規表現を使用する
--expression(-e): スクリプト（コマンド）を追加する（標準入力に対して処理する場合に使用）