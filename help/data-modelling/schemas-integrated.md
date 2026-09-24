---
audience: end-user
title: スキーマの概要
description: Adobe Experience Platform UI内でFederated Audience Compositionのスキーマを作成して使用する方法について説明します。
TQID: https://experienceleague.adobe.com/cpkFeiskYDpixNo01llqC3UKK8XfewN7XC2yAf1wOYQ
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 3b159f95e28414b75b44e41e822e9e3d0e35b537
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 35%
---
# スキーマの概要 {#schemas}

>[!AVAILABILITY]
>
>新しいスキーマエクスペリエンスは、一部の顧客のみが利用できます。 詳しくは、Adobe カスタマーケアにお問い合わせください。
>
>新しいスキーマエクスペリエンスにアクセスできない場合は、[&#x200B; スキーマの概要](./schemas.md)をお読みください。
>
>スキーマにアクセスするには、次のいずれかの権限が必要です。
>
>-**フェデレーションスキーマの管理**
>-**連合スキーマの表示**
>
>必要な権限について詳しくは、[アクセス制御ガイド](/help/governance-privacy-security/access-control.md)を参照してください。

スキーマは、データベースのテーブルの表現です。 これは、データをデータベーステーブルに関連付ける方法を定義するアプリケーション内のオブジェクトです。

スキーマを作成することにより、Experience Platform 連合オーディエンス構成でテーブルの表現を定義できます。

* ユーザーが理解しやすいように、わかりやすい名前と説明を指定します
* 実際の用途に応じて各フィールドの表示を決定します
* [データモデル](../data-modelling/models.md#data-model-start)で必要に応じて、このプライマリキー間のスキーマをリンクするために、プライマリキーを選択します

>[!CAUTION]
>
>同じデータベースに複数のサンドボックスを接続する場合は、異なる作業スキーマを使用する必要があります。

## スキーマの作成 {#create}

>[!CONTEXTUALHELP]
>id="platform_schemas_manageconfiguration"
>title="設定を管理"
>abstract="一時的な空白コンテンツ。"

Federated Audience Compositionでスキーマを作成するには、Experience Platform UIの&#x200B;**[!UICONTROL Data Management]** セクション内の&#x200B;**[!UICONTROL Schemas]**&#x200B;を選択します。 スキーマ UIで、「**[!UICONTROL スキーマを作成]**」を選択します。

![&#x200B; スキーマとスキーマの作成ボタンは、両方ともスキーマ UI内で強調表示されます。](/help/data-modelling/assets/integrated/select-create-schema.png)

「スキーマを作成」ポップオーバーが表示されたら、「**[!UICONTROL リレーショナル]**」、「**[!UICONTROL スキーマを見つける]**」および「**[!UICONTROL 次へ]**」を選択して、連合オーディエンス構成のスキーマを作成します。

![&#x200B; リレーショナルスキーマの作成ポップオーバー内で「スキーマを検索」ボタンが強調表示されます。](/help/data-modelling/assets/integrated/select-discover-schemas.png)

**[!UICONTROL 連合データベースを選択]**&#x200B;ポップオーバーが表示されます。 このポップオーバーで、「[ソースデータベース](/help/connections/home.md)」を選択し、「**[!UICONTROL 次へ]**」をクリックします。

![連合データベースを選択ポップオーバーが表示されます。](/help/data-modelling/assets/integrated/select-federated-database.png)

## スキーマを定義 {#define}

>[!CONTEXTUALHELP]
>id="platform_schemas_primarycompositekey"
>title="複合キー"
>abstract="複数のスキーマ列で構成されるスキーマキー。 複合キーとして使用する列にマークを付けます。"

連合データベースを選択した後、スキーマを定義できるようになりました。 「**[!UICONTROL データを追加]**」画面が表示されます。 このページでは、**[!UICONTROL テーブルを追加]**&#x200B;を選択して、スキーマに追加するテーブルを選択できます。

![&#x200B; データの追加画面で「テーブルを追加」ボタンが強調表示されます。](/help/data-modelling/assets/integrated/select-add-table.png)

**[!UICONTROL テーブルを選択]**&#x200B;ポップオーバーが表示されます。 このポップオーバーで、スキーマの作成に使用するテーブルを選択できます。

![テーブルを選択ポップオーバーが表示されます。](/help/data-modelling/assets/integrated/select-table.png){zoomable="yes"}

選択した各テーブルでは、選択した列を含むスキーマが生成されます。 各テーブルでは、スキーマのラベルの変更、説明の追加、フィールドラベルの名前の変更、フィールドラベルの表示の設定、スキーマのプライマリキーの選択ができます。

![選択したテーブルは、データの追加ページに表示されます。](/help/data-modelling/assets/integrated/tables-added.png){zoomable="yes"}

>[!NOTE]
>
>**[!UICONTROL 複合キー]**&#x200B;を選択し、使用するキーを1つだけ選択した場合、そのキーは標準スキーマのプライマリキーとして扱われます。

また、複数のスキーマ列で構成されるキーを作成できます。 「**[!UICONTROL 複合キー]**」を選択し、複合キーとして使用するキーをマークします。

![複合キーの切り替えとスキーマの両方が選択されています。](/help/data-modelling/assets/integrated/composite-key.png){zoomable="yes"}

設定が完了したら、「**[!UICONTROL 完了]**」を選択してスキーマの作成を完了します。

## スキーマの編集 {#schema-edit}

スキーマを編集するには、**スキーマ** ページで以前に作成したスキーマの横にある![省略記号アイコン &#x200B;](/help/assets/icons/more.png)を選択し、次に&#x200B;**[!UICONTROL 編集]**&#x200B;を選択します。

![&#x200B; スキーマを編集ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/edit-schema.png)

**[!UICONTROL スキーマを編集]** ウィンドウで、スキーマエディターを表示できます。 スキーマエディターの使用について詳しくは、[&#x200B; スキーマ UI ガイド &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas#customize-schema)を参照してください。

![&#x200B; スキーマエディターが表示されます。](/help/data-modelling/assets/integrated/schema-editor.png)

### 関係を編集 {#relationship-edit}

スキーマの関係を編集するには、スキーマエディター内の「**[!UICONTROL エンティティ図を表示]**」を選択します。

![&#x200B; 「エンティティ図を表示」ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/view-entity-diagram.png)

エンティティ図ページが表示されます。 このページでは、スキーマ間の関係を確立するためのリンクを作成できます。

![&#x200B; エンティティ図が表示されます。](/help/data-modelling/assets/integrated/entity-diagram.png)

リンクの作成について詳しくは、[&#x200B; データモデルの概要](/help/data-modelling/models.md#data-model-links)の「キャンバス表示」タブを参照してください。

## スキーマ内のデータのプレビュー {#schema-preview}

スキーマで表されるテーブル内のデータをプレビューするには、**[!UICONTROL データセット]** セクションに移動し、**[!UICONTROL 参照]**&#x200B;を選択します。

![&#x200B; データセットと「参照」ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/datasets-browse.png)

![3つのドット &#x200B;](/help/assets/icons/more.png)を選択し、続いて&#x200B;**[!UICONTROL データセットのプレビュー]**&#x200B;を選択すると、スキーマ内のデータのプレビューが表示されます。

![&#x200B; データセットのプレビューボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/select-preview-dataset.png)

## スキーマの更新 {#schema-refresh}

連合データベース内のテーブルは、更新、追加、削除できます。 その場合、最新の変更内容に合わせて Adobe Experience Platform のスキーマを更新する必要があります。 スキーマを更新するには、「**[!UICONTROL 詳細]**」ボタンを選択し、続いて「**[!UICONTROL 設定を管理]**」を選択します。

![設定を管理ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/manage-configuration.png)

**[!UICONTROL 設定を編集]** ポップオーバーが表示されます。 「**[!UICONTROL 更新]**」を選択して、スキーマを更新します。

![&#x200B; スキーマの更新ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/refresh-schema.png)

## スキーマの削除 {#schema-delete}

スキーマエディター内のスキーマを削除するには、**[!UICONTROL 詳細]**&#x200B;を選択し、その後&#x200B;**[!UICONTROL 削除]**&#x200B;を選択します。

![&#x200B; スキーマを削除ボタンがハイライト表示されます。](/help/data-modelling/assets/integrated/delete-schema.png)
