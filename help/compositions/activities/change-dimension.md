---
audience: end-user
title: 「ディメンションを変更」アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
source-git-commit: 4ba457f1dcd8b7997931a70d93a95f6a54c51cb5
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 29%

---


# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="補集合を生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にスキーマ（ターゲティングディメンションとも呼ばれます）を変更できます。 データテンプレートと入力スキーマに応じて軸を移動します。 例えば、「contracts」スキーマから「clients」スキーマに切り替えることができます。"

この **ディメンションを変更** アクティビティを使用すると、オーディエンスの作成時にスキーマ（ターゲティングディメンションとも呼ばれます）を変更できます。 データテンプレートと入力スキーマに応じて軸を移動します。

## ディメンションを変更アクティビティの設定 {#configure}

**ディメンションを変更**&#x200B;アクティビティを設定するには、次の手順に従います。

1. を追加 **ディメンションを変更** コンポジションに対するアクティビティ。

   ![](../assets/change-dimension.png)

1. の定義 **新しいスキーマ**. スキーマの変更時には、すべてのレコードが保持されます。

1. コンポジションを実行して結果を表示します。 テーブル内のデータを前後で比較 **ディメンションを変更** アクティビティを選択し、コンポジションテーブルの構造を比較します。

<!--
## Example {#example}

In this example, we want to send an SMS delivery to all the profiles who have made a purchase. To do this, we first use a **[!UICONTROL Build audience]** activity linked to a custom "Purchase" targeting dimension to target all purchases that occurred.

We then use a **[!UICONTROL Change dimension]** activity to switch the workflow targeting dimension to "Recipients". This allows us to be able to target the recipients who match the query.
-->



<!-- on parle de dimension, mais dans UI "schema", va rester comme ça ?-->