---
audience: end-user
title: プロファイルを保存アクティビティの使用
description: プロファイルを保存アクティビティの使用方法について学ぶ
exl-id: 1c840838-32d5-4ceb-8430-835a235b7436
source-git-commit: ca975be136155f69bc84362fde8c283b1c4edffe
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 55%

---

# プロファイルを保存 {#save-profile}

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile"
>title="プロファイルを保存"
>abstract="プロファイルを保存アクティビティを使用すると、外部ウェアハウスのデータを統合して Experience Platform プロファイルを強化し、追加の属性で顧客プロファイルを強化できます。 "

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_aepschemalist"
>title="Experience Platform スキーマを選択"
>abstract="プロファイルの Experience Platform スキーマを選択します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentitynamespace"
>title="プライマリ識別フィールドの選択"
>abstract="データベース内のターゲットプロファイルの識別に使用するプライマリ ID を選択します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_selectaepschema"
>title="Experience Platform スキーマを選択"
>abstract="プロファイルの Experience Platform スキーマを選択します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode"
>title="プロファイル更新モードの保存"
>abstract="プロファイルを保存アクティビティで使用できる更新モードには、完全更新と増分更新があります。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode_full"
>title="完全更新"
>abstract="完全更新モードは、プロファイルの完全なセットを更新して充実させます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_updatemode_incremental"
>title="増分更新"
>abstract="増分更新モードは、最後にエンリッチメントが実行されてから変更されたプロファイルを更新します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentityfield"
>title="プライマリ ID フィールド"
>abstract="プライマリ ID フィールドは、エンリッチメントのためにプロファイルを結合する際の信頼できるソースを示します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_requiredfieldscheck"
>title="必須フィールドの条件"
>abstract="必須フィールドは、データを書き出す際に、すべてのプロファイルまたはレコードに入力する必要がある属性です。 必須フィールドがない場合、書き出しは完了または有効になりません。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveprofile_primaryidentitycheck"
>title="プライマリ ID フィールドの条件"
>abstract="各プロファイルまたはレコードの一意の ID。 これにより、すべてのレコードを明確に認識して一致させることができ、データの重複を防ぐことができます。"

**プロファイルを保存**&#x200B;アクティビティを使用すると、外部ウェアハウスから統合されたデータを使用して Adobe Experience Platform プロファイルを強化できます。

このアクティビティは、通常、データをプラットフォームに物理的に移動または複製せずに、追加の属性やインサイトを取り込むことで、顧客プロファイルを強化するために使用されます。

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
