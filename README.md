# memodoc開発環境用docker

## 前提
- Docker（Desktop）がインストールされていること
- docker-composeがインストールされていること
- gitがインストールされていること

## 環境構築
1. 任意のディレクトリに本リポジトリをクローンする
2. クローンしたディレクトリ（memodoc-dev-environment）に移動する
3. .env.exampleをコピーして.envにリネームする
4. .env内のMYSQL関連の値を設定する
5. 下記コマンドでmemodocのリポジトリをworkspaceディレクトリにクローンする
    ```
    git clone https://github.com/joyrswd/memodoc.git ./workspace
    ```
6. 下記コマンドでdockerを立ち上げる
    ```
    docker-compose up -d
    ```
7. https://github.com/joyrswd/memodoc のインストール手順3以降を実施する  

以上

## コンテナ構成
- **app** -- アプリ（PHP）を実行するコンテナ
- **web** -- ウェブサーバー（apache）を実行するコンテナ  
    ※ ブラウザで http://localhost/ へアクセスして利用
- **mail** -- 開発環境用メールサーバー(mailpit)を実行するコンテナ  
    ※ ブラウザで http://localhost:8025/ へアクセスして利用
- **db** -- データベース（MariaDB）を実行するコンテナ
- **redis** -- Redisを実行するコンテナ（任意利用）


## ライセンス

このプロジェクトは[MITライセンス](LICENSE)の下でライセンスされています。

