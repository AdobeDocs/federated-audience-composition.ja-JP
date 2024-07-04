---
audience: end-user
title: コンポジションの作成
description: コンポジションの作成方法を説明します
source-git-commit: 0d6930b15be5013b57b8859dd3d21a5d3367ecae
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 41%

---


# コンポジション作成の主な原則 {#gs-composition-creation}

>[!CONTEXTUALHELP]
>id="dc_composition_creation_properties"
>title="構成のプロパティ"
>abstract="この画面で、コンポジションの作成に使用するテンプレートを選択し、ラベルを指定します。 「その他のOPTIONS」セクションを展開して、コンポジションの内部名、そのフォルダー、タイムゾーン、スーパーバイザーグループなどの追加の設定を指定します。 エラーが発生した場合にオペレーターに警告できるように、スーパーバイザーグループを選択することを強くお勧めします。"

## コンポジションには何が含まれていますか？ {#gs-composition-inside}

Federated Data Composition は、様々なアクティビティ（分割、エンリッチメントなど）を活用してオーディエンスを作成できる視覚的なキャンバスを提供します。

構成図は、実行される処理を表したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![](assets/composition-example.png){zoomable="yes"} {zoomable="yes"}

各コンポジションには次が含まれます。

* **アクティビティ**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。
* **トランジション**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。
* **作業用テーブル**：作業用テーブルには、トランジションによって実行されるすべての情報が含まれます。各コンポジションは、複数のワークテーブルを使用します。 これらのテーブルで伝達されたデータは、コンポジションのライフサイクルを通じて使用できます。

## コンポジションを作成するための主な手順 {#gs-composition-steps}

コンポジションを作成する主な手順は次のとおりです。

1. [コンポジションの作成と設定](../compositions/create-composition.md)
1. [アクティビティをオーケストレーション](../compositions/orchestrate-activities.md)
1. [コンポジションを実行し、その実行を監視します](../compositions/start-monitor-composition.md)
