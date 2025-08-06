---
audience: end-user
title: データソースを変更アクティビティ
description: データソースを変更アクティビティを使用して、構成で使用されるデータソースを変更し、構成内のデータの管理の柔軟性を向上させる方法について説明します。
exl-id: 8f8e627a-fef9-42b8-a42a-bfa1c421b202
source-git-commit: 59983bb7fd0f8886cc38bfcfc8d7005db4747ac0
workflow-type: ht
source-wordcount: '162'
ht-degree: 100%

---

# データソースを変更

>[!IMPORTANT]
>
>**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティと&#x200B;**[!UICONTROL データソースを変更]**&#x200B;アクティビティを 1 つの行に追加&#x200B;**しない**&#x200B;でください。両方のアクティビティを連続して使用する必要がある場合は、それらの間に&#x200B;**[!UICONTROL エンリッチメント]**&#x200B;アクティビティを含めます。これにより、適切に実行されるようになり、潜在的な競合やエラーが防止されます。

**[!UICONTROL データソースを変更]**&#x200B;アクティビティを使用すると、構成で使用されるデータソースを変更できます。

## 設定 {#configure}

**[!UICONTROL データソースを変更]**&#x200B;アクティビティをキャンバスに追加したら、ワークフローのデータソースを定義できます。

![連合オーディエンス構成ワークスペース内にデータソースオプションがハイライト表示されています。](/help/compositions/assets/change-data-source/configure.png){zoomable="yes"}{width="70%"}

| ソース | 説明 |
| ------ | ----------- |
| FDA 外部アカウント | 連合オーディエンス構成に接続された外部クラウドデータベース。 |

**[!UICONTROL FDA 外部アカウント]**&#x200B;を選択したら、接続する外部アカウントを選択できます。

![外部アカウントオプションを表示するポップオーバーが表示されています。](/help/compositions/assets/change-data-source/fda-external-account.png){zoomable="yes"}{width="70%"}
