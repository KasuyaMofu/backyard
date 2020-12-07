## 元資料

[JPCERT/CC 1週間振り返り (2020/11/28-2020/12/05)](https://zenn.dev/kasuyamofu/scraps/615fb2cfbdfc5f)

## 2020/12/06(日)

https://www.jpcert.or.jp/wr/2020/wr204701.html

(画像1: 2020-12-02号の一覧)

おはかすやでございます。糟屋もふです。
12月5日土曜日 AM50時、今日のおはようVTuberです。

### 今日は何の日？

毎週土曜日はJPCERT Weekly Reportの紹介です。
2020-12-02号の内容から、注目ポイントを抜粋してお伝えいたします。

今週、JPCERTにて重要と判断されたセキュリティ情報を含む製品は、以下の通りです。

- 複数の VMware 製品 ※仮想化ソフトウェア
  - (VMware Workspace One Access, VMware Identity Manager)
  - (8443/TCPポートへのアクセスで任意のOSコマンドを実行される恐れ)
- Drupal(ドルーパル) ※CMS
  - (.tar, .tar.gz, .bz2, or .tlzをアップロードする際の不備で任意のPHPコードを実行される恐れ)
- NETGEAR 製スイッチングハブ
  - (GS108Ev3へログインした状態で細工されたページにアクセスすると、設定を意図せず変更される恐れ)
- トレンドマイクロ ウイルスバスター for Mac ※セキュリティ
  - (当該製品にアクセス可能な第三者が、情報を窃取するなどの可能性)
- トレンドマイクロ InterScan Messaging Security ※メールゲートウェイ
  - (遠隔の第三者が、設定を変更したり、情報を窃取したりするなどの可能性)
- GROWI ※Wiki
  - (ユーザが非公開にしている情報を窃取される, XSS)

(画像2 トップ画像)
https://www.trendmicro.com/ja_jp/business/products/user-protection/sps/email-and-collaboration/interscan-messaging.html

この中で、私が注目すべきと感じたのは、
トレンドマイクロ InterScan Messaging Security です。

(画像3 概略図)
https://www.trendmicro.com/ja_jp/business/products/user-protection/sps/email-and-collaboration/interscan-messaging.html

この製品は、ざっくりいうと、メールのフィルタリングの製品で、
会社で受信する迷惑メールや標的型メール、
いわゆる「この人をだましてやるぞ！」といった内容のメールですね、
これらを弾くような製品です。

(画像4 会社の中のマシン)
https://www.irasutoya.com/2018/06/blog-post_198.html
https://www.irasutoya.com/2016/03/blog-post_89.html
https://www.irasutoya.com/2013/03/blog-post_26.html

この製品は、オンプレミスゲートウェイ製品というもので、
オンプレミス、というのは、ある会社で購入して、その会社の中の物理的なマシンにインストールするものです。 

よりエンジニアさん向けに伝えると、具体的には、ベアメタルサーバ、
またはESXiやHyper-V上へインストールするような、製品となります。

(画像5 新規受注無し)

そんな、 InterScan Messaging Security、実は、すでに新規受注が終了しており、
5年後にサポートが終了することが告知されております。

トレンドマイクロ社は、結構有名なセキュリティ大手ということで、
そのような会社がオンプレミスでのセキュリティ商品を廃止する、
という判断が非常に目を惹く部分です。

ではオンプレミス製品を廃止してどうするか。

(画像6 )
https://www.trendmicro.com/ja_jp/business/products/user-protection/sps/email-and-collaboration/cloud-email-gateway-services.html

こちらは、同トレンドマイクロ社のクラウド製品「Trend Micro Email Security」です。
パッ見ていただくとわかるように、非常にシンプルな構成ですね。
メールを全てトレンドマイクロ社に一旦配送し、その後、検査済みメールを会社に届けてくれる、というものです。

この製品のように、今まで会社に置いていたサーバを
トレンドマイクロ社のクラウドに移せば、
今回のような脆弱性が出たときのアップデート等にへの人手を割くこともなくなるわけですね。

大分元の話から離れてきましたが、
こういったクラウド化の動きは、セキュリティに限らず、色んな所で起こっています。

例えば、皆さんが何気なく使っているGmail、これも正にクラウドですね。
これは、メールの検査から保管までGoogle社で行っていることになります。

そんな感じで、これから数年、世の中の内外が変わっていく予兆が、
脆弱性のレポートを通じて見られた、という、個人的には、面白い話でした。

話したい事は済んだので今日はこれまで！
インフラエンジニアって、普段こういうことを考えたり、
そういう仕事についているんです、というご紹介でした！
お相手は、インフラエンジニアVTuberの糟屋もふでした。

それでは、明日に向けておやすみなさいっ
