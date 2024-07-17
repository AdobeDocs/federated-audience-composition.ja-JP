---
audience: end-user
title: オーディエンスを保存アクティビティの使用
description: オーディエンスを保存アクティビティの使用方法を学ぶ
badge: label="限定提供" type="Informative"
source-git-commit: 7a3d03543f6f903c3f7f66299b600807cf15de5e
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 44%

---


# オーディエンスを保存 {#save-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience"
>title="オーディエンスの保存"
>abstract="このアクティビティを使用すると、既存のオーディエンスを更新したり、構成の上流で計算された母集団から新しいオーディエンスを作成したりすることができます。 作成したオーディエンスはオーディエンスのリストに追加され、**オーディエンス**&#x200B;メニューから使用できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_outbound"
>title="アウトバウンドトランジションを生成"
>abstract="「**オーディエンスを保存**」アクティビティの後にトランジションを追加する場合は、このオプションを使用します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience_primary_identity"
>title="プライマリ ID フィールド"
>abstract="プロファイルに使用するプライマリ ID を選択します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/fields/identity#define-a-identity-field" text="詳しくは、Experience Platform のドキュメントを参照してください"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_namespace"
>title="ID 名前空間"
>abstract="プロファイルに使用する名前空間を選択します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces" text="詳しくは、Experience Platform のドキュメントを参照してください"

**オーディエンスを保存** アクティビティを使用すると、既存のオーディエンスを更新したり、コンポジションのアップストリームで計算された母集団から新しいオーディエンスを作成したりできます。 作成したオーディエンスはアプリケーションオーディエンスのリストに追加され、**オーディエンス**&#x200B;メニューから使用できるようになります。

このアクティビティは、基本的に、母集団グループを再利用可能なオーディエンスに変換することで、同じ構成で計算を維持するために使用されます。 **オーディエンスを作成**&#x200B;アクティビティや&#x200B;**結合**&#x200B;アクティビティなどの他のターゲティングアクティビティに接続します。

## オーディエンスを保存アクティビティの設定 {#save-audience-configuration}

**オーディエンスを保存**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **オーディエンスを保存** アクティビティをコンポジションに追加します。

   ![](../assets/save-audience.png)

1. 作成するオーディエンスのラベルを指定します。

1. 「**オーディエンスマッピングを追加**」をクリックし、「ソース」フィールドと「ターゲットオーディエンス」フィールドを選択します。

   * **Source オーディエンスフィールド**:
   * **ターゲットオーディエンスフィールド**:

   操作を繰り返して、必要な数のオーディエンスマッピングを追加します。

1. データベース内のターゲットプロファイルを識別するために使用するプライマリ ID と名前空間を選択します。

   * **プライマリ ID フィールド**: プロファイルの識別に使用するフィールドを選択します。 例えば、メールアドレスや電話番号などです。
   * **ID 名前空間**：プロファイルの識別に使用する名前空間、つまり ID キーとして使用するデータのタイプを選択します。 例えば、メールアドレスをプライマリ ID フィールドとして選択した場合は、ID 名前空間 **メール** を選択する必要があります。 一意の識別子が電話番号の場合は、ID 名前空間の&#x200B;**電話**&#x200B;を選択する必要があります。

コンポジションを実行すると、結果のオーディエンスがAdobe Experience Platform <!-- to check--> に保存され、**オーディエンス** メニューでアクセスできるようになります。

<!--

## Example{#save-audience-example}

The following example illustrates a simple audience update from targeting. A scheduler is added to run the workflow once a month. A query recovers all the profiles subscribed to the different application services available. The **Save audience** activity updates the audience by deleting profiles that have unsubscribed from the service since the last workflow execution and by adding the newly subscribed profiles.
-->
