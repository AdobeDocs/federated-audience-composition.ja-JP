---
title: AI アシスタントの概要
description: AI アシスタントを使用して、製品知識、運用上のインサイト、連合オーディエンス構成の作成などを行う方法を説明します。
exl-id: f7493a57-e42d-43f9-b20a-1b9b90477a74
source-git-commit: d3a97b5887778f910ca8f09f7cb8fa99360a612c
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 16%

---

# AI アシスタントの概要 {#ai-assistant}

AI アシスタントは、アドビの概念をナビゲートして理解するために設計されたユーザーインターフェイス機能です。 AI アシスタントを使用すると、Federated Audience Compositionを含むAdobe Experience Cloudの複数の製品における製品知識のユースケースをより深く理解できます。

>[!CAUTION]
>
>AI アシスタントを使用するには、Adobe Experience Cloud 生成 AI ユーザーガイドラインに同意する必要があります。 契約書について詳しくは、[AI アシスタント （レガシー）の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home){target="_blank"}を参照してください。

連合オーディエンス構成では、プロセスの様々な部分に関連するアドビの概念について説明する製品知識にアクセスできます。 AI アシスタントは、4種類のユースケースをサポートしています。**オープン ディスカバリー** （Experience League ドキュメントに基づいて製品コンセプトを調べる）、**ターゲットを絞った学習とトラブルシューティング** （特定の機能について質問する）、**運用上のインサイト** （連合オーディエンス構成内のオブジェクトについて質問する）、**連合オーディエンス構成の作成**。

## アクセス {#access}

AI アシスタントにアクセスするには、上部バーの「![&#x200B; AI アシスタント アイコン &#x200B;](/help/start/assets/ai-assistant/icon.png)」を選択します。 画面の右側のセクションに AI アシスタントが表示されます。 ![画像の代替テキストを使用](assets/do-not-localize/Smock_FullScreen_18_N.svg "展開アイコン ")を選択して、AI アシスタントウィンドウを展開できます。

![AI アシスタント アイコンがハイライト表示され、AI アシスタントへのアクセス方法が表示されます。](/help/start/assets/ai-assistant/access.png)

## AI アシスタントを使用 {#using}

AI アシスタントを開いたら、画面下部のフィールドに質問を入力し、Enterを押します。 質問に対する回答が表示されます。 親指を上げたり下げたりして、回答を評価できます。

![AI アシスタント内のサンプルの質問と回答が表示されます。](/help/start/assets/ai-assistant/sample-question-answer.png)

## 質問サンプル {#sample-questions}

次のクエリは、AI アシスタントに質問できる質問の種類を示しています。

| クエリタイプ | 質問サンプル |
| ---------- | --------------- |
| オープン検出 | <ul><li>連合オーディエンス構成とは何ですか？</li></ul> |
| ターゲット学習 | <ul><li>Snowflake フェデレーションデータベースアカウントを設定するにはどうすればよいですか？</li><li>連合構成を作成するにはどうすればよいですか？</li></ul> |
| 運用上のインサイト | <ul><li>サンドボックスにはいくつのフェデレーションデータベースがありますか？</li><li>過去30日間に作成したスキーマの数</li></ul> |
| 連合オーディエンス構成の作成 | <ul><li>英国在住の顧客を対象とした連合オーディエンスを作成します。</li></ul> |

さらに、AI アシスタントを使用して、連合オーディエンス構成を自律的に作成できます。

## オーディエンスの作成 {#create-audience}

AI アシスタントを使用して、自然言語プロンプトを使用した連合オーディエンス構成を作成できます。 AI アシスタントを使用してオーディエンスを作成する場合、AI アシスタントはプロンプトにもとづいたプランを作成し、AIを活用した自動化を使用してブラウザー内で実行します。

例えば、AI Assistantに「スキーマ CUSTOMERS_Tableを使用して英国在住のお客様の連合オーディエンスを作成する」と依頼した場合、AI Assistantは、連合コンポジションページに移動する手順、エージェントがコンポジションを作成する方法、完了後のオーディエンスを保存するなど、オーディエンスを作成するために実施する計画を示します。

![&#x200B; サンプルの質問と回答が表示されます。](/help/start/assets/ai-assistant/ask-create.png)

プランが正確に見える場合は、**[!UICONTROL 実行]**&#x200B;を選択して、エージェントがオートメーションを実行できるようにすることができます。 エージェントは、ブラウザー内で、Federated Audience Composition UI内でリクエストされたコンポジションを作成する手順を自律的に実行します。 任意の時点で自動化を停止する場合は、**[!UICONTROL 停止]**&#x200B;を選択します。

![&#x200B; プランが実行され、エージェントがプランを自律的に実行しています。](/help/start/assets/ai-assistant/execute-plan.png)

現在、オーディエンス作成スキルは次の追加機能をサポートしています。

- スケジューラー
   - 定期的なスケジュールで実行されるフェデレーションコンポジションを作成できます。 サポートされる値には、**Once**&#x200B;および&#x200B;**Daily**&#x200B;が含まれます。
- 重複の除外
   - データ調整中にフェデレーションデータレコードを重複排除できます

## 次の手順

AI アシスタントで達成できる目標の例、AI アシスタントの仕組みなど、AI アシスタントの詳細については、[AI アシスタントの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home){target="_blank"}を参照してください。

Federated Audience Compositionに関するInsightの運用上の質問の一覧については、[運用上のインサイトの節](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home#operational-insights){target="_blank"}を参照してください。
