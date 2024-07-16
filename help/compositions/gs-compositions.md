---
audience: end-user
title: 構成の基本を学ぶ
description: コンポジションの開始方法を説明します
source-git-commit: 0d6930b15be5013b57b8859dd3d21a5d3367ecae
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 14%

---

# 構成の基本を学ぶ {#compositions}

## コンポジションとは {#what}

Adobeデータコンポジションを使用すると、様々なアクティビティ（分割、除外など）をビジュアルキャンバスに活用してオーディエンスを作成できるコンポジションを作成できます。 完了すると、結果オーディエンスが既存のオーディエンスと共にAdobe Experience Platformに保存され、Journey Optimizerなどの宛先で活用して顧客をターゲットできます。

![](assets/composition-example.png)

## 構成へのアクセスと管理 {#access}

>[!CONTEXTUALHELP]
>id="dc_composition_list"
>title="構成"
>abstract="この画面では、構成の完全なリストにアクセスし、現在のステータス、前回／次回の実行日を確認して、新しい構成を作成できます。"

コンポジションには、Adobe Experience Platformの **[!UICONTROL オーディエンス]** メニューの「**フェデレーテッド コンポジション**」タブからアクセスできます。

この画面から新しいコンポジションを作成し、既存のコンポジションにアクセスできます。 名前の横にある省略記号ボタンをクリックして、既存のコンポジションを複製または削除することもできます。

![](assets/compositions-list.png)

リストを絞り込んで探しているコンポジションを簡単に見つけるには、リストを検索し、ステータスまたは前回の処理日でコンポジションをフィルタリングします。

列を追加または削除してリストをカスタマイズすることもできます。 これを行うには、**列を設定** ボタンをクリックし、目的の出力列を追加または削除します。

![](assets/compositions-columns.png)

## コンポジションのステータス {#status}

コンポジションには複数のステータスがあります。

* **[!UICONTROL ドラフト]**：コンポジションが作成され、保存されました。
* **[!UICONTROL 処理中]**：コンポジションが実行され、現在実行中です。
* **[!UICONTROL 停止]**：コンポジションの実行が停止しました。
* **[!UICONTROL 一時停止]**：コンポジションの実行が一時停止されました。
* **[!UICONTROL エラー]**：コンポジション実行でエラーが発生しました。 コンポジションを開き、ログとタスクにアクセスしてエラーを特定し解決します。

コンポジションの開始および監視方法について詳しくは、[ この節 ](../compositions/start-monitor-composition.md) を参照してください。