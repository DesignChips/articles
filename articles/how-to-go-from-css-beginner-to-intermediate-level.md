---
title: "CSS初心者から中級者までの道のり"
emoji: "🐥"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["css"]
published: false
---

# はじめに
誰もが最初は初心者です。もちろん私自身もCSSを使い始めた頃は初心者でした。しかし、だんだんと仕事をこなしていくうちに、徐々にではありますが中級者と呼べるレベルまでは来られたのではないかと思っています。

私は中級者になるまでには数年という時間を要してしまいましたが、これからCSSを始めるという人たちはもっと短時間で中級者まで到達できると考えています。

私自身の経験を元に、中級者に至るまでに必要だったことについてまとめているので、参考になりそうであれば「知の高速道路」として利用していただければ幸いです。

# 初級者/中級者とは

まずは本稿での初級者/中級者がどのような状態を指すのかを整理しておきます。あくまで本稿における定義であり、世間一般に初級者/中級者として区別されているものではないことにご留意ください。

知識・技術・仕事という３つの観点を軸として整理していきます。知識は知っていることおよび調べればわかるということを知っている物事を指し、技術は実際に行えることやコーディングによって実現できることを指します。

仕事は具体的にどのような実務を行うことができるかを指し、この３軸によって初級者/中級者を、ある程度の確からしさをもって分類できると私は考えています。

## 初級者

### 知識
- HTMLの書き方を知っている
- CSSの書き方を知っている
- CSSのプロパティと実際の挙動について調べて理解できる

### 技術
- HTML/CSSを使ってデザインに沿ったコーディングができる
- ブラウザの開発者ツールを使ってCSSのデバッグができる

### 仕事
- コードの変更、ブラウザでの確認というプロセスでコーディングできる
- メンターのサポートのもと、デザイナー等とコミュニケーションをとって仕事を進められる

## 中級者

### 知識
- HTMLタグの適切な用途を調べて理解できる
- CSSの設計手法について調べて理解できる

### 技術
- 適切なHTMLタグを選択できる
- 既存のルールに従ってコーディングできる

### 仕事
- デザインをもとに、ある程度までは頭の中でHTML/CSSを組み立てることができる
- メンターのサポートなしに、デザイナー等とコミュニケーションをとって仕事を進められる

## 初級者/中級者の違い
知識・技術・仕事という軸で初級者/中級者を定義しました。両者の間にはどのような違いがあるかをみてみましょう。

初級者は１人だけでコーディングを進めるのは難しくメンター等のサポーターが必要ですが、中級者は１人でもコーディングを進めることができます。実際にはCSSを書くことは、仕事全体のごく一部の限られた領域にしかすぎないので、１人で仕事を進めることは少ないです。

しかし、１人で進められる力を持った上で協力して仕事をすること、１人で進めることが難しいので協力してもらって仕事をすることには違いがあります。

# 初級者から中級者になるために
初級者/中級者の間に存在するギャップを埋めるために必要な知識・技術・仕事について整理していきます。

これらの内容については私の経験則や主観によるところも多いので、この記事だけではなくメンターや他の意見も参考にして、自分自身が目指す中級者像とのギャップを埋めるように行動することを推奨します。

## 知識
まずは知っておくと良い知識についてまとめます。ここで紹介しているものは大きな変更が加えられることは少ないため、一度学習してしまえば数年単位の長期間で利用できるものになります。

### WHATWG's HTML standard
[HTML Standard](https://html.spec.whatwg.org/multipage/)

HTMLの標準仕様がWHATWGによって定められています。内容は適宜アップデートされていくため全てを暗記する必要はありませんが、存在を知っているとHTMLタグを適切に使用する助けになります。

この仕様には、HTMLタグがどのようなコンテンツを配置するためのものなのか、どのタグの子要素として配置できるかなどが定義されています。Visual Studio CodeやJetBrains製のIDEなどでは、入れ子構造などの利用方法が間違っているとWarningを表示してくれる場合があります。Warningが表示された場合はこの仕様を参照して修正しましょう。

### MDN
[CSS: カスケーディングスタイルシート | MDN](https://developer.mozilla.org/ja/docs/Web/CSS)

MDNにはCSSの概念や各プロパティの仕様などがまとまっています。詳細度・継承・カスケードやボックスモデルとマージンの相殺、フレックスボックス/グリッドレイアウトなど、CSSの基本的な概念から具体的な使い方まで詳細に解説されています。

CSSで困ったらまずはこのページをみて、それでもわからない場合はGoogle検索で解決方法を探す、という順で調べましょう。

### 詳細度
[詳細度 - CSS: カスケーディングスタイルシート | MDN](https://developer.mozilla.org/ja/docs/Web/CSS/Specificity)

詳細度は最終的のどのスタイルが反映されるのかを決める概念です。

理解していなくてもブラウザが勝手に計算してくれるので見た目が合うようにスタイルを書くことはできます。しかし、実際の仕事では複雑なスタイルを崩壊させずに維持していくため、詳細度を一定に保つことが必要になります。

[CSS Architecture — Philip Walton](https://philipwalton.com/articles/css-architecture/)では、優れたCSSアーキテクチャの目標は以下の４つを持ったCSSにすることだと言っています。これらを満たすためには詳細度のコントロールが重要になってきます。初心者のうちはかなり難しく感じますが、失敗できる環境で練習を積み重ねましょう。

1. **予測しやすい（Predictable）**
1. **再利用しやすい（Reusable）**
1. **保守しやすい（Maintainable）**
1. **拡張しやすい（Scalable）**

### BEM

[BEM — Block Element Modifier](http://getbem.com/)

BEMは、Block, Element, Modifierという３つの概念を取り入れた、再利用可能なコンポーネントを作るための方法論です。

2015年ごろに登場し、Webサイト制作やWebサービス開発の現場でも広く普及しています。BEMの使い方や実例を紹介しているサイトはかなりありますし、BEMのサイト自体もBEMで設計されているので、様々な情報を見て簡単に学習できます。

## 技術
次は、中級者として仕事をしていくために必要なことを挙げていきます。

### コーディングするプロセスを確立する

スタイルを書くためには、まずどのようなスタイルを書くかを考えてから手を動かすことが必要になります。場当たり的に考えて書くことはもちろん可能ですが、実装のスピードや効率を上げるためには、自分のプロセスを確立することが重要です。ここでは私が使っている方法を紹介しますが人によってやりやすい方法は異なるため、最初は誰かの真似をしつつも自分の方法を確立しましょう。

<!-- TODO: 見直す -->
デザインのファイルを元にHTML/CSSを書く時は、次のようなステップを踏んで進めています。ここでは、ある１ページを作るという想定です。

1. **デザインの意図を理解する**
それぞれの要素がどのような意味を持ったものなのかを知ることで、適切なクラス名をつけやすくなります。わからない箇所がある場合は、デザインファイルを作った人に確認してみましょう。

1. **要素の分解**
ページを一定のまとまりごとに分解します。BEMのBlockにあたる単位で分解できることが理想です。

1. **レイアウトの設計**
それぞれの要素ごとに適用する `display` を決めます。このまとまりは横並びが必要なので `display: flex`を使う、このまとまりは表形式になっているので `display: grid` を使う、などを決めます。

1. **余白の設計**
情報はある一定のまとまりごとにグルーピングされていて、グループごとに余白があるはずです。この余白は、この要素の `margin-top` にするなど、`margin` をどのように持たせるかを設計します。

1. **HTMLコーディング**
ここで初めてコードを書きます。まずはクラス名なしで全体のマークアップを行います。HTML Standardなどを参考に適切なHTMLタグを決めます。

1. **クラス名設計**
BEMにしたがってクラス名を決めます。スタイルを適用しないことが予想できる要素にはクラス名を付けなくても構いません。

1. **CSSコーディング**
最後にスタイルを書きます。スタイルを書くときにも、それぞれの小さな要素に対して「要素の分解」「レイアウトの設計」「余白の設計」というプロセスを適用すると、コーディングのスピードが上がります。

### 詳細度を一定に保つ

### BEMでクラス名を決める

## 仕事

### デザインを元にコーディングするプロセスのスピードをあげる

### 仕様が決まっていないことが多い要素

# さらに先へ
