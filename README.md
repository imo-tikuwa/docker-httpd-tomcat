# docker-httpd-tomcat

## メモ
httpdとtomcatをajp連携している環境下で8キロバイトを超えるGETリクエストを投げる。  
414 Request-URI too largeエラーの確認及び、解消を行う。

## 使い方
dockerコンテナを作成
```
docker-compose build
docker-compose up -d
```

---
起動中の各コンテナ内に入るコマンド
```
# httpdコンテナ
docker-compose exec httpd bash

# tomcatコンテナ
docker-compose exec tomcat sh
```

コンテナ起動中にブラウザでローカルホストの80番にアクセスしApache Tomcatのトップ画面が見れてれば正常に起動できています。

## dockerコマンドメモ
コンテナとイメージとネットワークを消す
```
docker-compose down --rmi all --volumes
```

## 参考サイト
- [apacheとtomcatをdockerコンテナで作って,ajp連携できるようにした話。 &#8211; ukijumotahaneniarukenia](https://ukijumotahaneniarukenia.site/2019/05/01/apache%E3%81%A8tomcat%E3%82%92docker%E3%82%B3%E3%83%B3%E3%83%86%E3%83%8A%E3%81%A7%E4%BD%9C%E3%81%A3%E3%81%A6ajp%E9%80%A3%E6%90%BA%E3%81%A7%E3%81%8D%E3%82%8B%E3%82%88%E3%81%86%E3%81%AB%E3%81%97/)
- [Apacheにsecretを設定して、安全にTomcatとAJP通信する - Qiita](https://qiita.com/polarbear08/items/f016a0675e6c9637e7b8)
- [《滅びの呪文》Docker Composeで作ったコンテナ、イメージ、ボリューム、ネットワークを一括完全消去する便利コマンド - Qiita](https://qiita.com/suin/items/19d65e191b96a0079417)
