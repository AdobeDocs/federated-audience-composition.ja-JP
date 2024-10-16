---
audience: end-user
title: フェデレーション データベースとの接続を作成および管理します
description: フェデレーション データベースとの接続を作成および管理する方法を説明します
badge: label="限定提供" type="Informative"
exl-id: ab65cd8a-dfa0-4f09-8e9b-5730564050a1
source-git-commit: c2d4ec21f497a1c4ad9c1701b4283edd16ca0611
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 81%

---

# 接続の作成 {#connections-fdb}

Experience Platform 連合オーディエンス構成を使用すると、お客様はサードパーティのデータウェアハウスからオーディエンスを作成して強化し、このオーディエンスを Adobe Experience Platform に読み込むことができます。

連合データベースと Adobe Experience Platform を操作するには、まず接続を確立する必要があります。この接続は、Adobe Experience Platform ユーザーインターフェイスで使用できる専用のユーザーインターフェイスで設定されます。詳しくは、このページを参照してください。

データベースとの接続を設定するには、次の手順に従います。

1. 左側のパネルの「**[!UICONTROL 連合データ]**」セクションを参照します。

1. **[!UICONTROL 連合データベース]** リンクで、「**[!UICONTROL 連合データベースを追加]**」ボタンをクリックします。

   ![](assets/connections_list.png){zoomable="yes"}

1. データベースの名前とタイプを使用して、接続の&#x200B;**[!UICONTROL プロパティ]**&#x200B;を設定します。

   ![](assets/connections_name.png){zoomable="yes"}

   タイプを選択すると、入力する他のプロパティにアクセスできます。サポートされているデータベースについて詳しくは、[このページ](federated-db.md)を参照してください。

   ![](assets/connections_details.png){zoomable="yes"}

   設定の指定は、データベースのタイプによって異なります。接続を設定するために必要な詳細にアクセスするには、以下のリンクを参照してください。

   * [Amazon Redshift](federated-db.md#amazon-redshift)
   * [Azure Synapse](federated-db.md#azure-synapse-redshift)
   * [Google BigQuery](federated-db.md#google-big-query)
   * [Snowflake](federated-db.md#snowflake)
   * [Vertica Analytics](federated-db.md#vertica-analytics)

1. 詳細を入力したら、「**[!UICONTROL 接続をテスト]**」ボタンと「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックします。

1. 「**[!UICONTROL 終了]**」ボタンをクリックして、接続の作成を完了します。

   ![](assets/connections_testdeploy.png){zoomable="yes"}

   次に示すように、フェデレーテッド データベース接続の概要が表示されます。

   ![](assets/connections_overview.png){zoomable="yes"}
