---
audience: end-user
title: コンポジションの基本を学ぶ
description: コンポジションの開始方法を説明します
source-git-commit: 8f4242b02f2cd135bf4adc3a69db08fe1f812e4e
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 16%

---

# コンポジションの基本を学ぶ {#compositions}

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_properties"
>title="構成のプロパティ"
>abstract="このセクションでは、コンポジションの作成時にもアクセスできる一般的なコンポジションプロパティを提供します。"

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_segmentation"
>title="構成のセグメント化"
>abstract="デフォルトでは、コンポジションの最後の実行のワークテーブルのみが保持されます。 このオプションを有効にすると、テスト目的で作業用テーブルを保持できます。 必ず使用してください **のみ** 開発環境またはステージング環境で実行します。 実稼動環境では絶対にオンにしないでください。"




## コンポジションとは何ですか？ {#compositions-start}


>[!CONTEXTUALHELP]
>id="dc_workflow_list"
>title="構成"
>abstract="この画面では、コンポジションの完全なリストにアクセスし、現在のステータス、最後/次回の実行日を確認して、新しいコンポジションを作成できます。"


## エラー管理の設定  {#error-settings}

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_error"
>title="エラー管理の設定"
>abstract="この節では、実行中にエラーを管理する方法を定義できます。 プロセスを一時停止、一定数のエラーを無視、コンポジションの実行を停止のいずれかを選択できます。"

* **[!UICONTROL エラー管理]**：このフィールドでは、コンポジションアクティビティでエラーが発生した場合に行うアクションを定義できます。
次の 3 つのオプションが使用可能です。

   * **[!UICONTROL プロセスを中断]**：コンポジションは自動的に一時停止され、ステータスが次のように変更されます **[!UICONTROL 失敗]**. 問題が解決したら、を使用してコンポジションを再開します **[!UICONTROL 再開]** ボタン。
   * **[!UICONTROL 無視]**：エラーをトリガーしたタスクのステータスが「」に変わります **[!UICONTROL 失敗]**&#x200B;ただし、コンポジションは **[!UICONTROL 開始日時]** ステータス。
   * **[!UICONTROL プロセスを中止]**：コンポジションは自動的に停止し、ステータスが次のように変わります **[!UICONTROL 失敗]**. 問題が解決したら、を使用してコンポジションを再開します **[!UICONTROL 開始]** ボタン。

* **[!UICONTROL 連続エラー]**：このフィールドは、「**[!UICONTROL エラーの場合]**」フィールドで「**[!UICONTROL 無視]**」の値が選択されたときに有効になります。プロセスを停止するまでに無視するエラーの数を指定できます。この数に達すると、コンポジションのステータスが次のように変わります **[!UICONTROL 失敗]**. このフィールドの値が 0 の場合、エラーの数にかかわらず、コンポジションは停止しません。
