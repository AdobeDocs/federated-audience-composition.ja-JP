---
audience: end-user
title: スキーマの基本を学ぶ
description: スキーマの開始方法を学ぶ
badge: label="限定提供" type="Informative"
source-git-commit: 96508e648b2f97dd9410df617ed3a5fd8b354b52
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 31%

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

スキーマは、データがデータベーステーブルにどのように関連付けられるかを定義するアプリケーション内のオブジェクトです。
スキーマがテーブルを参照します。

## スキーマの作成方法 {#schema-create}

「**[!UICONTROL FEDERATED DATA]**」セクションで、「**[!UICONTROL モデル]** リンクに移動します。 「**[!UICONTROL スキーマ]**」タブがあります。
「**[!UICONTROL スキーマを作成]**」ボタンをクリックします。

![](assets/schema_create.png){zoomable="yes"}

ドロップダウンリストでソースデータベースを選択し、「**[!UICONTROL テーブルを追加]** タブをクリックします

![](assets/schema_tables.png){zoomable="yes"}

データベース内のすべてのテーブルにアクセスし、スキーマを作成できるようになります。

テーブルを追加すると、そのフィールドにアクセスでき、本当に必要なものを保持できます。

![](assets/schema_fields.png){zoomable="yes"}

## スキーマの編集方法 {#schema-edit}

スキーマを編集するには、スキーマフォルダーでスキーマの名前をクリックします。 以下のページにアクセスできます。
「**[!UICONTROL 編集]** ボタンをクリックします。

![](assets/schema_edit.png){zoomable="yes"}

## スキーマのデータをプレビューするにはどうすればよいですか？ {#schema-preview}

スキーマが表すテーブルのデータをプレビューするには、次のように「**[!UICONTROL データ]**」タブに移動します。

![](assets/schema_data.png){zoomable="yes"}

「**[!UICONTROL 列を設定]**」ボタンをクリックして、データの概要を変更できます。

![](assets/schema_columns.png){zoomable="yes"}

## スキーマの削除方法は？ {#schema-delete}

スキーマを削除するには、「**[!UICONTROL 詳細]**」ボタン、「**[!UICONTROL 削除]** の順にクリックします。

![](assets/schema_delete.png){zoomable="yes"}