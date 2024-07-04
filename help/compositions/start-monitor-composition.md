---
audience: end-user
title: コンポジションの作成
description: コンポジションの作成方法を説明します
source-git-commit: 4a73702c99762a5e9ab73485fa46916b9c28fcc3
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 29%

---


# コンポジションの開始と監視 {#start-monitor}

コンポジションを作成し、キャンバスで実行するタスクを設計したら、コンポジションを起動して、その実行状況を監視できます。

## コンポジションを開始 {#start}

コンポジションを開始するには、 **[!UICONTROL 開始]** ボタンをクリックします。 コンポジションが実行されている場合、コンポジションの最後に達するまで、キャンバス内の各アクティビティが順番に実行されます。

視覚的なフローを使用すると、ターゲットプロファイルの進行状況をリアルタイムで追跡できます。これにより、各アクティビティのステータスと、アクティビティ間で移行中のプロファイルの数をすばやく識別できます。

![](assets/composition-visual-flow.png)

## コンポジション切り替え {#transitions}

コンポジションでは、トランジションを通じてあるアクティビティから別のアクティビティに転送されたデータが、一時的なワークテーブルに保存されます。 このデータは、トランジションごとに表示できます。これを行うには、トランジションを選択して、画面の右側でそのプロパティを開きます。

* 「**[!UICONTROL スキーマをプレビュー]**」をクリックして、作業用テーブルのスキーマを表示します。
* 「**[!UICONTROL 結果をプレビュー]**」をクリックして、選択したトランジションで転送されたデータを視覚化します。

![](assets/transition-preview.png)

## アクティビティ実行を監視 {#activities}

各アクティビティボックスの右上隅にある視覚的な指標を使用すると、アクティビティの実行を確認できます。

| 視覚的な指標 | 説明 |
|-----|------------|
| ![](assets/activity-status-pending.png){zoomable="yes"}{width="70%"} | このアクティビティは現在実行中です。 |
| ![](assets/activity-status-orange.png){zoomable="yes"}{width="70%"} | このアクティビティには注意が必要です。これには、配信の送信確認や、必要なアクションの実行が含まれる場合があります。 |
| ![](assets/activity-status-red.png){zoomable="yes"}{width="70%"} | アクティビティでエラーが発生しました。この問題を解決するには、コンポジションのログを開いて詳細を確認します。 |
| ![](assets/activity-status-green.png){zoomable="yes"}{width="70%"} | アクティビティが正常に実行されました。 |

## ログとタスクを監視 {#logs-tasks}

コンポジションのログとタスクを監視することは、コンポジションを分析し、正しく実行されていることを確認するための重要な手順です。 これらには、からアクセスできます **[!UICONTROL ログ]** ボタンは、アクションツールバーと各アクティビティのプロパティパネルで使用できます。

![](assets/logs-button.png)

この **[!UICONTROL コンポジションログとタスク]** 画面には、コンポジションの実行履歴が表示され、すべてのユーザーのアクションと発生したエラーが記録されます。

<!-- à confirmer, pas trouvé dans les options = The workflow history is saved for the duration specified in the workflow execution options. During this duration, all the messages are therefore saved, even after a restart. If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.-->

履歴は、以下のように複数のタブに整理されています。

* この **[!UICONTROL ログ]** タブには、すべてのコンポジションアクティビティの実行履歴が表示されます。 実行された操作と実行エラーのインデックスを時系列順に作成します。
* この **[!UICONTROL タスク]** タブには、アクティビティの実行順序の詳細が表示されます。 各タスクの最後にある「」ボタンを使用すると、アクティビティを通じて渡されるイベント変数をリストできます。
* この **[!UICONTROL 変数]** tab キーを押すと、コンポジションで渡されたすべての変数がリストされます。 コンポジションキャンバスからのみログおよびタスクにアクセスする場合にのみ使用できます。 アクティビティのプロパティペインからログにアクセスする際に、この機能が使用できるようになりました。  <!-- à confirmer-->

![](assets/logs-tasks.png)

すべてのタブで、表示される列とその順序を選択し、フィルターを適用し、検索フィールドを使用して目的の情報をすばやく見つけることができます。

## コンポジション実行コマンド {#execution-commands}

右上隅のアクションバーには、コンポジションの実行を管理できるコマンドが用意されています。

![](assets/execution-actions.png)

使用可能なアクションは次のとおりです。

* **開始**：コンポジションの実行を開始し、実行が **処理中** ステータス。 コンポジションが開始され、初期のアクティビティがアクティブ化されます。

* **[!UICONTROL 再開]**：一時停止したコンポジションの実行を再開します。 作文は次の要素を取り入れます **処理中** ステータス。

* **[!UICONTROL 一時停止]** コンポジションの実行。その後、 **一時停止** ステータス。 ワークフローが再開されるまでは新しいアクティビティは有効化されません。ただし、進行中の操作は中断されません。

* **[!UICONTROL 停止]** 実行中のコンポジションで、 **完了** ステータス。 進行中の操作は、可能であれば中断されます。コンポジションを停止した場所から再開することはできません。

* **再起動**：コンポジションを停止してから再開します。 ほとんどの場合、停止には一定の時間がかかり、 **開始** ボタンは、停止が有効な場合にのみ使用できます。