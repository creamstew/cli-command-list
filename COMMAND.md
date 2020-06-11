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