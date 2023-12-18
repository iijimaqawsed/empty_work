# README

* Ruby version: 3.2.2

## 構成
- ruby
- mysql
- phpmyadmin
- mailcatcher

## M1,M2チップ搭載型のMAC端末の場合
- 「docker-compose.yml」の7行目のコメントアウトを解除する

## コンテナの立ち上げ方
以下CMDやターミナルでコマンド実行

※「Docker Desktop」をインストールしておくこと
- docker-compose build
- docker-compose run --rm web rails db:create
- docker-compose up -d

## テストメール受信方法
以下コマンド実行
- rails c
- inquiry = Inquiry.new(name: "テスト太郎", message: "問い合わせメッセージ")
- InquiryMailer.send_mail(inquiry).deliver_now
- exit
「http://localhost:1080」にアクセスしてメールを受信しているか確認

