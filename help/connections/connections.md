---
audience: end-user
title: 連合データベースとの接続の作成および管理
description: 連合データベースとの接続の作成および管理方法について説明します
badge: label="限定提供" type="Informative"
exl-id: ab65cd8a-dfa0-4f09-8e9b-5730564050a1
source-git-commit: de5955ad481061c6f8e488c86fc9666736a2fa1e
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 85%

---

# 接続の作成 {#connections-fdb}

Experience Platformの Federated Audience Composition を使用すると、お客様は、サードパーティのデータウェアハウスからオーディエンスを作成および強化し、オーディエンスをAdobe Experience Platformにインポートできます。 サポートされるデータウェアハウスのリストについては、[ この節 ](../start/access-prerequisites.md#supported-systems) を参照してください。

連合データベースと Adobe Experience Platform を操作するには、まず接続を確立する必要があります。この接続は、Adobe Experience Platform ユーザーインターフェイスで使用できる専用のユーザーインターフェイスで設定されます。詳しくは、このページを参照してください。

データベースとの接続を設定するには、次の手順に従います。

1. 左側のパネルの「**[!UICONTROL 連合データ]**」セクションを参照します。

1. **[!UICONTROL 連合データベース]**&#x200B;リンクで、「**[!UICONTROL 連合データベースを追加]**」ボタンをクリックします。

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
   * [Databricks](federated-db.md#databricks)

1. 詳細を入力したら、「**[!UICONTROL 接続をテスト]**」ボタンと「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックします。

   ![](assets/connections_testdeploy.png){zoomable="yes"}

1. 「**[!UICONTROL 終了]**」ボタンをクリックして、接続の作成を完了します。

   次に示すように、連合データベース接続の概要が表示されます。

   ![](assets/connections_overview.png){zoomable="yes"}
