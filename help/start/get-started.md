---
title: Experience Platform 連合オーディエンス構成の基本を学ぶ
description: アドビの連合オーディエンス構成の概要と Adobe Experience Platform での使用方法について説明します
exl-id: 43464aea-9c1d-4f1f-859f-82f209f350b7
source-git-commit: bb3e01b11d34568b61fdd98eedaa59af5267fd87
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 76%

---

# 連合オーディエンス構成の基本を学ぶ {#gs-fac}

連合オーディエンス構成は、[Adobe Real-Time Customer Data Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/home){target="_blank"} および [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} 環境で使用できます。これを使用すると、サードパーティのデータウェアハウスからオーディエンスを作成して強化し、このオーディエンスを Adobe Experience Platform に読み込むことができます。連合オーディエンス構成は、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer 内でエンタープライズデータウェアハウスを直接接続し、データウェアハウスのテーブルに対してクエリを実行するための簡単で強力なソリューションを提供します。

アドビの連合オーディエンス構成は、Adobe Experience Platform アプリのユーザーが、Amazon Redshift、Azure Synapse Analytics などのデータウェアハウスやクラウドストレージプラットフォームに保存されている顧客データにアクセスするのに役立ちます。顧客データを複数のデータウェアハウスに保存し、複製せずに即座にアクセスできるようになります。サポートされているプラットフォームについて詳しくは、[このページ](../connections/federated-db.md#supported-db)を参照してください。

>[!INFO]
>
>連合オーディエンス構成を使用してオーディエンスを作成する方法について詳しくは、この[ステップバイステップガイド](https://experienceleague.adobe.com/ja/docs/platform-learn/tutorial-comprehensive-technical/datacollection/module13/fac)を参照してください。

## 機能 {#rn-capabilities}

連合オーディエンス構成は、オーディエンスのキュレーションとアクティベーションに対する包括的なアプローチを用いて、Real-time CDP と Journey Optimizer の価値を拡張します。

* 重要なウェアハウスベースのデータセットへのアクセスを拡張して、価値の高いオーディエンスを作成：既存のデータウェアハウスを主要なレコードシステムとして活用しながら、クラス最高のアプリケーションを活用して優れた顧客体験を実現します。

* エンゲージメントのユースケースを強化するための包括的なサポート：連合オーディエンス構成は、Real-time CDP または Journey Optimizer と組み合わせることで、連合オーディエンスによるブランド主導のパーソナライズされたエクスペリエンスをサポートし、リアルタイムイベントによってトリガーされる瞬間的なエクスペリエンスを、ユーザー属性と組み合わせて提供し、チーム全体のユースケース要件を満たします。

* データの移動と重複を最小化：基になるデータをコピーせずに、エンタープライズデータウェアハウスにあるデータセットからオーディエンスを作成し、実用的なマーケティングプロファイルとオーディエンスを管理します。

* 1 つのシステムをエクスペリエンス駆動型ワークフローに利用：Adobe Experience Platform で取得した連合オーディエンスをキュレーションし、すべてのチャネルにわたってアウトバウンドエクスペリエンスを調整します。

* B2C および B2B CDP のお客様は、連合オーディエンス構成を活用し、サポートされているエンタープライズデータウェアハウスからのデータを統合して、個人ベースのオーディエンスを作成できるようになりました。さらに、エンタープライズデータウェアハウスで使用可能な関連属性を組み込むことで、既存の AEP の個人ベースのオーディエンスのエンリッチメントを行い、オーディエンスプロファイルを強化して、よりパーソナライズされ、ターゲットを絞ったエンゲージメントを実現できます。

## ユースケース {#use-cases}

Federated Audience Composition では、オーディエンスの作成、オーディエンスのエンリッチメント、顧客プロファイルのエンリッチメントという **3 つの** ユースケースのカテゴリをサポートしています。

* オーディエンスの作成：データウェアハウスからオーディエンスを作成し、マーケターに適したドラッグ&amp;ドロップユーザーインターフェイスを介して、オーディエンスをExperience Platformに統合し、Real-Time CDPまたはJourney Optimizerで使用できるようにします。 その結果、機密の基になるデータをコピーしたり、既存のデータを複製したりすることなく、データウェアハウスに対してクエリを実行できます。
   * **例：** 過去の購入者の取引履歴データを使用して、それらの取引をExperience Platformにコピーせずに、価値の高いオーディエンスをウェアハウスに作成します。

* オーディエンスの強化：データウェアハウスから追加のデータセットを使用し、この情報をオーディエンスにオーバーレイすることで、Experience Platformの既存のオーディエンスに詳細を追加できます。基になるデータをExperience Platformにコピーする必要はありません。 オーディエンスのエンリッチメントを使用すると、エンリッチメントされたオーディエンスで改善されたパーソナライゼーションを提供できます。
   * **例：** 価値の高い過去の購入者の Federated Audience Composition オーディエンスを使用して、買い物かごの放棄を行ったExperience Platform オーディエンスを強化し、ターゲットを絞ったオファーを提供します。

* プロファイルのエンリッチメント：データウェアハウスから個々の顧客属性を選択して、Experience Platform プロファイルを強化できます。 これらのプロファイルに連合データを追加することで、インバウンド顧客シグナルによってトリガーされるインモーメントエクスペリエンスをより適切に活用できます。
   * **例：** フェデレーションされたオーディエンスの情報を使用してExperience Platform プロファイルを強化します。 価値の高い過去の購入者 federated audience に属するサイト訪問者に、オンサイト行動によってトリガーされるターゲットオファーをマーケティングできるようになりました。

![図](assets/fac-use-cases.png){zoomable="yes"}{width="75%" align="center"}

Federated Audience Composition のユースケースについて詳しくは、[Federated Audience Composition ホワイトペーパー ](https://business.adobe.com/resources/sdk/flexibly-access-enterprise-data-with-federated-audience-composition.html) を参照してください。

## 主な手順 {#gs-steps}

アドビの連合オーディエンス構成を使用すると、取り込みプロセスなしで、データベースから直接 Adobe Experience Platform オーディエンスを作成および更新できます。

<!--![diagram](assets/steps-diagram.png){zoomable="yes"}{width="85%" align="center"}-->

主な手順：

1. **データ統合**：様々なソースからデータを統合し、統合されたデータセットに結合します。Adobe Experience Platform アプリとエンタープライズデータウェアハウスを接続する方法、サポートされているデータベース、およびこれらの設定方法について詳しくは、[この節](../connections/federated-db.md)を参照してください。

1. **データモデリング**：データの構造、関係、制約を定義するデータモデルとスキーマをデザインおよび作成します。スキーマについて詳しくは、[このページ](../customer/schemas.md)を参照してください。データモデルのリンクを作成する方法について詳しくは、[このページ](../data-management/gs-models.md)を参照してください。

1. **データ変換**：データ操作テクニックを適用して、データ要素の形式、構造、値を変更し、特定の分析やアプリケーションに対して互換性を持たせたり、適合させたりします。

1. **データ使用**：オーディエンスを作成、調整および構築します。オーディエンスの構成方法について詳しくは、[このページ](../compositions/gs-compositions.md)を参照してください。また、Adobe Experience Platform オーディエンスポータルと宛先を通じて、既存のオーディエンスを更新または再利用することもできます。詳しくは、[このページ](../connections/destinations.md)を参照してください。

>[!NOTE]
>
>コンポジションを実行すると、結果のオーディエンスが外部オーディエンスとしてAdobe Experience Platformに保存され、Adobe Real-Time Customer Data PlatformやAdobe Journey Optimizerで使用できるようになります。 **オーディエンス**&#x200B;メニューでアクセスできます。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}

## ガバナンス、プライバシー、セキュリティ {#governance-privacy-security}

### プライバシーリクエスト {#gov-privacy-requests}

構成を作成すると、結果として得られるオーディエンスは Adobe Experience Platform に保存されます。

その後、Adobe Experience Platform **Privacy Service** を通じて、これらのオーディエンスに対応するプロファイルデータにアクセスしたり、プロファイルデータを削除したりするプライバシーリクエストを行うことができます。このサービスでは、顧客データリクエストの管理に役立つ[ユーザーインターフェイス](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja){target="_blank"}と [RESTful API](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/overview){target="_blank"} を提供します。

>[!NOTE]
>
>Privacy Service について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja){target="_blank"}を参照してください。

Adobe 連合オーディエンス構成から顧客データにアクセスし、削除する個別のリクエストを作成および管理できます。**アクセスリクエスト**&#x200B;および&#x200B;**削除リクエスト**&#x200B;を送信する手順について詳しくは、[リアルタイム顧客プロファイルドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/privacy){target="_blank"}を参照してください。

### 監査記録 {#gov-audit-trail}

監査記録機能では、環境に対して行われたすべてのアクションとイベントの詳細かつ時系列の記録がリアルタイムで提供されます。[詳細情報](../admin/audit-trail.md)

## 詳細情報 {#learn}

<!-- Workflow + Workflow activities-->


連合オーディエンス構成、ガードレールおよび制限にアクセスする方法について詳しくは、[このページ](access-prerequisites.md)を参照してください。

また、[このページ](faq.md)のよくある質問も参照してください。


>[!CONTEXTUALHELP]
>id="dc_workflow_settings_execution"
>title="実行設定"
>abstract="このセクションでは、構成履歴を保持する日数など、ワークフローの実行に関連する設定を指定できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_query_enrichment_noneditable"
>title="編集不可のアクティビティ"
>abstract="コンソールで「**クエリ**」アクティビティまたは「**エンリッチメント**」アクティビティに追加のデータを設定する際、エンリッチメントデータが考慮され、アウトバウンドトランジションに渡されますが、編集はできません。"

<!-- Create a link -->

>[!CONTEXTUALHELP]
>id="dc_federated_database_create_link"
>title="リンクの作成"
>abstract="リンク設定を定義します。"


<!-- incremental query IDs -->

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

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalmode_standard"
>title="増分クエリモード"
>abstract="増分クエリを使用すると、新しい実行ごとに以前の実行結果を除外することで、同じクエリを複数回実行できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_incrementalmode_custom"
>title="増分クエリモード"
>abstract="増分クエリを使用すると、日付フィールドが増分クエリアクティビティの最後の実行日以降である結果のみを考慮して、同じクエリを複数回実行できます。"

>[!CONTEXTUALHELP]
>id="dc_orchestration_build_audience_dimension"
>title="ターゲティングディメンションの選択"
>abstract="ターゲティングディメンションは、受信者、契約の受益者、オペレーター、サブスクライバーなど、ターゲットされる母集団を操作ごとに定義します。デフォルトでは、メールと SMS の場合、ターゲットは受信者ビルトインテーブルから選択されます。プッシュ通知の場合、デフォルトのターゲットディメンションはサブスクライバーのアプリケーションです。"

