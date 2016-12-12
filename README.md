# GeoLocation
スマートフォンの位置（緯度、経度）と日時情報をサーバー側へ設定するためのツール。<BR>
端末（スマートホンなど）のブラウザー(Chrome)でアクセスし、端末の位置（緯度、経度）と日時の情報をファイルとして作成できる。<BR>

# 準備 
## apache2インストール
 $ sudo apt-get install apache2<BR>
 次にApacheのSSLモジュールと，デフォルトのSSLのサイトを有効化し，Apacheを再起動します。<BR>

## SSLモジュールの有効化 (Geolocationを利用するにはHTTPSが必須)
 $ sudo a2enmod ssl<BR>
 $ sudo a2ensite default-ssl      //デフォルトのSSL証明書を利用<BR>
 $ sudo service apache2 restart<BR>
 これで，Apacheが443番ポートの待ち受けを開始する<BR>
