---
audience: end-user
title: コンポジションの作成
description: コンポジションの作成方法を説明します
badge: label="限定提供" type="Informative"
exl-id: 861440ab-ce14-46aa-a215-b86fc9ffeef0
source-git-commit: f549f1611bfe6deb6dc684e3a0d9c968ba7c184a
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 59%

---

# 構成作成の主な原則 {#gs-composition-creation}

>[!CONTEXTUALHELP]
>id="dc_composition_creation_properties"
>title="構成プロパティ"
>abstract="この画面では、構成の作成に使用するテンプレートを選択し、ラベルを指定します。「その他のオプション」セクションを展開して、構成の内部名、フォルダー、タイムゾーン、スーパーバイザーグループなどの詳細設定を行います。エラーが発生した場合にオペレーターに警告できるように、スーパーバイザーグループを選択することを強くお勧めします。"

## コンポジションの内容 {#gs-composition-inside}

Experience PlatformFederated Audience Composition は、様々なアクティビティ（分割、エンリッチメントなど）を活用してオーディエンスを作成できる視覚的なキャンバスを提供します。

構成図は、実行される処理を表したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![](assets/composition-example.png){zoomable="yes"} {zoomable="yes"}

各コンポジションには次が含まれます。

* **[!UICONTROL アクティビティ]**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。
* **[!UICONTROL トランジション]**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。
* **[!UICONTROL 作業用テーブル]**：作業用テーブルには、トランジションによって実行されるすべての情報が含まれます。各コンポジションは、複数のワークテーブルを使用します。 これらのテーブルで伝達されたデータは、コンポジションのライフサイクルを通じて使用できます。

## コンポジションを作成するための主な手順 {#gs-composition-steps}

コンポジションを作成する主な手順は次のとおりです。

1. [コンポジションの作成と設定](../compositions/create-composition.md)
1. [アクティビティをオーケストレーション](../compositions/orchestrate-activities.md)
1. [コンポジションを実行し、その実行を監視します](../compositions/start-monitor-composition.md)
