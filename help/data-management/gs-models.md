---
audience: end-user
title: データモデルの基本を学ぶ
description: データモデルの開始方法について説明します
badge: label="限定提供" type="Informative"
exl-id: 8f9e9895-dcd7-4718-8922-4f7fefe9ed94
source-git-commit: f549f1611bfe6deb6dc684e3a0d9c968ba7c184a
workflow-type: ht
source-wordcount: '380'
ht-degree: 100%

---

# データモデルの基本を学ぶ {#data-model}

>[!CONTEXTUALHELP]
>id="dc_model_menu"
>title="モデルの操作"
>abstract="この画面には、スキーマとデータモデルがリストされます。 「**作成**」ボタンからスキーマとデータモデルを作成できます。"

>[!CONTEXTUALHELP]
>id="dc_datamodel_add_schema"
>title="スキーマの選択"
>abstract="データモデルのスキーマを選択します。"


>[!CONTEXTUALHELP]
>id="dc_datamodel_add_audience"
>title="オーディエンスの選択"
>abstract="データモデルのオーディエンスを選択します。"

>[!CONTEXTUALHELP]
>id="dc_datamodel_properties"
>title="データモデルのプロパティ"
>abstract="データモデルのラベルを入力します。"


## データモデルとは {#data-model-start}

データモデルは、スキーマ、オーディエンスおよびこれらの間のリンクのセットです。オーディエンスとデータベースデータを連合するために使用されます。

詳しくは、[スキーマ](../customer/schemas.md#schema-start)を参照してください。

詳しくは、[オーディエンス](../start/audiences.md)を参照してください。

例えば、データモデルの表現を以下に示します。テーブルおよびこの名前と、テーブル間のリンクです。

![](assets/datamodel.png){zoomable="yes"}

連合オーディエンス構成では、多くのデータモデルを作成できます。

作成は、ユースケースに基づいて行います。必要なテーブルを選択し、必要に応じてテーブルをリンクします。

## データモデルの作成 {#data-model-create}

データモデルを作成するには、次の手順に従います。

1. 「**[!UICONTROL 連合データ]**」セクションで、**[!UICONTROL モデル]**&#x200B;リンクに移動し、「**[!UICONTROL データモデル]**」タブを参照します。

   ![](assets/datamodel_create.png){zoomable="yes"}

1. 「**[!UICONTROL データモデルを作成]**」ボタンをクリックして、データモデルの名前を定義し、「**[!UICONTROL 作成]**」ボタンをクリックします。

   ![](assets/datamodel_name.png){zoomable="yes"}

1. 次に、データモデルのスキーマ、オーディエンおよびリンクを追加します。

   ![](assets/datamodel_schemas.png){zoomable="yes"}

### リンクを作成 {#data-model-links}

データモデルのテーブル間にリンクを作成するには、次の手順に従います。

1. 1 つのテーブルの&#x200B;**[!UICONTROL リンクを作成]**&#x200B;メニューをクリックするか、「**[!UICONTROL リンクを作成]**」ボタンをクリックして、2つのテーブルを選択します。

   ![](assets/datamodel_createlinks.png){zoomable="yes"}

1. 指定されたフォームに入力して、リンクを定義します。

   ![](assets/datamodel_link.png){zoomable="yes"}

   **カーディナリティ**

   * 一対多：ソーステーブルの 1 つのオカレンスは、ターゲットテーブルの複数のオカレンスに対応させることができますが、ターゲットテーブルの 1 つのオカレンスは、ソーステーブルの最大 1 つのオカレンスにのみ対応させることができます。

   * 多対一：ターゲットテーブルの 1 つのオカレンスは、ソーステーブルの複数のオカレンスに対応させることができますが、ソーステーブルの 1 つのオカレンスは、ターゲットテーブルの最大 1 つのオカレンスにのみ対応させることができます。

   * 一対一：ソーステーブルの 1 つのオカレンスは、最大でターゲットテーブルの 1 つのオカレンスに対応させることができます。

データモデルに対して定義されたすべてのリンクが、次のようにリストされます。

![](assets/datamodel_alllinks.png){zoomable="yes"}

## ハウツービデオ {#data-model-video}

データモデルの作成方法については、次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/3432020)
