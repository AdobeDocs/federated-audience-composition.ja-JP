---
audience: end-user
title: 「データSourceを変更」アクティビティ
description: データソースを変更アクティビティを使用して、コンポジションで使用されるデータソースを変更し、コンポジション内のデータをより柔軟に管理する方法を説明します。
source-git-commit: 2a21dcde345febdaad0934c8835df5f7ae8c30f6
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 18%

---


# データソースを変更

>[!IMPORTANT]
>
>**[!UICONTROL ディメンションを変更]** アクティビティと **[!UICONTROL データソースを変更]** アクティビティは、1 行に追加 **しない** でください。 両方のアクティビティを連続して使用する必要がある場合は、それらの間に&#x200B;**[!UICONTROL エンリッチメント]**&#x200B;アクティビティを含めます。これにより、適切な実行が確保され、潜在的な競合やエラーが防止されます。

**[!UICONTROL データソースを変更]** アクティビティを使用すると、コンポジションで使用されるデータソースを変更できます。

## 設定 {#configure}

**[!UICONTROL データソースを変更]** アクティビティをキャンバスに追加したら、ワークフローのデータソースを定義できます。

![Federated Audience Composition ワークスペース内で「データソース」オプションがハイライト表示されています。](/help/compositions/assets/change-data-source/configure.png){zoomable="yes"}{width="70%"}{align="center"}

| ソース | 説明 |
| ------ | ----------- |
| FDA 外部アカウント | Federated Audience Composition を通じてAdobe Campaignに接続された外部クラウドデータベース。 |

**[!UICONTROL FDA 外部アカウント]** を選択したら、接続する外部アカウントを選択できます。

![ 外部アカウントオプションを表示するポップオーバーが表示されます。](/help/compositions/assets/change-data-source/fda-external-account.png){zoomable="yes"}{width="70%"}{align="center"}
