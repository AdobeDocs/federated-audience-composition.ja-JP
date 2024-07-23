---
audience: end-user
title: スキーマの基本を学ぶ
description: スキーマの開始方法を学ぶ
badge: label="限定提供" type="Informative"
source-git-commit: d168a67fb14644dab5d33e0e9d17c850d2a66262
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 20%

---

# スキーマの基本を学ぶ {#schemas}


>[!CONTEXTUALHELP]
>id="dc_schema_create_select_tables"
>title="テーブルの選択"
>abstract="データモデルに追加するテーブルを選択します。"

>[!CONTEXTUALHELP]
>id="dc_schema_create_key"
>title="キー"
>abstract="データ紐付けのキーを選択します。"

>[!CONTEXTUALHELP]
>id="dc_schema_create_schema_name"
>title="スキーマの名前"
>abstract="スキーマの名前を入力します。"


>[!CONTEXTUALHELP]
>id="dc_schema_edit_description"
>title="スキーマの説明"
>abstract="スキーマの説明には、列、タイプ、ラベルがリストされます。 また、スキーマの紐付けキーを確認することもできます。 スキーマ定義を更新するには、鉛筆アイコンをクリックします。"

>[!CONTEXTUALHELP]
>id="dc_schema_filter_sources"
>title="フィルタリングするソースデータベースの選択"
>abstract="ソースに基づいてスキーマをフィルタリングできます。 1 つまたは複数の連合データベースを選択して、このスキーマを表示します。"


## スキーマとは {#schema-start}

スキーマは、データベースのテーブルを表すものです。 これは、データがデータベーステーブルにどのように関連付けられているかを定義するアプリケーション内のオブジェクトです。

スキーマを作成すると、FAC でテーブルの表現を操作できます。

- わかりやすい名前と説明を指定して、ユーザーが理解しやすいようにします
- 各フィールドの実際の用途に応じた表示を決定する
- [ データモデル ](../data-management/gs-models.md#data-model-start) の必要に応じて、プライマリキーを選択して、スキーマ間をリンクします

## スキーマの作成 {#schema-create}

FAC でスキーマを作成するには、次の手順に従います。
「**[!UICONTROL FEDERATED DATA]**」セクションで、「**[!UICONTROL モデル]** リンクに移動します。 「**[!UICONTROL スキーマ]**」タブがあります。
「**[!UICONTROL スキーマを作成]**」ボタンをクリックします。

![](assets/schema_create.png){zoomable="yes"}

次の場所にあるドロップダウンリストを使用して、新しいインターフェイスにアクセスできます
アプリケーションに接続されているすべてのデータベース。 詳しくは、[ データベース接続 ](../connections/connections.md#connections-fdb) を参照してください。
リストでソースデータベースを選択し、「**[!UICONTROL テーブルを追加]** タブをクリックします

![](assets/schema_tables.png){zoomable="yes"}

データベース内のすべてのテーブルのリストにアクセスできます。

スキーマを作成するテーブルを追加すると、以下のようにフィールドにアクセスできます。

![](assets/schema_fields.png){zoomable="yes"}

テーブルごとに、次の操作を実行できます。

- 指定されたスキーマラベルの名前を変更
- 説明を追加
- すべてのフィールドの名前を変更し、表示を決定します。
- スキーマのプライマリキーを選択

例えば、追加したテーブルの直後に、次のようにテーブルが読み込まれているとします。

![](assets/schema_lumaorder.png){zoomable="yes"}

スキーマは、次のように定義できます。

![](assets/schema_lumaorders.png){zoomable="yes"}

## スキーマの編集 {#schema-edit}

スキーマを編集するには、スキーマフォルダーでスキーマの名前をクリックします。 以下のページにアクセスできます。
「**[!UICONTROL 編集]** ボタンをクリックします。

![](assets/schema_edit.png){zoomable="yes"}

スキーマを作成する場合と同じ方法でアクセスできます。

- 指定されたスキーマラベルの名前を変更
- 説明を追加
- すべてのフィールドの名前を変更し、表示を決定します。
- スキーマのプライマリキーを選択

![](assets/schema_edit_orders.png){zoomable="yes"}

## スキーマ内のデータのプレビュー {#schema-preview}

スキーマが表すテーブルのデータをプレビューするには、次のように「**[!UICONTROL データ]**」タブに移動します。
**[!UICONTROL 計算]** リンクをクリックすると、録画の合計数を確認できます。

![](assets/schema_data.png){zoomable="yes"}

「**[!UICONTROL 列を設定]**」ボタンをクリックして、データの概要を変更できます。

![](assets/schema_columns.png){zoomable="yes"}

## スキーマの削除 {#schema-delete}

スキーマを削除するには、「**[!UICONTROL 詳細]**」ボタン、「**[!UICONTROL 削除]** の順にクリックします。

![](assets/schema_delete.png){zoomable="yes"}
