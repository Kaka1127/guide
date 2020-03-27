---
title: "Portainerの使い方"
weight : 3
---

### Portainerの用途

Portainerは主に以下の用途で利用します。

- Harborに保存するためのイメージ名変更
- Harborへのイメージ保存

リンク

- Portainer: `http://10.xxx.xxx.xxx:9000`

---

#### ログイン画面

![login](/images/portainer_login.png)

---

#### トップ画面

![top](/images/portainer_top.png)

| 番号 | 説明 |
| ------------- | ------------- |
| ① | メニュー画面です。 |
| ② | コンテナを管理している対象が一覧で表示されます。”local”は実行されている環境を意味します。 |
| ③ | ユーザー名が表示されます。パスワード変更、ログアウトすることができます。 |

---

#### ダッシュボード

管理する対象を選択すると稼働状況が確認できますが、使用するのは“Containers”と“Images”のみです。  

![dash](/images/portainer_dash.png)

---

#### ログイン方法

ログイン画面からユーザー名・パスワードを入力します。

{{% notice note %}}
ユーザー名・パスワードはシステム管理者から提供されますので、不明な場合はシステム管理者に確認してください。
{{% /notice %}}

---

#### 初期設定

Harborに保存するためにHarborへのアクセス権限を登録します

1. 左側のメニューから“Registries”を選択
2. “Add registry”を押す
   ![add](/images/portainer_add.png)
3. "Custom Registry"を選択の上、必要事項を記入
   - Name: ログインIDと同じ名前
   - Registry URL：HarborのIPアドレス
   - Userneme：HarborにログインするID
   - Password：ログインIDのパスワード
   ![cre](/images/portainer_cre.png)
4. 保存

---

#### 立ち上げたコンテナの保存

Rancherのカタログで立ち上げた環境で開発が完了したコンテナを保存します。

1. ダッシュボードトップまたは左メニューの“Containers”を選択
2. 表示された稼働中のコンテナ一覧から保存したいコンテナを選択
   ![name](/images/portainer_name.png)

3. “Create Image”の“Registry”で自分のIDを選択し、Imageに名前をつける
   ![create](/images/portainer_create.png)
   {{% notice note %}}
   保存先になるHarborのプロジェクトは先に作成しておく必要があります。
   アクセス権限のないHarborのプロジェクトには保存できません。
   {{% /notice %}}

4. ダッシュボードトップまたは左メニューの“Images”を選択
5. 作成したイメージを選択
   ![image](/images/portainer_image.png)
   {{% notice tip %}}
   ”Created”でソートするとイメージを見つけやすいです。
   {{% /notice %}}

6. Pushのボタンを押してイメージを保存
   ![push](/images/portainer_push.png)
