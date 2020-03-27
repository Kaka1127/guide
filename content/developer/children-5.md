---
title: "ワークステーション向け初期設定"
weight : 5
---

#### dockerへの初期設定

- TLS通信をしないアドレスを追加  
  1. “/etc/docker/daemon.json”を編集

  ```console
  {
      "insecure-registries": ["10.xxx.xxx.xxx"]
  }
  ```

  {{% notice note %}}
  ・ファイルが存在しない場合は作成ください。
  {{% /notice %}}
  2. dockerの再起動

  ```command
  $ sudo service docker restart
  ```

- Dockerログインコマンド  
  使用するワークステーションで以下のコマンドを実行

  ```command
  $ sudo docker login 10.xxx.xxx.xxx
  ```

---

#### Dockerイメージの名前付け

Harborにイメージを保存するに当たって以下の規則にしたがってイメージに名前をつけます。

 イメージの名前規則：`<IP>/<Harborのプロジェクト>/<管理する名前>:<タグ名>`
  
  例：10.xxx.xxx.xxx/kato/test:1.0

- イメージの名前をつける方法
  1. docker tagコマンドを使用して、イメージ名を変更
  
     ```command
     docker tag <コンテナ名/ID> <イメージ名>:<タグ名>
     ```
  
  2. 実行中のコンテナをdocker commitコマンドで保存
  
     ```command
     docker commit <コンテナ名/ID> <イメージ名>:<タグ名>
     ```

  3. Dockerfileのビルド時に名前をつけてイメージを生成

     ```command
     docker build -t <イメージ名>:<タグ名> .
     ```

{{% notice info %}}
・権限のないプロジェクトへの保存はできません。  
・Publicではないプロエジェクトにイメージを保存する場合は予めプロジェクトを作成しておく必要があります。  
・イメージ名の変更方法に関しては[ワークステーション向け初期設定](../children-5)を確認ください。
{{% /notice %}}
