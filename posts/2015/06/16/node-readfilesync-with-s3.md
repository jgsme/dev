# [io.js の fs.readFileSync を S3 と組み合わせると死ぬ](/2015/06/16/node-readfilesync-with-s3.html)

今日は、運用してる簡単なバッチスクリプトに「挙動がバギーなんだが〜」と問い合わせをもらって調べた。すると、どうやら `fs.readFileSync` でこちらが想定しているファイルを取得できていないことが分かった。

ブレークダウンしていくと、一定以上のサイズのファイルが途切れて取得されていることが分かった。当該ファイルは EC2 上のサーバに S3 をマウントしていて、`s3fs` 経由でファイルを参照していた。

試しにそのファイルを `cp` でローカルにコピーして read の権限を与えてやるとこちらが想定している通りのデータを取得することができた。まじかー。。。

たぶん `s3fs` の問題だろうから深入りせずに

```LiveScript
...
execSync "cp #{s3Path} #{tmpPath}"
execSync "chmod +r #{tmpPath}"
readFileSync tmpPath
...
```

というアレゲな対応になってしまった...。
