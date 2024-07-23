---
audience: end-user
title: フェデレーション データベースとの接続を作成および管理します
description: フェデレーション データベースとの接続を作成および管理する方法を説明します
badge: label="限定提供" type="Informative"
source-git-commit: c1c035d3783af6c3bc94f2ba0aff7ba515fb68e2
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 5%

---

# 接続の作成 {#connections-fdb}

AEP で直接フェデレーテッドデータベースを操作することは、接続を確立することを意味します。

データベースとの接続を設定するには、「**[!UICONTROL FEDERATED DATA]**」セクションに移動し、「**[!UICONTROL Federated Databases]**」リンクで「**[!UICONTROL Federated Database を追加]**」ボタンをクリックします。

![](assets/connections_list.png){zoomable="yes"}

接続のウィンドウ **[!UICONTROL プロパティ]** にアクセスし、データベースの名前とタイプを指定します。

![](assets/connections_name.png){zoomable="yes"}

タイプを選択すると、入力する他のプロパティにアクセスできるようになります。 [ サポートされているデータベースについて詳しくは、こちらを参照してください ](federated-db.md)。

![](assets/connections_details.png){zoomable="yes"}

データベースのタイプに応じて、接続を設定するために必要な情報について、以下のリンクで説明します。

* [Amazon Redshift](federated-db.md#amazon-redshift)
* [Azure synapse](federated-db.md#azure-synapse-redshift)
* [Google BigQuery](federated-db.md#google-big-query)
* [Snowflake](federated-db.md#snowflake)
* [Vertica Analytics](federated-db.md#vertica-analytics)

詳細を入力したら、「**[!UICONTROL 接続をテスト]**」ボタンと「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックします。
「**[!UICONTROL 保存]**」ボタンをクリックして、接続の作成を完了します。

![](assets/connections_testdeploy.png){zoomable="yes"}

次のような、Federated データベース接続の概要が表示されます。

![](assets/connections_overview.png){zoomable="yes"}
