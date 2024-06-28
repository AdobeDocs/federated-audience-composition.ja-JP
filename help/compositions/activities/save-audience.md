---
audience: end-user
title: オーディエンスを保存アクティビティの使用
description: 分岐アクティビティの使用方法を学ぶ
source-git-commit: 05a023a7f7aab719f3771030a7ac8bba57e5bee3
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 67%

---

# オーディエンスを保存 {#save-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience"
>title="オーディエンスの保存"
>abstract="このアクティビティを使用すると、既存のオーディエンスを更新したり、コンポジションのアップストリームで計算された母集団から新しいオーディエンスを作成したりできます。 作成したオーディエンスはオーディエンスのリストに追加され、**オーディエンス**&#x200B;メニューから使用できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_outbound"
>title="アウトバウンドトランジションを生成"
>abstract="「**オーディエンスを保存**」アクティビティの後にトランジションを追加する場合は、このオプションを使用します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_save_audience_primary_identity"
>title="プライマリ ID フィールド"
>abstract="プロファイルに使用するプライマリ ID を選択します。"
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity#define-a-identity-field" text="詳しくは、Experience Platformドキュメントを参照してください。"


>[!CONTEXTUALHELP]
>id="dc_orchestration_saveaudience_namespace"
>title="ID 名前空間"
>abstract="プロファイルに使用する名前空間を選択します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces" text="詳しくは、Experience Platformドキュメントを参照してください。"



この **オーディエンスを保存** アクティビティを使用すると、コンポジションのアップストリームで計算された母集団から既存のオーディエンスを更新したり、新しいオーディエンスを作成したりできます。 作成したオーディエンスはアプリケーションオーディエンスのリストに追加され、**オーディエンス**&#x200B;メニューから使用できるようになります。

このアクティビティは、基本的に、母集団グループを再利用可能なオーディエンスに変換することで、同じ構成で計算を維持するために使用されます。 **オーディエンスを作成**&#x200B;アクティビティや&#x200B;**結合**&#x200B;アクティビティなどの他のターゲティングアクティビティに接続します。

## オーディエンスを保存アクティビティの設定 {#save-audience-configuration}

**オーディエンスを保存**&#x200B;アクティビティを設定するには、次の手順に従います。

1. を追加 **オーディエンスを保存** コンポジションに対するアクティビティ。

1. **モード**&#x200B;ドロップダウンで、実行するアクションを選択します。

   * **既存のオーディエンスを作成または更新**：**オーディエンスラベル**&#x200B;を定義します。オーディエンスが既に存在する場合は更新されます。存在しない場合は新しいオーディエンスが作成されます。

   * **既存のオーディエンスを更新**：既存のオーディエンスのリストから更新する&#x200B;**オーディエンス**&#x200B;を選択します。

1. 既存のオーディエンスに適用する&#x200B;**更新モード**&#x200B;を選択します。

   * **オーディエンスコンテンツを新しいデータに置換**：すべてのオーディエンスコンテンツを置き換えます。古いデータは失われます。「オーディエンスの保存」アクティビティのインバウンドトランジションからのデータのみが保持されます。このオプションを選択すると、オーディエンスの種類と、更新されたオーディエンスのターゲティングディメンションが削除されます。

   * **新しいデータでオーディエンスを入力**：古いオーディエンスコンテンツは保持され、オーディエンスを保存アクティビティのインバウンドトランジションのデータが追加されます。

1. **オーディエンスを保存**&#x200B;アクティビティの後にトランジションを追加する場合は、「**アウトバウンドトランジションを生成**」オプションをオンにします。

保存したオーディエンスの内容は、そのオーディエンスの詳細表示で利用できます。詳細表示は&#x200B;**オーディエンス**&#x200B;メニューからアクセスできます。このビューから使用可能な列は、のインバウンドトランジションの列に対応しています **オーディエンスを保存** アクティビティ。

<!--

## Example{#save-audience-example}

The following example illustrates a simple audience update from targeting. A scheduler is added to run the workflow once a month. A query recovers all the profiles subscribed to the different application services available. The **Save audience** activity updates the audience by deleting profiles that have unsubscribed from the service since the last workflow execution and by adding the newly subscribed profiles.
-->
