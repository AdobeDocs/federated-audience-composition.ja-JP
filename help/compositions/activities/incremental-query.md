---
audience: end-user
title: 増分クエリアクティビティの使用
description: 増分クエリアクティビティの使用方法について説明します
hide: true
hidefromtoc: true
source-git-commit: 5fe470ce83a5c3d3df7717bc1203849d99edf430
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 増分クエリ {#incremental-query}

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery"
>title="増分クエリ"
>abstract="「**増分クエリ**」アクティビティを使用すると、クエリモデラーを使用してデータベースにクエリを実行できます。 このアクティビティが実行されるたびに、以前の実行結果が除外されます。 これにより、新しい要素だけをターゲットにすることができます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery_history"
>title="増分処理クエリ履歴"
>abstract="増分処理クエリ履歴"

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalquery_processeddata"
>title="増分クエリの処理済みデータ"
>abstract="増分クエリの処理済みデータ"

**増分クエリ**&#x200B;アクティビティを使用すると、スケジュールに基づいてデータベースに対してクエリを実行できます。このアクティビティが実行されるたびに、以前の実行結果が除外されます。 これにより、新しい要素だけをターゲットにすることができます。

**[!UICONTROL 増分クエリ]**&#x200B;アクティビティは、次のような様々な用途に使用できます。

* 個人をセグメント化して、メッセージやオーディエンスなどのターゲットを定義する。
* データをエクスポートする。例えば、アクティビティを使用して、定期的にファイルに新規ログをエクスポートできます。この機能は、外部レポートや BI ツールでログデータを使用する場合に役に立ちます。

以前の実行で既にターゲットになっている母集団は、構成に保存されます。つまり、同じテンプレートから開始された 2 つの構成は同じログを共有しません。一方、同じ構成の同じ増分クエリに基づく 2 つのタスクは、同じログを使用します。

実行中のいずれかの増分クエリの結果が 0 と等しい場合、プログラムされた次回のクエリの実行まで、構成は一時停止されます。このため、増分処理クエリに続くトランザクションとアクティビティが、次回の実行前に処理されることはありません。

## 増分クエリアクティビティの設定 {#incremental-query-configuration}

**増分クエリ**&#x200B;アクティビティを設定するには、次の手順に従います。

1. 構成に&#x200B;**増分クエリ**&#x200B;アクティビティを追加します。

1. 「**[!UICONTROL オーディエンス]**」セクションで「**ターゲティングディメンション**」を選択し、「**[!UICONTROL 続行]**」をクリックします。

   ターゲティングディメンションは、受信者、契約の受益者、オペレーター、サブスクライバーなど、ターゲットされる母集団を操作ごとに定義します。デフォルトでは、ターゲットが受信者から選択されます。<!--[Learn more about targeting dimensions](../../audience/about-recipients.md#targeting-dimensions)-->

1. 新しいメールをデザインする際にオーディエンスを作成するのと同じ方法で、クエリモデラーを使用してクエリを定義します。[詳しくは、クエリモデラーの操作方法を参照してください。](../../query/query-modeler-overview.md)

1. 「**[!UICONTROL 処理済みのデータ]**」セクションで、使用する増分モードを選択します。

   * **[!UICONTROL 以前の実行結果を除外]**：アクティビティを実行するたびに、前回の実行結果が除外されます。

     以前の実行でターゲットになった受信者は、ターゲットとなった日からの経過日数が最大に達するまでログに記録することができます。これを行うには、「**[!UICONTROL 履歴（日数）]**」フィールドを使用します。値がゼロの場合、受信者がログからパージされることはありません。

   * **[!UICONTROL 日付フィールドを使用]**：このオプションを使用すると、特定の日付フィールドに基づいて、以前の実行の結果を除外できます。それには、選択したターゲティングディメンションで使用できる属性のリストから目的の日付フィールドを選択します。構成の次回の実行時には、最後の実行日より後に変更または作成されたデータのみが取得されます。

     構成を最初に実行した後、「**[!UICONTROL 最終実行日]**」フィールドが使用可能になります。このフィールドで次の実行の日付が指定され、構成を実行するたびに自動的に更新されます。それでも、必要に応じて手動で別の値を入力すれば、この値を上書きすることはできます。

   >[!NOTE]
   >
   >**[!UICONTROL 日付フィールドを使用]**&#x200B;モードでは、選択された日付フィールドに応じて、より柔軟な指定が可能です。例えば、指定したフィールドが変更日に対応している場合、日付フィールドモードでは、最後に更新されたデータを取得できます。一方、他のモードでは、構成の最後の実行以降に変更があった場合でも、前回の実行でターゲットになったレコードは単純に除外されます。

<!--

## Example {#incremental-query-example}

The following example shows the configuration of a workflow which filters every week the profiles in the Adobe Campaign database that are subscribed to the Yoga Newsletter service, to send them a welcome email.

![](../assets/incremental-query-example.png)

The workflow is made up of the following elements:

* A **[!UICONTROL Scheduler]** activity, to execute the workflow every Monday at 6 am.
* An **[!UICONTROL Incremental query]** activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.
* An **[!UICONTROL Email delivery]** activity.
-->
