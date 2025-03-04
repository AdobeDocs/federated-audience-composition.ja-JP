---
audience: end-user
title: 分割アクティビティの使用
description: 分割アクティビティの使用方法について説明します
exl-id: 6346eef6-b164-40cf-9402-b5ff208af97f
source-git-commit: 65052ffcd8c70817aa428bea7f8b6baa0a49a1b0
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 100%

---

# 分割 {#split}

>[!CONTEXTUALHELP]
>id="dc_orchestration_split"
>title="分割アクティビティ"
>abstract="**分割**&#x200B;アクティビティを使用すると、フィルタリングルールや母集団サイズなどの様々な選択条件に基づいて、流入母集団を複数のサブセットにセグメント化できます。"

**分割**&#x200B;アクティビティを使用すると、フィルタリングルールや母集団サイズなどの様々な選択条件に基づいて、流入母集団を複数のサブセットにセグメント化できます。

## 分割アクティビティの設定 {#split-configuration}

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_segments"
>title="分割アクティビティのセグメント"
>abstract="入力母集団をセグメント化するのに必要な数のサブセットを追加します。<br/></br>「**分割**」アクティビティを実行すると、母集団はアクティビティに追加された順序で様々なサブセットに分割されます。 構成を開始する前に、矢印ボタンを使用して、必要に応じてサブセットを順番に並べ替えておきます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_filter"
>title="分割アクティビティのフィルター"
>abstract="サブセットにフィルタリング条件を適用するには、「**[!UICONTROL フィルターを作成]**」をクリックし、クエリモデラーを使用して目的のフィルタリングルールを設定します。例えば、データベースにメールアドレスが存在する入力母集団のプロファイルを含めます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_limit"
>title="分割アクティビティの制限"
>abstract="サブセットで選択するプロファイル数を制限するには、「**[!UICONTROL 制限を有効にする]**」オプションの切替スイッチをオンにし、含める母集団の数または割合を指定します。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_sorting"
>title="分割アクティビティの並べ替え"
>abstract="サブセットの母集団制限を設定する場合、特定のプロファイル属性に基づいて、選択したプロファイルを昇順または降順にランク付けできます。 これを行うには、「**並べ替えを有効にする**」オプションの切替スイッチをオンにします。 例えば、購入金額が最も高い上位 50 のプロファイルのみを含むようにサブセットを制限できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_complement"
>title="分割で補集合を生成"
>abstract="すべてのサブセットを設定したら、どのサブセットにも一致しなかった残りの母集団を選択し、追加のアウトバウンドトランジションに含めることができます。 これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_generatesubsets"
>title="同じテーブルにすべてのサブセットを生成"
>abstract="このオプションをオンに切り替えると、すべてのサブセットが 1 つの出力トランジションにグループ化されます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_emptytransition"
>title="空のトランジションをスキップ"
>abstract="「**[!UICONTROL 空のトランジションをスキップ]**」オプションをオンに切り替えると、入力母集団が空の場合に、このサブセットの出力トランジションが無効になります。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_split_enable_overlapping"
>title="出力母集団の重複を有効にする"
>abstract="「**[!UICONTROL 出力母集団の重複を有効にする]**」オプションにより、複数のサブセットに属している母集団を管理できます。このオプションを選択していない場合、サブセットの条件を複数満たす場合でも、複数の出力トランジションに受信者が表示されません。受信者は、一致した基準の 1 番目のタブのターゲットになります。チェックボックスをオンにすると、受信者がフィルター条件を満たす場合、複数のサブセットで受信者を検索できます。 "

**分割**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **分割**&#x200B;アクティビティを構成に追加します。

1. アクティビティ設定パネルが開き、デフォルトのサブセットが表示されます。「**セグメントを追加**」ボタンをクリックして、入力母集団をセグメント化する必要な数のサブセットを追加します。

   >[!IMPORTANT]
   >
   >「**分割**」アクティビティを実行すると、母集団はアクティビティに追加された順序で様々なサブセットに分割されます。例えば、最初のサブセットが初期母集団の 70％を回復した場合、次に追加されたサブセットの選択条件は残りの 30％にのみ適用されます。
   >
   >構成を開始する前に、必要に応じてサブセットを順番に並べ替えておきます。これを行うには、矢印ボタンを使用して、サブセットの位置を変更します。

1. サブセットを追加したら、アクティビティにはサブセットと同数の出力トランジションが表示されます。構成キャンバスで簡単に識別できるように、各サブセットのラベルを変更することを強くお勧めします。

   ![](../assets/split.png)

1. 各サブセットで入力母集団をフィルタリングする方法を設定します。それには、次の手順に従います。

   1. サブセットを展開して、そのプロパティを表示します。

      ![](../assets/split-subset.png)

   1. サブセットにフィルタリング条件を適用するには、「**[!UICONTROL フィルターを作成]**」をクリックし、クエリモデラーを使用して目的のフィルタリングルールを設定します。例えば、データベースにメールアドレスが存在する入力母集団のプロファイルを含めます。[詳しくは、クエリモデラーの操作方法を参照してください。](../../query/query-modeler-overview.md)

   1. サブセットで選択するプロファイル数を制限するには、「**[!UICONTROL 制限を有効にする]**」オプションの切替スイッチをオンにし、含める母集団の数または割合を指定します。

   1. 入力母集団が空の場合にトランジションを無効にするには、「**[!UICONTROL 空のトランジションをスキップ]**」オプションをオンに切り替えます。サブセットに一致するプロファイルがない場合、構成は次のアクティビティに移行しません。

   >[!NOTE]
   >
   >サブセットの母集団制限を設定する場合、特定のプロファイル属性に基づいて、選択したプロファイルを昇順または降順にランク付けできます。 これを行うには、「**[!UICONTROL 並べ替えを有効にする]**」オプションの切替スイッチをオンにします。 例えば、購入金額が最も高い上位 50 のプロファイルのみを含むようにサブセットを制限できます。

1. すべてのサブセットを設定したら、どのサブセットにも一致しなかった残りの母集団を選択し、追加のアウトバウンドトランジションに含めることができます。 これを行うには、「**[!UICONTROL 補集合を生成]**」オプションの切替スイッチをオンにします。

1. 「**[!UICONTROL 同じテーブル内のすべてのサブセットを生成]**」オプションを使用して、すべてのサブセットを 1 つの出力トランジションにグループ化できるようになりました。

1. 「**[!UICONTROL 出力母集団の重複を有効にする]**」オプションにより、複数のサブセットに属している母集団を管理できます。

   * このオプションを選択していない場合、サブセットの条件を複数満たす場合でも、複数の出力トランジションに受信者が表示されません。受信者は、一致した基準の 1 番目のタブのターゲットになります。
   * チェックボックスをオンにすると、受信者がフィルター条件を満たす場合、複数のサブセットで受信者を検索できます。ベストプラクティスは、排他的な条件を使用することです。

これでアクティビティが設定されました。実行時に、母集団はアクティビティに追加された順序で、様々なサブセットにセグメント化されます。

<!--
## Example{#split-example}

In the following example, the **[!UICONTROL Split]** activity is used to segment an audience into distinct subsets based on the communication channel that we want to use :

* **Subset 1 "push"**: This subset comprises all profiles who have installed our mobile application.
* **Subset 2 "sms"**: Mobile phone users: For the remaining population that did not fall into Subset 1, subset 2 applies a filtering rule to select profiles with mobile phones in the database.
* **Complement transition**: This transition captures all the remaining profiles that did not match Subset 1 or Subset 2. Specifically, it includes profiles who neither installed the mobile application nor have a mobile phone, such as users who haven't installed the mobile app or lack a registered mobile number.

![](../assets/workflow-split-example.png)
-->
