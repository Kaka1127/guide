---
title: "Harobrの使い方"
weight : 2
---

### Harborの用途

Haborは主に以下の用途で利用します。

- Dockerイメージの管理
- Rancherで環境を立ち上げる時にイメージを取得する先として利用する
- チームまたは自分専用のレジストリが持てる

リンク

- Harbor: `http://10.xxx.xxx.xxx`

---

#### ログイン画面

![login](/images/harbor_login.png)

---

#### トップ画面

![top](/images/harbor_top.png)

| 番号 | 説明 |
| ------------- | ------------- |
| ① | 権限のあるプロジェクトの一覧を確認できます。”library”は社内共通イメージが存在します。 |
| ② | ユーザー名が表示されます。ここを押すとパスワード変更、ログアウトすることができます。 |
| ③ | Harbor上で行ったイベント（削除、プロジェクト追加など）が表示されます。 |
| ④ | ログインしたユーザの権限で確認できるレポジトリ情報が表示されます。 |
| ⑤ | ログインしたユーザの権限で確認できるイベントのログ情報が確認できます。 |
| ⑥ | 新しくプロジェクトを作成、削除するためのボタンです。 |

---

#### ログイン方法

ログイン画面からユーザー名・パスワードを入力します。

{{% notice note %}}
ユーザー名・パスワードはシステム管理者から提供されますので、不明な場合はシステム管理者に確認してください。
{{% /notice %}}

---

#### チーム/自分専用のレジストリ作成

- 専用レジストリの作成
  1. トップ画面の”New PROJECT”ボタンを押す
  2. ”ProjectName”をつける
     ![create](/images/harbor_create.png)
{{% notice warning %}}
Access Levelを“Public”にするとログインできるユーザ全てに公開されます。
{{% /notice %}}
  3. トップ画面で確認
     ![created](/images/harbor_created.png)

- チームで共有のプロジェクトでユーザ追加する場合
  1. プロジェクトにある“Members”から“＋USER”を押す
     ![project](/images/harbor_project.png)
  2. ”Name”から登録されているユーザを選択し、権限を付与
     ![member](/images/harbor_member.png)
     - Admin：メンバー管理、プロジェクトの設定などの権限を持つ
     - Master：イメージの削除など“Developer”以上の権限を持つ
     - Developer：プロジェクトの読み取り権限と書き込み権限
     - Guest：プロジェクトの読み取り専用の権限
{{% notice info %}}
権限に関する詳細は[こちら](https://github.com/goharbor/harbor/blob/v1.9.4/docs/permissions.md)を参照してください。
{{% /notice %}}
  3. 参加メンバーの確認
     ![member](/images/harbor_confirm.png)

{{% notice note %}}
以降は主にワークステーションを使った開発者向けに説明を行います。
{{% /notice %}}

---

#### イメージの取得/保存方法

イメージの保存、取得には予めDockerコマンドでログインしておきます。

```command
$ sudo docker login 10.xxx.xxx.xxx
```

{{% notice note %}}
・DockerコマンドでHarborにログインするにはdockerのDaemonに対して事前にセットアップする必要があります。  
・詳細は[ワークステーション向け初期設定](../children-5)を確認ください。
{{% /notice %}}

- 取得方法
　Docker Pullコマンドでイメージを取得

  ```command
  $ sudo docker pull 10.xxx.xxx.xxx/library/tensorflow:20.02-tf2-py3
  ```

  {{% notice info %}}
  権限のないプロジェクトからイメージを取得することはできません。
  {{% /notice %}}

- 保存方法
　Docker Pushコマンドでイメージを取得

  ```command
  $ sudo docker push 10.xxx.xxx.xxx/kato/test:1.0
  ```

  {{% notice info %}}
  ・権限のないプロジェクトへの保存はできません。  
  ・Publicではないプロエジェクトにイメージを保存する場合は予めプロジェクトを作成しておく必要があります。  
  ・イメージ名の変更方法に関しては[ワークステーション向け初期設定](../children-5)を確認ください。
  {{% /notice %}}
