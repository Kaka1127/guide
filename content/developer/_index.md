+++
title = "開発者"
weight = 2
chapter = true
pre = "<b>2. </b>"
+++

### Chapter 2

## 開発者向けガイド

開発者がシステムを利用するために必要な項目を記載しています。  
以下のチャートを参考に読むべきページを確認ください。

{{<mermaid align="center">}}
graph TD;
    A(Start) --> B[Rancherの使い方]
    B --> C[Harborの使い方]
    C --> D{GPUの利用状況を確認}
    D --> |はい| E[Grafanaの使い方]
    D --> |いいえ| F{ワークステーションの利用}
    E --> F
    F --> |はい| G[ワークステーション向け初期設定]
    F --> |いいえ| K{開発した環境を保存するか}
    G --> Z
    K --> |はい| H[Portainerの使い方]
    K --> |いいえ| Z[終了]
    H --> Z
    E --> Z
{{< /mermaid >}}

{{% children %}}
