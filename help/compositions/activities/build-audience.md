---
audience: end-user
title: オーディエンスを作成アクティビティの使用
description: オーディエンスを作成アクティビティの使用方法を学ぶ
source-git-commit: b21306cefe6e9e66263012110a7f89f2d92b38a5
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 53%

---


# オーディエンスを作成 {#build-audience}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience"
>title="オーディエンスを作成アクティビティ"
>abstract="この **オーディエンスを作成** アクティビティを使用すると、コンポジションにエントリするオーディエンスを定義できます。"

この **オーディエンスを作成** アクティビティを使用すると、コンポジションにエントリするオーディエンスを定義できます。

オーディエンス母集団を定義するには、次の操作を実行します。

<!--* Select an existing audience, created as a list in the client console.-->
* Adobe Experience Platform オーディエンスを選択します。
* クエリモデラービルダーを使用してフィルタリング条件を定義および組み合わせて、新しいオーディエンスを作成します。

この **オーディエンスを作成** アクティビティは、コンポジションの最初または他のアクティビティの後に配置できます。 すべてのアクティビティは、の後に配置できます **オーディエンスを作成**.

## オーディエンスを作成アクティビティの設定 {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_audienceselector"
>title="オーディエンス"
>abstract="オーディエンスを選択します。"

**オーディエンスを作成**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **オーディエンスを作成**&#x200B;アクティビティを追加します。
1. ラベルを定義します。
1. **独自に作成**&#x200B;または&#x200B;**オーディエンスを読み取り**&#x200B;のオーディエンスタイプを定義します。
1. 以下のタブに示す手順に従って、オーディエンスを設定します。

>[!BEGINTABS]

>[!TAB 独自のクエリを作成]

独自のクエリを作成するには、次の手順に従います。

1. 「**独自のクエリを作成**」を選択します。
1. 「**ターゲティングディメンション**」を選択します。ターゲティングディメンションは、受信者、契約の受益者、オペレーター、サブスクライバーなど、ターゲットされる母集団を操作ごとに定義します。デフォルトでは、ターゲットが受信者から選択されます。<!-- [Learn more about targeting dimensions](../../audience/about-recipients.md#targeting-dimensions)-->
1. 「**続行**」をクリックします。
1. 新しいメールをデザインする際にオーディエンスを作成するのと同じ方法で、クエリモデラーを使用してクエリを定義します。 <!--[Learn how to work with the query modeler](../../query/query-modeler-overview.md)-->

>[!TAB オーディエンスの閲覧]

既存のオーディエンスを選択するには、次の手順に従います。

1. 「**オーディエンスを読み取り**」を選択します。
1. 「**続行**」をクリックします。
1. 新しい配信をデザインする際にオーディエンスを使用するのと同じ方法で、オーディエンスを選択します。 <!--Refer to this [section](../../audience/add-audience.md).-->

>[!ENDTABS]

<!--
## Examples{#build-audience-examples}

Here is an example of a workflow with two **Build audience** activities. The first one targets the poker players audience, followed by an email delivery. The second one targets the VIP clients audience, followed by an SMS delivery.

![](../assets/workflow-audience-example.png)
-->
