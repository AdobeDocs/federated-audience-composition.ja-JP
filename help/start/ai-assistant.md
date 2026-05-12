---
title: AI アシスタントの概要
description: 製品知識、運用上のインサイト、連合オーディエンス構成の作成を含む、AI アシスタントの使用方法について説明します。
exl-id: f7493a57-e42d-43f9-b20a-1b9b90477a74
TQID: https://experienceleague.adobe.com/j-KXucjaZa4dNSjg5POqxh7KOSUHG5CnBkBLFA6rPVs
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: fda4d9d7b45833d7e080ae80f42b7ca5ce36b3ad
workflow-type: ht
source-wordcount: 651
ht-degree: 100%

---

# AI アシスタントの概要 {#ai-assistant}

AI アシスタントは、アドビの概念をナビゲートして理解するために設計されたユーザーインターフェイス機能です。 AI アシスタントを使用すると、連合オーディエンス構成を含む Adobe Experience Cloud 全体の複数の製品の製品知識ユースケースをより深く理解できます。

>[!CAUTION]
>
>AI アシスタントを使用するには、Adobe Experience Cloud 生成 AI ユーザーガイドラインに同意する必要があります。 契約について詳しくは、[AI アシスタント（レガシー）の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home){target="_blank"}を参照してください。

連合オーディエンス構成では、プロセスの様々な部分に関連するアドビの概念について説明する製品知識にアクセスできます。 AI アシスタントは、**オープン検出**（Experience League ドキュメントに基づいて製品の概念を探索）、**ターゲット学習とトラブルシューティング**（特定の特長と機能について質問）、**運用上のインサイト**（連合オーディエンス構成内のオブジェクトについて質問）、**連合オーディエンス構成の作成**&#x200B;の 4 つのタイプのユースケースをサポートしています。

## アクセス {#access}

AI アシスタントにアクセスするには、上部のバーにある ![AI アシスタントアイコン](/help/start/assets/ai-assistant/icon.png) を選択します。 画面の右側のセクションに AI アシスタントが表示されます。 ![詳細画像の代替テキスト](assets/do-not-localize/Smock_FullScreen_18_N.svg "展開アイコン") を選択して、AI アシスタントウィンドウを展開できます。

![AI アシスタントへのアクセス方法を示す、AI アシスタントアイコンがハイライト表示されています。](/help/start/assets/ai-assistant/access.png)

## AI アシスタントの使用 {#using}

AI アシスタントを開いたら、画面下部にあるフィールドに質問を入力し、Enter キーを押します。質問に対する回答が表示されます。サムアップまたはサムダウンを使用して回答を評価できます。

![AI アシスタント内のサンプルの質問と回答が表示されます。](/help/start/assets/ai-assistant/sample-question-answer.png)

## 質問サンプル {#sample-questions}

次のクエリに、AI アシスタントに質問できるタイプを示します。

| クエリタイプ | 質問サンプル |
| ---------- | --------------- |
| オープン検出 | <ul><li>連合オーディエンス構成とは何ですか？</li></ul> |
| ターゲット学習 | <ul><li>Snowflake 連合データベースアカウントを設定するにはどうすればよいですか？</li><li>連合構成を作成するにはどうすればよいですか？</li></ul> |
| 運用上のインサイト | <ul><li>サンドボックスにある連合データベースはいくつですか？</li><li>過去 30 日間に作成したスキーマの数</li></ul> |
| 連合オーディエンス構成の作成 | <ul><li>英国在住の顧客の連合オーディエンスを作成します。</li></ul> |

また、AI アシスタントを使用して、連合オーディエンス構成を自律的に作成できます。

## オーディエンスの作成 {#create-audience}

AI アシスタントを使用して、自然言語プロンプトを使用した連合オーディエンス構成を作成できます。AI アシスタントを使用してオーディエンスを作成する際、AI アシスタントはプロンプトに基づいてプランを作成し、AI を活用した自動処理を使用してブラウザー内で実行します。

例えば、AI アシスタントに「スキーマ CUSTOMERS_Table を使用して、英国在住の顧客の連合オーディエンスを作成してください」と質問した場合、AI アシスタントは、連合構成ページへの移動、エージェントが構成を作成する仕組み、完了後のオーディエンスの保存などの手順を含む、オーディエンスを作成するために実行するプランをレイアウトします。

![サンプルの質問と回答が表示されます。](/help/start/assets/ai-assistant/ask-create.png)

プランが正確に見える場合は、「**[!UICONTROL 実行]**」を選択して、エージェントに自動処理を実行させることができます。エージェントは、ブラウザー内で、連合オーディエンス構成 UI 内でリクエストされた構成を作成する手順を自律的に実行します。任意の時点で自動処理を停止する場合は、「**[!UICONTROL 停止]**」を選択します。

![プランが実行され、エージェントがプランを自律的に実行しています。](/help/start/assets/ai-assistant/execute-plan.png)

現在、オーディエンス作成スキルは、次の追加機能をサポートしています。

- スケジューラー
   - 繰り返しスケジュールで実行される連合構成を作成できます。サポートされる値には、**1 回**&#x200B;および&#x200B;**毎日**&#x200B;が含まれます。
- 重複の除外
   - データ紐付け中に連合データレコードを重複排除できます

## 次の手順

AI アシスタントで達成できる目標の例、AI アシスタントの仕組みを含む AI アシスタントについて詳しくは、[AI アシスタントの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home){target="_blank"}を参照してください。

連合オーディエンス構成について質問できる運用上のインサイトの質問の完全なリストについて詳しくは、[運用上のインサイトの節](https://experienceleague.adobe.com/ja/docs/experience-platform/ai-assistant/home#operational-insights){target="_blank"}を参照してください。
