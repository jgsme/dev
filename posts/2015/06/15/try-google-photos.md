# [Google Photosを試す](/2015/06/15/try-google-photos.html)

先日発表された Google Photos を使ってみようと思い立ったが、手持ちの写真をアップロードするのはもうちょっと様子見てからにすることにした。そこで、先月の自分の tumblr からごっそりと写真を抜いてくるスクリプトをささっと書いた。

https://github.com/e-jigsaw/lpt

月が変わるまで Tumblr の API を叩き続けてひたすら画像の URL をかき集めて、それをまとめてダウンロードする簡単なスクリプト。Google Photos 側が複数枚の画像をまとめてアップロードしてくれるのは確認していたので(当初は Google Photos の API を叩くとかなんとかしようと考えていたが)ローカルに一旦ダウンロードして、それをブラウザで一括選択でアップロードすることにした。

Google Photos のアップローダはとても賢くて、アップロード中にインターネットが寸断してしまって、アップロードやり直しかと一瞬青ざめたがインターネットが切れても切れたところからレジュームするような仕組みにもなっていてさすがだなあ、と感心した。

ひと通りアップロードしたあとに「アシスタント」というタブを開くと、Google 様が似た写真を賢くまとめてくれたコラージュ画像が見れてビビった。さらにスゴいのが、連写したような写真群に対してはアニメーションというかたちで勝手に GIF を生成してくれる機能。

白眉はやはり検索で、「車」と検索すると以下のような結果が返ってくる。もはや怖い。

![](https://cloud.githubusercontent.com/assets/557961/8156475/f4fc7986-1387-11e5-9868-bdd4ba469da0.png)

とはいえ、まだ他のワードの精度なんかはイマイチなのでそこら辺がもっと学習されたらいいなーとおもった。