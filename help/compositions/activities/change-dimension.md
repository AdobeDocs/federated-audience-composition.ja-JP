---
audience: end-user
title: 「ディメンションを変更」アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
source-git-commit: 92d4a7cf1414ae74b2684619d295eca065a92ce2
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 56%

---

# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="補集合を生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にターゲティングディメンションを変更できます。データテンプレートと入力ディメンションに応じて軸を移動します。例えば、「契約」ディメンションから「クライアント」ディメンションに切り替えることができます。"

この **ディメンションを変更** アクティビティを使用すると、オーディエンスの作成時にターゲティングディメンションを変更できます。 データテンプレートと入力ディメンションに応じて軸を移動します。 <!--[Learn more on targeting dimensions](../../audience/about-recipients.md#targeting-dimensions)-->


## ディメンションを変更アクティビティの設定 {#configure}

**ディメンションを変更**&#x200B;アクティビティを設定するには、次の手順に従います。

1. を追加 **ディメンションを変更** コンポジションに対するアクティビティ。

1. **新しいターゲットディメンション**&#x200B;を定義します。ディメンションの変更時には、すべてのレコードが保持されます。

1. コンポジションを実行して結果を表示します。 ディメンションの変更アクティビティの前後でテーブル内のデータを比較し、コンポジションテーブルの構造を比較します。

<!--
## Example {#example}

In this example, we want to send an SMS delivery to all the profiles who have made a purchase. To do this, we first use a **[!UICONTROL Build audience]** activity linked to a custom "Purchase" targeting dimension to target all purchases that occurred.

We then use a **[!UICONTROL Change dimension]** activity to switch the workflow targeting dimension to "Recipients". This allows us to be able to target the recipients who match the query.
-->
