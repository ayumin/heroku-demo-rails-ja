# Heroku Booth Demo

## デモセットアップ

### 1. デモアカウントの作成方法

Herokuのアカウントを持っていない場合、以下のURLから@salesforce.comのメールアドレスをつかってサインアップしてください。
[https://id.heroku.com/signup](https://id.heroku.com/signup)

### 2. Heroku Toolbeltのインストール

以下のURLからHerokuの開発ツールをインストールしてください。
[https://toolbelt.heroku.com/](https://toolbelt.heroku.com/)

### 3. アカウント情報の入力
以下のURLにアクセスし、アカウント設定画面でクレジットカード情報を入力してください。（課金はされませんがデモ実施をする上でクレジットカード情報がないと利用できない機能があるため）

[https://dashboard.heroku.com/account](https://dashboard.heroku.com/account)

画面をスクロールして「Billing」のリンクをクリックしてクレジットカード情報を設定。

## デモ概要

Heroku BoothではHerokuにアプリケーションをデプロイし、デプロイしたアプリケーションに対してクリック操作でできる拡張を中心に説明をおこないます。

Platform BoothではForce.comとHerokuアプリの接続について説明し、Herokuの中心的な説明はHeroku Boothに振ってください。

### デモの流れ

1.アプリがローカルで動くことを示す
2.アプリをHerokuにデプロイする
3.アプリにアドオンを追加する
4アプリのDynoを拡張する

### 1.アプリがローカルで動くことを示す

ターミナルで以下のコマンドを実行し、アプリのソースコードを取得します。
（事前に取得しておいてもよい）

    cd
    mkdir demo
    cd demo
    git clone https://github.com/xxxx/jp-heroku-demo-ruby
    cd jp-heroku-demo-ruby

以下のコマンドを実行し、アプリをローカルで実行します。

    foreman start

以下のURLにアクセスし、ローカルでのアプリが動いていることを示します。

[http://localhost:5000](http://localhost:5000)

### 2. アプリをHerokuにデプロイする

以下のURLにアクセスし、Herokuのダッシュボードをブラウザで開きます。

[https://dashbord.heroku.com](https://dashbord.heroku.com)

中央下部にある「Create new app」をクリックします。

作成するアプリの名前をアルファベットとハイフン、数字の組み合わせで入力します。
- 例. demo-app-201407

ダイアログ右下の「Create app」をクリックしてアプリを作成します。
次のダイアログが表示されたら、右下の「Finish up」をクリックします。

ターミナルで以下のコマンドを実行します。（ディレクトリが ~/demo/jp-heroku-demo-rubyであることを確認）
    git remote add heroku git@heroku.com:<作成したアプリの名前>.git
    git push heroku master

アプリケーションのソースコードがHerokuに移送され、実行環境の構築が自動的に行われます。以下のコマンドを実行し、Heroku側のデータベースを初期化します。
    heroku run rake:db migrate

以下のコマンドを実行し、Heroku上で実行しているアプリをブラウザで開きます。
    heroku open

### 3. アプリにアドオンを追加する

### 4. アプリのDynoを追加する









