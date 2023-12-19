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

- 「.env-example」をコピーしてファイル名を「.env」に変更する

### 以下CMDやターミナルでコマンド実行

※「Docker Desktop」をインストールしておくこと
- docker-compose up -d
- docker-compose exec web rails db:create

※エラーが発生した場合は時間を置いて、もう一度実行する「docker-compose exec web rails db:create」
- docker-compose exec web rails db:migrate

「http://localhost:3000」にアクセスしてウェルカムページが表示されるか確認

## テストメール受信確認方法
### 以下コマンド実行
- docker-compose exec web rails c
- inquiry = Inquiry.new(name: "テスト太郎", message: "問い合わせメッセージ")
- InquiryMailer.send_mail(inquiry).deliver_now
- exit

「http://localhost:1080」にアクセスしてメールを受信しているか確認

