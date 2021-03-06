# [卒業を支える技術](/2014/02/15/graduate-technology.html)

無事卒論を提出できまして、ゆったりとした週末を送っております、いかがお過ごしでしょうか。

約一週間ほどで実験から卒論執筆までこなして、かなり死ぬ思いでやり抜けたのも、不断の弛まぬ努力の賜物...というよりは、各々のツールが助けてくれたのでせっかくなのでまとめておこうと思います。

# 全体

## Doit.im

ここ1年半ほど、Doit.imでタスク管理をしています。ちょっとしたことでも、未来の自分にやらせることはタスクにしてしまって積極的に未来の自分に任せていくスタイルです。ちなみに、タスクを見ながら過去の自分に舌打ちをしながらこなすスタイルとも言います。

[http://doit.im/](http://doit.im/)

# 執筆

## エディタ

### Sublime Text 2

Sublime Text 2で全編書き上げました。なんせルックスが綺麗(にカスタムできる)なのと、拡張性の高さがお気に入りポイントです。あと、キーボードショートカットが多くてかなり思いのままにプロジェクト内を移動できるので快適。

[http://www.sublimetext.com/](http://www.sublimetext.com/)

### Mou

メモをするときや、考えを整理するときはmarkdownぐらいがちょうどいいので、Mouで日付のファイルを作ってその日のメモなどをまとめていました。

[http://mouapp.com/](http://mouapp.com/)

## TeX

前に卒論を書いたときはPagesだったから内容を書くことに集中できたけれど、今回はTeXで書いたのでそれなりに苦労をしました。Sublimeからcmd+Bでビルド->Preview.appでpdfを開くところまで自動化できるので便利。リファレンスなんかを、同ファイルだとよしなに補完してくれるのだけれど、別ファイルだとうまく補完できなかったのでなんとかしたかったなー。

## git

卒論書きは、書いては直し書いては直し、の繰り返しなのでバージョン管理が肝心であるとおもいます。そのために、gitで論文のディレクトリをまるっと管理しておりました。本音をいうと、研究室にGitlabを建ててそこに各々がリポジトリを作って、セクション毎ぐらいの粒度でissueを立てて、そこにコミットを積んでいって、それをレビューして、ということがしたかったのだけれど導入コストがウォールマリアぐらい高いのでやめました。紙サイコー！紙イェーイ！

[http://git-scm.com/](http://git-scm.com/)

### Bitbucket

提出を目前にSSDが突然の死を迎えたりすると困るのでBitbucketでバックアップをとっておきました。

[http://bitbucket.org/](http://bitbucket.org/)

## Dropbox, Timemachine

これもSSDの死から即立ち直るためにDropboxとOSXのTimemachineの二重バックアップ体制で、毎日寝る前に必ずバックアップをとりながら生活していました。

[http://www.dropbox.com/](http://www.dropbox.com/)

## Keynote

半年ほど前まではInkscapeでモリモリと図を作っていたものの、めんどくさくてKeynoteで図を作るようになりました...。最低限の図はKeyで事足りる...。

# 実験

## node.js

冬休みあたりには、最近流行ってるし、速いらしいしGoで実装してみよっかな〜みたいなことを妄想していたのですが、タイトなスケジュールでそんなこと言ってる余裕もなく、慣れ親しんでるnodeで書くことにしました。数値計算がメインなので、nodeのココがイイから採用しました！っていうのは全くなくて、単に慣れてるってだけでチョイスしたので許してください。

[http://nodejs.org/](http://nodejs.org/)

## Coffee-Script

生のjsは勘弁御免之介なので、これも慣れてるCoffeeで書くことにしました。

[http://coffeescript.org/](http://coffeescript.org/)

## Underscore.js

[@tatyusa419](https://twitter.com/tatyusa419)に「関数型Javascript」本を借りて、UnderscoreSUGEEEEってなったのでモリモリ活用しました。

[http://underscorejs.org/](http://underscorejs.org/)

## mocha+chai

事前に、自前でつくるモジュールに必要になりそうなテストをmochaとchaiで書いておいたので、まずはそのテストを通すところからはじめて、開発を進めていきました。実験のメインコードは概ね50行程度で書ききれる簡素なつくりだったのでノーテストでフィニッシュしました。

[http://visionmedia.github.io/mocha/](http://visionmedia.github.io/mocha/)

## cake

実験は並列化できるものだったので、10プロセスぐらい並列して実行させていました。実験の度に跳ね上がるCPU使用率、唸るファン！この実験のレギュレーションなんかをいちいちコマンドラインで手打ちするのが面倒だったので、Coffee-Scriptのビルドファイルであるcakeに実験の種類毎ぐらいにタスクを作っておいて、`% cake hoge`で実験が走るようにしました。

# 結果の加工

## harp

実験をCUIで終えたら、その結果をGUIで確認するためにブラウザでグラフをレンダリングして確認したりできるようにしました。harpは、jadeやcoffeeを書いておけばコンフィグファイルも作らずにいい具合にサーブしてくれるので便利だとおもいます。

[http://harpjs.com/](http://harpjs.com/)

## d3.js

結果を全てcsvに出力したら、d3.jsでcsvを読み込んでグラフの出力をします。半年ほど前に、Rでグラフを描画することを試みたものの、あまり便利さを享受する前に心が折れてしまったのでd3.jsで。結果はsvgでレンダリングされるので、適当にcssファイルを書いておいてやればアピアランスも自在なので便利だとおもいます。

[http://d3js.org/](http://d3js.org/)

## async.js

Underscoreに慣れてくると、asyncは非同期に対応したUnderscoreみたいに見えてきて魂のステージが上がったような気持ちになりました。複数ファイル扱ったりするのに使いました。

[http://github.com/caolan/async](http://github.com/caolan/async)

## phantomjs

終わってみれば、出力がsvgなのでsvgをファイルに出力してepsに変換すればよかったのですが、当時はそれを思いつかずにphantomjsでスクリーンショットを撮って、それをepsに変換しておりました...。おかげでepsのファイル容量が肥大化してえらい目に遭いました。

[http://phantomjs.org/](http://phantomjs.org/)

## Imagemagick

みんな大好きImagemagick、pngからepsの変換もこれがあれば楽ちん。

[http://www.imagemagick.org/](http://www.imagemagick.org/)

# その他

ダラダラとやり続けると生産性が下がるので、メリハリをつけてヤるときはヤる、ヌくときはヌく、を心がけて乗り切りました。3食きっちりとり、DDRで身体を動かして、夜はバッチリ寝て朝は早めに起きて創造性が必要なことは午前中のうちに全てこなし、午後からはあまり考えずに済むことをやる。このリズムをしっかり身体に刻んでいくのが肝要かなあと。

それから、人間がやるべきでない作業は早いうちに自動化しておくのが鉄則だとおもいます。
