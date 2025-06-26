---
audience: end-user
title: 連合データベースとの接続の作成および管理
description: 連合データベースとの接続の作成および管理方法について説明します
exl-id: ab65cd8a-dfa0-4f09-8e9b-5730564050a1
source-git-commit: b39fc9ed99a799d6ef6d5821554ebd2a409a652f
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 95%

---

# 接続の作成 {#connections-fdb}

>[!AVAILABILITY]
>
>接続にアクセスするには、次のいずれかの権限が必要です。
>
>-**連合データベースの管理**
>>-**連合データベースの表示**
>
>必要な権限の詳細については、[ アクセス制御ガイド ](/help/governance-privacy-security/access-control.md) を参照してください。

Experience Platform 連合オーディエンス構成を使用すると、お客様はサードパーティのデータウェアハウスからオーディエンスを作成して強化し、このオーディエンスを Adobe Experience Platform に読み込むことができます。サポートされているデータウェアハウスについて詳しくは、[この節](../start/access-prerequisites.md#supported-systems)を参照してください。

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
   * [Databricks](federated-db.md#databricks)
   * [Google BigQuery](federated-db.md#google-bigquery)
   * [Snowflake](federated-db.md#snowflake)
   * [Vertica Analytics](federated-db.md#vertica-analytics)
   * [Microsoft Fabric](federated-db.md#microsoft-fabric)

1. サポートされている各データベースに対して、「**[!UICONTROL サーバー IP]**」ボタンを選択します。連合オーディエンス構成インスタンスに関連付けられているすべての IP のリストが表示されます。

   ![](assets/connections_server_IPs.png){zoomable="yes"}

   リストから IP をクリックしてシステムにコピーし、この IP を承認してデータベースに接続します。

   >[!NOTE]
   >
   >指定されたデータベースに対して連合オーディエンス構成を使用するには、そのデータベースに関連付けられているすべての IP アドレスを許可する必要があります。

1. 詳細を入力したら、「**[!UICONTROL 接続をテスト]**」ボタンと「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックします。

   ![](assets/connections_testdeploy.png){zoomable="yes"}

1. 「**[!UICONTROL 終了]**」ボタンをクリックして、接続の作成を完了します。

   次に示すように、連合データベース接続の概要が表示されます。

   ![](assets/connections_overview.png){zoomable="yes"}
