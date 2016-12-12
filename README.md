# GeoLocation & Date
スマートフォンの位置（緯度、経度）と日時情報をサーバー側へ設定するためのツール。<BR>
端末（スマートホンなど）のブラウザー(Chrome)でアクセスし、端末の位置（緯度、経度）と日時の情報をサーバ側のファイルとして作成できる。<BR>

# 準備 
## apache2とphp5のインストール
 $ sudo apt-get install apache2 php5<BR>
 次にApacheのSSLモジュールと，デフォルトのSSLのサイトを有効化し，Apacheを再起動します。<BR>

## SSLモジュールの有効化 (Geolocationを利用するにはHTTPSが必須)
 $ sudo a2enmod ssl<BR>
 $ sudo a2ensite default-ssl      //デフォルトのSSL証明書を利用<BR>
 $ sudo service apache2 restart<BR>
 これで，Apacheが443番ポートの待ち受けを開始する<BR>

## info.phpの配置とアクセス
 /var/www/html/の下などへ配置し、端末のbrawser(検証はchromeのみ）でinfo.phpをアクセスします。<br>
 デフォルトの証明書を利用しているので、セキュリティの警告が表示されます<Br>
 端末の位置情報をアクセスするので、許可を求めるメッセージが表示されます<BR>　

## info.phpでは、次のファイルへ情報を書き込んでいるので、必要に応じてinfo.phpを修正してください。
 /tmp/LatLng　緯度、経度<BR>
 /tmp/date    YYYY/MM/DD HH:mm:SS<BR>
 
## 日時の設定例 ( dateコマンド)　
 サーバ側がインターネットをアクセスできればntpコマンドの利用がお手軽ですが、info.phpの情報から日時の設定も可能<br>
 $ sudo date -s "\`cat /tmp/date\`"<BR>
 
