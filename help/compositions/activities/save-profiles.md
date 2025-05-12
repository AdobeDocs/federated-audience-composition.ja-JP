---
audience: end-user
title: プロファイルを保存アクティビティの使用
description: プロファイルを保存アクティビティの使用方法について学ぶ
exl-id: 1c840838-32d5-4ceb-8430-835a235b7436
source-git-commit: fae57356b8e9f5358a39d31cad4883171a310fb6
workflow-type: ht
source-wordcount: '238'
ht-degree: 100%

---

# プロファイルを保存 {#save-profile}

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile"
>title="プロファイルを保存"
>abstract="プロファイルを保存アクティビティを使用すると、外部ウェアハウスのデータを統合して Experience Platform プロファイルを強化し、追加の属性で顧客プロファイルを強化できます。 "

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_aepschemalist"
>title="AEP スキーマの選択"
>abstract="プロファイルの Experience Platform スキーマを選択します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentitynamespace"
>title="プライマリ識別フィールドの選択"
>abstract="データベース内のターゲットプロファイルの識別に使用するプライマリ ID を選択します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_selectaepschema"
>title="AEP スキーマの選択"
>abstract="プロファイルの Experience Platform スキーマを選択します。"

**プロファイルを保存**&#x200B;アクティビティを使用すると、外部ウェアハウスから統合されたデータを使用して Adobe Experience Platform プロファイルを強化できます。

このアクティビティは通常、データを物理的にプラットフォームに移動または複製せずに、追加の属性とインサイトを取り込むことで、顧客プロファイルの強化に使用されます。

## プロファイルを保存アクティビティの設定 {#save-profile-configuration}

**プロファイルを保存**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **プロファイルを保存**&#x200B;アクティビティを構成に追加します。

   ![](../assets/save-profile.png)

1. 作成するプロファイルのラベルを指定します。

   >[!IMPORTANT]
   >
   >オーディエンスラベルは、現在のサンドボックス内で一意にする必要があります。既存のオーディエンスと同じラベルにすることはできません。

1. 使用する Adobe Experience Platform スキーマを選択します。

   ![](../assets/save-profile-2.png)

1. データベース内のプロファイルの識別に使用するプライマリ ID フィールドを選択します。

1. 追加のデータ属性を紐付けする場合は、「**属性を追加**」をクリックします。

   次に、マッピングする属性ごとに、「**ソース**」フィールド（外部データ）と「**宛先**」フィールド（スキーマフィールド）を指定します。

   ![](../assets/save-profile-3.png)

1. 設定が完了したら、「**開始**」をクリックします。
