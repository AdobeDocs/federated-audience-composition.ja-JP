---
audience: end-user
title: エンリッチメントアクティビティの使用
description: エンリッチメントアクティビティの使用方法について説明します
badge: label="限定提供" type="Informative"
exl-id: 6bf12c25-fbef-4588-89d0-28215cbcbf58
source-git-commit: 8fa60d20dc574bbddc0106508d57a1cd3f3d3db8
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 92%

---

# エンリッチメント {#enrichment}

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment"
>title="「エンリッチメント」アクティビティ"
>abstract="**エンリッチメント**&#x200B;アクティビティでは、データベースからの追加情報を使用してターゲットデータを強化できます。 一般的に、セグメント化アクティビティ後の構成で使用されます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_data"
>title="「エンリッチメント」アクティビティ"
>abstract="エンリッチメントデータを構成に追加すると、「**エンリッチメント**」アクティビティの後に追加したアクティビティでこのデータを使用して、行動、環境設定、選択に基づいてプロファイルを個別のグループにセグメント化できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_simplejoin"
>title="リンク定義"
>abstract="作業テーブルデータと連合データベースの間にリンクを作成します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_enrichment_reconciliation"
>title="エンリッチメントの紐付け"
>abstract="紐付けパラメーターを設定します。"

>[!CONTEXTUALHELP]
>id="dc_targetdata_personalization_enrichmentdata"
>title="エンリッチメントデータ"
>abstract="構成の強化に使用するデータを選択します。 2 種類のエンリッチメントデータを選択できます。スキーマの単一のエンリッチメント属性（ターゲティングディメンションとも呼ばれる）、またはテーブル間の基数が 1-N のリンクであるコレクションリンクです。"

**エンリッチメント**&#x200B;アクティビティでは、連合データベースからの追加情報を使用してターゲットデータを強化できます。一般的に、セグメント化アクティビティ後の構成で使用されます。

Federated Audience Composition 宛先への接続を設定した場合は、エンリッチメント アクティビティを使用して、外部データベースからの属性でAdobe Experience Platformに取り込むデータを強化できます。 [詳しくは、外部データを使用して Adobe Experience Platform オーディエンスを強化する方法を参照してください](../../connections/destinations.md)

エンリッチメントデータは次のいずれかを実行できます。

* 構成のターゲットと&#x200B;**同じ作業用テーブルから**：

  *顧客のグループをターゲットに設定し、「生年月日」フィールドを現在の作業用テーブルに追加*

* **別の作業用テーブルから**：

  *顧客のグループをターゲットにし、「購入」テーブルから取得した「金額」フィールドと「製品のタイプ」フィールドを追加します*。

エンリッチメントデータを構成に追加すると、**エンリッチメント**&#x200B;アクティビティの後に追加したアクティビティで、このデータを使用して、顧客の行動、環境設定、選択に基づいて顧客を個別のグループにセグメント化できます。

<!--For instance, you can add to the working table information related to customers' purchases and use this data to personalize emails with their latest purchase or the amount spent on these purchases.-->

## エンリッチメントアクティビティを設定します。 {#enrichment-configuration}

次の手順に従って、**エンリッチメント**&#x200B;アクティビティを設定します。

1. **オーディエンスを作成**&#x200B;および&#x200B;**結合**&#x200B;アクティビティを追加します。
1. **エンリッチメント**&#x200B;アクティビティを追加します。

   ![](../assets/enrichment.png)

1. 構成に複数のトランジションを設定している場合は、「**[!UICONTROL プライマリセット]**」フィールドを使用して、データを強化するためにプライマリセットとして使用するトランジションを定義できます。

1. 「**エンリッチメントデータを追加**」をクリックし、データのエンリッチメントに使用する属性を選択します。

   ![](../assets/enrichment-add.png)

   >[!NOTE]
   >
   >属性選択画面の「**式を編集**」ボタンを使用すると、属性を選択する高度な式を作成できます。

<!--PAS VU SUR INSTANCE: You can select two types of enrichment data: a single enrichment attribute from the target dimension, or a collection link. Each of these types is detailed in the examples below:

    * [Single enrichment attribute](#single-attribute)
    * [Collection lnk](#collection-link)-->

<!--
## Examples {#example}

### Single enrichment attribute {#single-attribute}

Here, we are just adding a single enrichment attribute, for example, the date of birth. Follow these steps:

1. Click inside the **Attribute** field.
1. Select a simple field from the schema, also known as targeting dimension, the date of birth in our example. 
1. Click **Confirm**.
-->
<!--### Collection link {#collection-link}

In this more complex use case, we will select a collection link which is a link with a 1-N cardinality between tables. Let's retrieve the three latest purchases that are less than 100$. For this you need to define:

* an enrichment attribute: the **Total amount** field
* the number of lines to retrieve: 3
* a filter: filter out items that are greater than 100$
* a sorting: descendant sorting on the **Order date** field. 

#### Add the attribute {#add-attribute}

This is where you select the collection link to use as enrichment data.

1. Click inside the **Attribute** field.
1. Click **Display advanced attributes**.
1. Select the **Total amount** field from the **Purchases** table. 

#### Define the collection settings{#collection-settings}

Then, define how the data is collected and the number of records to retrieve.

1. Select **Collect data** in the **Select how the data is collected** drop-down.
1. Type "3" in the **Lines to retrieve (Columns to create)** field. 

If you want, for example, to get the average amount of purchases for a customer, select **Aggregated data** instead, and select **Average** in the **Aggregate function** drop-down.

#### Define the filters{#collection-filters}

Here, we define the maximum value for the enrichment attribute. We filter out items that are greater than 100$. [Learn how to work with the query modeler](../../query/query-modeler-overview.md)

1. Click **Edit filters**.
1. Add the two following filters: **Total amount** exists AND **Total amount** is less than 100. The first one filters NULL values as they would appear as the greatest value.
1. Click **Confirm**.

#### Define the sorting{#collection-sorting}

We now need to apply sorting in order to retrieve the three **latest** purchases.

1. Activate the **Enable sorting** option.
1. Click inside the **Attribute** field.
1. Select the **Order date** field.
1. Click **Confirm**. 
1. Select **Descending** from the **Sort** drop-down.-->
