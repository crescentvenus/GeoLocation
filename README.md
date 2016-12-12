# GeoLocation

スマートフォンの位置（緯度、経度）と日時情報をサーバー側へ設定するためのツール。
端末（スマートホンなど）のブラウザー(Chrome)でアクセスし、端末の位置（緯度、経度）と日時の情報をファイルとして作成できる。

# 準備 
## apache2インストール
 $ sudo apt-get install apache2
 次にApacheのSSLモジュールと，デフォルトのSSLのサイトを有効化し，Apacheを再起動します。

## SSLモジュールの有効化 (Geolocationを利用するにはHTTPSが必須)
 $ sudo a2enmod ssl
 $ sudo a2ensite default-ssl      //デフォルトのSSL証明書を利用
 $ sudo service apache2 restart
 これで，Apacheが443番ポートの待ち受けを開始する
