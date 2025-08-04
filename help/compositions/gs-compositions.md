---
audience: end-user
title: 構成の基本を学ぶ
description: 構成の開始方法について説明します
exl-id: 92142d16-3483-4f6e-afde-9f88d5d7d1c4
source-git-commit: 59983bb7fd0f8886cc38bfcfc8d7005db4747ac0
workflow-type: ht
source-wordcount: '551'
ht-degree: 100%

---

# 構成の基本を学ぶ {#compositions}

>[!AVAILABILITY]
>
>構成にアクセスするには、次のいずれかの権限が必要です。
>
>-**連合構成の管理**
>>-**連合構成の表示**
>
>必要な権限について詳しくは、[アクセス制御ガイド](/help/governance-privacy-security/access-control.md)を参照してください。

連合オーディエンス構成では、構成を作成し、そこから視覚的なキャンバスで様々なアクティビティを活用してオーディエンスを作成できます。構成を作成した後、結果として生成されたオーディエンスは Adobe Experience Platform に保存され、Experience Platform の宛先や Adobe Journey Optimizer で顧客のターゲティングに活用できます。

![連合オーディエンス構成内にサンプルの構成ワークフローが表示されています。](assets/gs-compositions/composition-example.png){zoomable="yes"}{width="70%"}

## 構成へのアクセスと管理 {#access}

>[!CONTEXTUALHELP]
>id="dc_composition_list"
>title="構成"
>abstract="この画面では、構成の完全なリストにアクセスし、現在のステータス、前回／次回の実行日を確認して、新しい構成を作成できます。"

構成には、Adobe Experience Platform **[!UICONTROL オーディエンス]**&#x200B;メニューの「**[!UICONTROL 顧客]**」セクションにある「**[!UICONTROL 連合構成]**」タブからアクセスできます。

この画面から、新しい構成を作成したり、既存の構成にアクセスしたりできます。また、名前の横にある![省略記号](/help/assets/icons/more.png)ボタンを選択して、既存の構成を複製または削除することもできます。

また、名前、ステータス、作成者、最終変更日など、構成に関する情報も表示できます。

| ステータス | 説明 |
| ------ | ----------- |
| **[!UICONTROL ドラフト]** | 構成が作成され、保存されました。 |
| **[!UICONTROL 処理中]** | 構成が行われ、現在実行中です。 |
| **[!UICONTROL 停止]** | 構成の実行が完了し、停止しています。 |
| **[!UICONTROL 一時停止]** | 構成の実行が一時停止されています。 |
| **[!UICONTROL エラー]** | 構成の実行でエラーが発生しました。エラーに関する詳細情報を表示するには、構成を開き、ログにアクセスします。 |

構成を開始または停止する方法について詳しくは、[構成の開始と監視ガイド](./start-monitor-composition.md)を参照してください。

![使用可能な構成のリストが表示されています。](assets/gs-compositions/compositions-list.png){zoomable="yes"}{width="70%"}

リストを絞り込み、探している構成を見つけるには、リストを検索し、ステータスまたは最終処理日で構成をフィルタリングします。

また、列を追加または削除してリストをカスタマイズすることもできます。これを行うには、「**[!UICONTROL 列を設定]**」ボタンを選択し、目的の出力列を追加または削除します。

![構成の参照ページに追加できる使用可能な列のリストが表示されています。](assets/gs-compositions/compositions-columns.png){zoomable="yes"}{width="70%"}

### アクセスラベルの適用 {#access-labels}

特定の構成にアクセスラベルを適用するには、構成、「**[!UICONTROL アクセスを管理]**」の順に選択します。

![構成キャンバス内で「アクセスを管理」ボタンがハイライト表示されています。](assets/gs-compositions/select-manage-access.png){zoomable="yes"}{width="70%"}

**[!UICONTROL アクセスを管理]**&#x200B;ポップオーバーが表示されます。このページでは、該当するアクセスラベルとデータガバナンスラベルを構成に適用できます。

![「アクセスを管理」ポップオーバーが表示されています。構成に適用できる、すべてのラベルのリストが表示されています。](assets/gs-compositions/manage-access.png){zoomable="yes"}{width="70%"}

| ラベルタイプ | 説明 |
| ---------- | ----------- |
| 契約ラベル | 契約ラベル（「C」ラベル）は、契約上の義務を負うデータや、組織のデータガバナンスポリシーに関連するデータの分類に使用されます。 |
| ID ラベル | ID ラベル（「I」ラベル）は、個人を特定できるデータや、個人に連絡できるデータの分類に使用されます。 |
| 機密ラベル | 機密ラベル（「S」ラベル）は、ユーザーや組織が機密性が高いと見なすデータの分類に使用されます。 |
| パートナーエコシステムラベル | パートナーエコシステムラベルは、組織の外部のソースからのデータの分類に使用されます。 |

アクセスラベルとデータガバナンスラベルについて詳しくは、[データ使用ラベル用語集](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/reference)を参照してください。

## 次の手順

このガイドを参照することで、構成のアクセスラベルへのアクセス、管理、作成方法を学びました。オーディエンス全体の操作方法について詳しくは、[オーディエンスガイド](../start/audiences.md)を参照してください。
