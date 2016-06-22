# cookie - クッキーとはなにか

## cookie を説明する前にアフェリエイトを知っていますか？

    何かを説明する前にどのように使われているかを知っておくと理解はしやすいでしょう。

    ブログ記事のはしっこに貼られている、広告を見た事ある人は多いとおもいます。

    たとえば、ここにアクセスしてみてくださ。

    http://yonabeperl.blog.jp/

    これは私が主催しているプログラミング勉強会のブログですが、
    右側に広告が表示されています。

    しかも、この広告は表示している人によって違う広告になっているはずです。

    この広告をクリックしてみると、広告先のサイトへ移動するとおもます。

    それでは、マウスをこの広告の上で右クリック > 検証 をしてみましょう。
    単純なリンクが埋め込まれているわけではないです。

    ソースコードがあまりに長いので、細かい説明を省くと

    この広告画像にはアフェリエイトを管理しているサーバーへのリンクが貼ってあって
    クリックするといったん、管理しているサーバーへ遷移します。
    ここで管理しているサーバーへどこからアクセスしてきたかの記録がとられ、
    広告先のサイトへリダイレクトされるわけです。
    そして広告のページを表示している段階で情報がページに埋め込まれます
    cookie の機能が使われています。

    参考:
    http://www.fancs.com/pr/archives/2471

    文章だと分かりにくいですね。
    概念はこういう事です。

    ad_img = 広告画像
    affili_server = アフェリエイト管理サーバー
    ec_page = 広告先のページ(例えばショッピングサイトの購入画面)
    thanks_page = 購入完了のページ

    +------+  +---------------+  +-------+
    |ad_img|->|affili_server  |->|ec_page|
    +------+  | redirect ->   |  +-------+
              |               |      |
              |               |  +-----------+
              | conversion <- |<-|thanks_page|
              +---------------+  +-----------+

    cookie という機能を使って、なにかしらのデータをweb ブラウザに埋め込む事によって
    自分が張った広告リンクがクリックされて事によって、ネットショッピングが
    成立したことが証明できるわけです。
    cookie という手軽にデータを保存できる機能を使って、
    ネットショッピングサイトの世界は大きく発展していきました。

## アフェリエイトは儲かると思いますか？

    自宅にいながら、月に100万稼ぐ方法など、
    明らかに過大な謳い文句とおもわれるアフェリエイトのススメのようの記事を見る事があります。

    アフェリエイトセミナーに参加しませんか？など。

    確かに、莫大なアクセス数、クリック数、購買の成約をすれば稼げはしますが、
    どうやればそんなにクリックされる web サイトを作る事ができるんでしょうか？

    大抵こういう稼げますセミナーに参加する人は、どういう仕組みで
    アフェリエイトが構築されているか理解できてない人です。

    すでにあなたが莫大な数の読者がいるブログを連載していたり、
    web サイトを運営しているなら話は別ですが。

    私個人の感覚だと、莫大なアクセスを稼ぐ記事を書くより
    プログラミングのスキルを身につけて、アフェリエイトを運営する側の
    仕事をする方が、手堅くて、早いと思っています。

## なにをみれば cookie を確認できるのか

    このサイトにアクセスしてみましょう

    http://hackers.jpn.org/support/index.html

    画面を右クリック > 検証
    もしくは
    上部のメニュー > 表示 > 開発/管理 > デペロッパーツール

    Console を開きます

    下記の様に入力しましょう

    > window.navigator.cookieEnabled
    すると
    > true

    と返ってくれば cookie の機能が有効な証拠です。

    次に cookie が埋め込まれているかをみます

    > document.cookie
    > ""

    おそらく "" 空文字、なにもはいっていないと思います。

    こちらをみましょう
    Console 文字の列に Resources をクリックします
    Cookies > hackers.jpn.org を開くとたくさんいろんなものがあります。
    今の web ブラウザは高度に進化していますので、 Cookie の管理も少々複雑です。