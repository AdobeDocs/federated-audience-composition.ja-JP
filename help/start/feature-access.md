---
title: 連合オーディエンス構成へのアクセス
description: 連合オーディエンス構成に必要な権限について説明します。
exl-id: 84138456-218b-4beb-ae7b-146213b03cc2
source-git-commit: 62bbed4818caf06539234f97d4c0d1cf9c9a52d1
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 46%

---

# 連合オーディエンス構成へのアクセス {#feature-access}

## サンドボックスへのアクセスの管理 {#access-sandboxes}

Adobe Experience Platform 連合オーディエンス構成を購入すると、この時点でアクティブになっているサンドボックスごとに製品プロファイルが作成されます。この製品プロファイルは、Admin Console の **Adobe Experience Platform** 製品カードの下に作成され、次の命名規則に従います。`ACP_FAC - <<SandboxName>> - admin.` 特定のサンドボックスの連合オーディエンス構成にアクセスするには、このサンドボックス用に作成された製品プロファイルにユーザーを追加する必要があります。

例えば、「fac-test」という名前の新しいサンドボックスをアクティブ化すると、対応する製品プロファイル「ACP_FAC - fac-test - admin」が作成されます。このサンドボックスで連合オーディエンス構成にアクセスするには、ユーザーをこの製品プロファイルに追加する必要があります。

## 連合オーディエンス構成へのアクセスの管理

**Federated Audience Composition** にアクセスするには、まず、Federated Audience Composition の様々な側面にアクセスするために必要な権限を割り当てる必要があります。 次に、これらの役割を、**Federated Audience Composition** にアクセスする必要があるユーザーに割り当てる必要があります。

権限を割り当てることができるのは管理者のみです。

1. **[!UICONTROL 権限]**&#x200B;メニューに移動します。

1. **[!UICONTROL 役割]**&#x200B;メニューから、更新する&#x200B;**[!UICONTROL 役割]**&#x200B;を選択します。

   ![](assets/access_fda_1.png)

1. 「**[!UICONTROL 編集]**」を選択して、役割の権限を変更します。

   ![](assets/access_fda_2.png)

1. ユーザーに必要な権限を追加します。 Federated Audience Composition へのアクセスに対して、次の権限を追加できます。

   | 権限 | 説明 |
   | ---------- | ----------- |
   | 連合データの管理 | この権限を使用して、Federated Audience Composition のすべての側面を管理します。 この権限には、フェデレーション データベースの管理、フェデレーション スキーマの管理、フェデレーション データ モデルの管理、およびフェデレーション コンポジションの管理が含まれます。 |
   | 連合データベースの管理 | このアクセス許可を使用して、フェデレーション データベースへの接続を追加、表示、更新、および削除します。 |
   | 連合データベースの表示 | この権限を使用して、フェデレーション データベースへの接続を表示します。 |
   | 連合スキーマの管理 | この権限を使用して、スキーマを作成、表示、更新、削除および更新します。 |
   | 連合スキーマデータの表示 | この権限を使用して、スキーマセクション内の「データ」タブを表示します。 |
   | 連合スキーマを表示 | この権限を使用して、スキーマテーブルを表示します。 |
   | 連合データモデルの管理 | この権限を使用して、データモデルを作成、表示、更新、削除します。 |
   | 連合データモデルを表示 | この権限を使用して、データモデルを表示します。 |
   | フェデレーション監査追跡の表示 | この権限を使用して、Federated Audience Composition の監査記録を表示します。 |
   | フェデレーション構成の管理 | この権限を使用して、フェデレーテッド コンポジションを作成、表示、更新、削除します。 |
   | フェデレーション構成の表示 | この権限を使用して、フェデレーションされたコンポジションを表示します。 |

   ![](assets/permissions.png)

1. 必要な変更を加えたら、「**[!UICONTROL 保存]**」を選択します。

この役割に既に割り当てられているユーザーは、権限が自動的に更新され、連合オーディエンス構成にアクセスできます。

この役割を新しいユーザーに割り当てるには：

1. 役割ダッシュボード内の「**[!UICONTROL ユーザー]**」タブに移動し、「**[!UICONTROL ユーザーを追加]**」を選択します。

   ![](assets/access_fda_4.png)

1. ユーザーの名前またはメールアドレスを入力するか、使用可能なリストから選択します。完了したら、「**[!UICONTROL 保存]** を選択します。

<!-- Alternatively, you can assign one of the pre-existing roles to the users, depending on what permissions they need. For more information on assigning pre-existing roles to a user, please read the [guide on managing users for a product profile](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/users).

| Role name | Permissions |
| --------- | ----------- |
| FAC Data Managers | <ul><li>Manage Federated Compositions</li><li>View Federated Databases</li><li>View Federated Schemas</li><li>View Federated Schema Data</li><li>View Federated Data Models</li></ul> |
| FAC Composition Managers | <ul><li>Manage Federated Compositions</li></ul> |
| FAC Administrators | <ul><li>Manage Federated Data</li></ul> | -->

次に、ユーザーはインスタンスにアクセスする手順が記載されたメールを受信します。まだユーザーを作成していない場合は、[このドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/abac/permissions-ui/users)を参照してください。
