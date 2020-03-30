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
    A(開発スタート) --> B{パソコンのOS}
    B --> |Windows| C[1.Rancherの使い方]
    B --> |Ubuntu| D[1.ワークステーション向け初期設定]
    C --> E[2.Harborの使い方]
    D --> F[2.Harborの使い方]
    F --> G[3.Rancherの使い方]
    E --> H[3.Portainerの使い方]
    H --> J[4.Grafanaの使い方]
    G --> L[4.Grafanaの使い方]
    J --> K[5.チュートリアル]
{{< /mermaid >}}

{{% children %}}
