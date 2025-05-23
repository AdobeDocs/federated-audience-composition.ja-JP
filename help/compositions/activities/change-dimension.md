---
audience: end-user
title: ディメンションを変更アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
exl-id: e71017bd-6d2f-4ace-b2d9-cbfbb537d127
source-git-commit: 65052ffcd8c70817aa428bea7f8b6baa0a49a1b0
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="dc_orchestration_dimension_complement"
>title="補集合の生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。 これを行うには、「**[!UICONTROL 補集合を生成]**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にスキーマ（ターゲティングディメンションとも呼ばれる）を変更できます。データテンプレートと入力スキーマに応じて軸を移動します。例えば、「契約」スキーマから「クライアント」スキーマに切り替えることができます。"

**ディメンションを変更**&#x200B;アクティビティを使用すると、オーディエンスの作成時にスキーマ（ターゲティングディメンションとも呼ばれる）を変更できます。データテンプレートと入力スキーマに応じて軸を移動します。

## ディメンションを変更アクティビティの設定 {#configure}

**ディメンションを変更**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **ディメンションを変更**&#x200B;アクティビティを構成に追加します。

   ![](../assets/change-dimension.png)

1. **新規スキーマ**&#x200B;を定義します。スキーマの変更時に、すべてのレコードが保持されます。

1. 構成を実行して結果を表示します。**ディメンションを変更**&#x200B;アクティビティの前後のテーブル内のデータを比較して、構成テーブルの構造を比較します。

<!--
## Example {#example}

In this example, we want to send an SMS delivery to all the profiles who have made a purchase. To do this, we first use a **[!UICONTROL Build audience]** activity linked to a custom "Purchase" targeting dimension to target all purchases that occurred.

We then use a **[!UICONTROL Change dimension]** activity to switch the workflow targeting dimension to "Recipients". This allows us to be able to target the recipients who match the query.
-->

