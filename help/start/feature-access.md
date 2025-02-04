---
title: Federated Audience 構成へのアクセス
description: Federated Audience Composition に必要な権限について説明します
source-git-commit: ed72ae722ffd5fbf14f491630b748a5009f4ebc5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 36%

---

# Federated Audience 構成へのアクセス {#feature-access}

## サンドボックスへのアクセスの管理 {#access-sandboxes}

連合オーディエンス構成アドオンを購入すると、この時点でアクティブになっているサンドボックスごとに製品プロファイルが作成されます。この製品プロファイルは、Admin Console の **Adobe Experience Platform** 製品カードの下に作成され、次の命名規則に従います。`ACP_FAC - <<SandboxName>> - admin.` 特定のサンドボックスの連合オーディエンス構成にアクセスするには、このサンドボックス用に作成された製品プロファイルにユーザーを追加する必要があります。

例えば、「fac-test」という名前の新しいサンドボックスをアクティブ化すると、対応する製品プロファイル「ACP_FAC - fac-test - admin」が作成されます。このサンドボックスで連合オーディエンス構成にアクセスするには、ユーザーをこの製品プロファイルに追加する必要があります。

## Federated Audience コンポジションへのアクセスの管理

>[!AVAILABILITY]
>
>権限は、2 月のリリースの一部として利用できます。

**Federated Audience Composition** にアクセスするには、まず **Federated Data の管理** 権限が適切な役割に割り当てられていることを確認する必要があります。 次に、これらの役割を、**Federated Audience Composition** へのアクセスを必要とするユーザーに割り当てる必要があります。

権限を割り当てることができるのは管理者のみです。

1. **[!UICONTROL 権限]** メニューに移動します。

1. **[!UICONTROL 役割]** メニューから、更新する **[!UICONTROL 役割]** を選択します。

   ![](assets/access_fda_1.png)

1. **[!UICONTROL 編集]** をクリックして、役割の権限を変更します。

   ![](assets/access_fda_2.png)

1. **Federated Data** リソースを追加して、ドロップダウンメニューから **[!UICONTROL Federated Data を管理]** を選択します。

   ![](assets/access_fda_3.png)

1. 必要な変更を加えたら、「**[!UICONTROL 保存]**」をクリックします。

この役割に既に割り当てられているユーザーは、権限が自動的に更新され、Federated Audience Composition にアクセスできます。

この役割を新しいユーザーに割り当てるには：

1. 役割ダッシュボード内の「**[!UICONTROL ユーザー]**」タブに移動し、「**[!UICONTROL ユーザーを追加]**」をクリックします。

   ![](assets/access_fda_4.png)

1. ユーザーの名前またはメールアドレスを入力するか、使用可能なリストから選択します。 完了したら、「**[!UICONTROL 保存]**」をクリックします。

その後、インスタンスへのアクセス手順を記載したメールがユーザーに届きます。 まだユーザーを作成していない場合は、[このドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/abac/permissions-ui/users)を参照してください。


