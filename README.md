# docker-httpd-tomcat

## メモ
httpdとtomcatをajp連携している環境下で8キロバイトを超えるGETリクエストを投げる。  
414 Request-URI too largeエラーの確認及び、解消を行う。

## dockerコマンドメモ
```
docker-compose build --no-cache
docker-compose up -d

docker-compose exec httpd bash

docker-compose exec tomcat sh
```
