---
audience: end-user
title: スキーマの基本を学ぶ
description: スキーマの開始方法について説明します
badge: label="限定提供" type="Informative"
exl-id: 2c939185-f1c1-4f2b-ae1b-e2539e121eff
source-git-commit: c2d4ec21f497a1c4ad9c1701b4283edd16ca0611
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 97%

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
>abstract="ソースに基づいてスキーマをフィルタリングできます。 1 つまたは複数の連合データベースを選択して、そのスキーマを表示します。"

## スキーマとは {#schema-start}

スキーマは、データベースのテーブルの表現です。これは、データをデータベーステーブルに関連付ける方法を定義するアプリケーション内のオブジェクトです。

スキーマを作成することにより、Experience Platform 連合オーディエンス構成でテーブルの表現を定義できます。

* ユーザーが理解しやすいように、わかりやすい名前と説明を指定します
* 実際の用途に応じて各フィールドの表示を決定します
* [データモデル](../data-management/gs-models.md#data-model-start)で必要に応じて、このプライマリキー間のスキーマをリンクするために、プライマリキーを選択します

>[!CAUTION]
>
>複数のサンドボックスを同じデータベースに接続する際は、異なる作業スキーマを使用する必要があります。
>

## スキーマの作成 {#schema-create}

連合オーディエンス構成でスキーマを作成するには、次の手順に従います。

1. 「**[!UICONTROL 連合データ]**」セクションで、**[!UICONTROL モデル]**&#x200B;リンクに移動します。「**[!UICONTROL スキーマ]**」タブを参照し、「**[!UICONTROL スキーマを作成]**」ボタンをクリックします。

   ![](assets/schema_create.png){zoomable="yes"}

   この手順では、ドロップダウンリストを備えた新しい画面にアクセスして、環境に接続されているデータベースを検索できます。データベース接続について詳しくは、[この節](../connections/connections.md#connections-fdb)を参照してください。

1. リストでソースデータベースを選択し、「**[!UICONTROL テーブルを追加]**」タブをクリックします。

   ![](assets/schema_tables.png){zoomable="yes"}

   その後、データベース内のすべてのテーブルのリストが表示されます。

1. スキーマを作成するテーブルを追加すると、以下のように、そのフィールドにアクセスできるようになります。

   ![](assets/schema_fields.png){zoomable="yes"}

   テーブルごとに、次の操作を実行できます。

   * スキーマのラベルを変更する
   * 説明を追加する
   * すべてのフィールドの名前を変更し、表示を設定する
   * スキーマのプライマリキーを選択する

   例えば、次のテーブルの場合、以下が読み込まれます。

   ![](assets/schema_lumaorder.png){zoomable="yes"}

   スキーマは、次のように定義できます。

   ![](assets/schema_lumaorders.png){zoomable="yes"}

## スキーマの編集 {#schema-edit}

スキーマを編集するには：

1. スキーマフォルダー内のスキーマの名前をクリックします。

1. 「**[!UICONTROL 編集]**」ボタンをクリックします。

   ![](assets/schema_edit.png){zoomable="yes"}

   [スキーマの作成](#schema-create)時と同じオプションにアクセスできます。

   ![](assets/schema_edit_orders.png){zoomable="yes"}

## スキーマ内のデータのプレビュー {#schema-preview}

スキーマで表現されたテーブル内のデータをプレビューするには、以下のように「**[!UICONTROL データ]**」タブを参照します。

レコードの合計数をプレビューするには、**[!UICONTROL 計算]**&#x200B;リンクをクリックします。

![](assets/schema_data.png){zoomable="yes"}

データの表示を変更するには、「**[!UICONTROL 列を設定]**」ボタンをクリックします。

![](assets/schema_columns.png){zoomable="yes"}

## スキーマの削除 {#schema-delete}

スキーマを削除するには、「**[!UICONTROL その他]**」ボタンをクリックし、「**[!UICONTROL 削除]**」を選択します。

![](assets/schema_delete.png){zoomable="yes"}
