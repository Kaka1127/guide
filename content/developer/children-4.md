---
title: "Grafanaの使い方"
weight : 4
---

### Grafanaの用途

Grafanaは主に以下の用途で利用します。

- GPUの稼働状況確認

リンク

- Grafana: `http://10.xxx.xxx.xxx:30300`

---

#### ログイン画面

![login](/images/grafana_login.png)

---

#### トップ画面

![top](/images/grafana_top.png)

---

#### ログイン方法

ログイン画面からユーザー名・パスワードを入力します。

{{% notice note %}}
ユーザー名・パスワードはシステム管理者から提供されますので、不明な場合はシステム管理者に確認してください。
{{% /notice %}}

---

#### GPUの稼働状況確認

1. 左上にある”Home”より”General”にある”GPU”を選択
   ![top](/images/grafana_select.png)

2. GPUの情報が集約されたダッシュボードが表示
   ![top](/images/grafana_metrics.png)