---
title: Federated Audience Composition の概要
description: Adobe Federated Audience Composition の概要と、Adobe Experience PlatformやAdobe Journey Optimizerなどのダウンストリームサービスでの使用方法について説明します
exl-id: 43464aea-9c1d-4f1f-859f-82f209f350b7
source-git-commit: 65a69bf857ec1a0701534693600a8c6340179838
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 51%

---

# Federated Audience Composition の概要

Federated Audience Composition を使用すると、サードパーティのデータウェアハウスからオーディエンスを作成および強化し、そのオーディエンスをAdobe Experience Platformに読み込むことができます。 これにより、企業のデータウェアハウスをAdobe Real-Time Customer Data PlatformやAdobe Journey Optimizerなどのダウンストリームサービス内に直接接続し、データウェアハウスのテーブルに対してクエリを実行するための簡単で強力なソリューションが提供されます。 その結果、データウェアハウスや、Amazon Redshift やAzure Synapse Analytics などのクラウドストレージプラットフォームに保存されている顧客データにアクセスできます。

## 機能 {#rn-capabilities}

連合オーディエンス構成は、オーディエンスのキュレーションとアクティベーションに対する包括的なアプローチを用いて、Real-time CDP と Journey Optimizer の価値を拡張します。

* **重要なウェアハウスベースのデータセットへのアクセスを拡張して、価値の高いオーディエンスを作成**：既存のデータウェアハウスをレコードのメインシステムとして使用しながら、クラス最高のアプリケーションを活用して優れたカスタマーエクスペリエンスを強化できます。

* **エンゲージメントのユースケースを強化するための包括的なサポート**:Federated Audience Composition はReal-Time CDPまたはJourney Optimizerと組み合わせて、Federated Audiences でブランド主導のパーソナライズされたエクスペリエンスをサポートし、リアルタイムイベントでトリガーされたインサイトエクスペリエンスを、チーム全体のユースケース要件を満たすユーザー属性と組み合わせて提供します。

* **データの移動と重複を最小限に抑える**：基本データをコピーして実用的なマーケティングプロファイルとオーディエンスを管理することなく、エンタープライズデータウェアハウスに存在するデータセットからオーディエンスを作成できます。

* **エクスペリエンス駆動型ワークフローで単一のシステムを利用**:Adobe Experience Platformで取り込まれたオーディエンスとフェデレーション オーディエンスの両方をキュレーションし、すべてのチャネルにわたってアウトバウンドエクスペリエンスを調整できます。

* **マルチエディションのサポート**:B2C および B2B CDP のお客様は、Federated Audience Composition を活用して、サポートされているエンタープライズデータウェアハウスのデータを統合することで、人物ベースのオーディエンスを構築できます。 さらに、enterprise data warehouse で使用可能な関連属性を取り込み、オーディエンスプロファイルを強化してパーソナライズされたターゲットエンゲージメントを強化することで、既存のExperience Platformの人物ベースのオーディエンスを強化できます。

## ユースケース {#use-cases}

連合オーディエンス構成では、オーディエンスの作成、オーディエンスエンリッチメント、顧客プロファイルエンリッチメントという **3 つ**&#x200B;のカテゴリのユースケースをサポートしています。

* **オーディエンスの作成**:Data Warehouse からオーディエンスを作成し、マーケターに適したドラッグ&amp;ドロップユーザーインターフェイスを使用して、それらのオーディエンスをExperience Platformに統合し、Real-Time CDPまたはJourney Optimizerで使用できるようにします。 その結果、基になる機密性の高いデータをコピーしたり、既存のデータを複製したりすることなく、データウェアハウスに対してクエリを実行できます。
   * **例：**&#x200B;ウェアハウス内のトランザクションデータ履歴を使用して、これらのトランザクションを Experience Platform にコピーすることなく、価値の高い過去の購入者のオーディエンスを作成します。

* **オーディエンスの強化**：データウェアハウスから追加のデータセットを使用し、この情報をオーディエンスにオーバーレイすることで、Experience Platformの既存のオーディエンスに詳細を追加できます。基になるデータをExperience Platformにコピーする必要はありません。 オーディエンスエンリッチメントを使用すると、強化されたオーディエンスを用いて改善されたパーソナライゼーションを提供できます。
   * **例：**&#x200B;買い物かごを放棄したユーザーの Experience Platform オーディエンスを、価値の高い過去の購入者の連合オーディエンス構成オーディエンスで強化し、ターゲットを絞ったオファーを提供します。

* **プロファイルのエンリッチメント**:Data Warehouse から個々の顧客属性を選択して、Experience Platform プロファイルを強化できます。 これらのプロファイルに連合データを追加すると、インバウンド顧客シグナルによってトリガーされる即時のエクスペリエンスをより強化できます。
   * **例：**&#x200B;連合オーディエンスからの情報を使用して、Experience Platform プロファイルを強化します。価値の高い過去の購入者の連合オーディエンスに属するサイト訪問者に対して、サイト上での行動に基づいてトリガーされるターゲットオファーを使用してマーケティングできるようになりました。

![図](assets/overview/fac-use-cases.png){zoomable="yes"}{width="75%" align="center"}

連合オーディエンス構成のユースケースについて詳しくは、[連合オーディエンス構成のホワイトペーパー](https://business.adobe.com/resources/sdk/flexibly-access-enterprise-data-with-federated-audience-composition.html)を参照してください。

## 主な手順 {#gs-steps}

アドビの連合オーディエンス構成を使用すると、取り込みプロセスなしで、データベースから直接 Adobe Experience Platform オーディエンスを作成および更新できます。

<!--![diagram](assets/steps-diagram.png){zoomable="yes"}{width="85%" align="center"}-->

1. **接続の作成**：様々なソースからのデータを統合し、統合されたデータセットに結合します。 Adobe Experience Platform アプリケーションの enterprise data warehouse への接続、サポートされているデータベース、接続の設定について詳しくは、[&#x200B; 接続の概要 &#x200B;](./connections/home.md) を参照してください。

2. **データのモデル化**：データの構造、関係、制約を定義するスキーマとデータモデルを設計および作成します。 スキーマについて詳しくは、[&#x200B; スキーマの概要 &#x200B;](./data-modelling/schemas.md) を参照してください。 データモデルについて詳しくは、[&#x200B; データモデルの概要 &#x200B;](./data-modelling/models.md) を参照してください。

3. **データの変換**：データ操作テクニックを適用して、データ要素の形式、構造または値を変更し、特定の分析やアプリケーションに対して互換性や適したものにします。

4. **オーディエンスの作成**：オーディエンスを作成、オーケストレーションおよび作成する。 オーディエンスの構成について詳しくは、[&#x200B; 構成の概要 &#x200B;](./compositions/home.md) を参照してください。 また、Adobe Experience Platform オーディエンスポータルと宛先を通じて、既存のオーディエンスを更新または再利用することもできます。詳しくは、[このページ](./connections/destinations.md)を参照してください。

>[!NOTE]
>
>構成を実行すると、結果のオーディエンスが外部オーディエンスとして Adobe Experience Platform に保存され、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer で使用できるようになります。**オーディエンス**&#x200B;メニューでアクセスできます。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}

## ガバナンス、プライバシー、セキュリティ {#governance-privacy-security}

### プライバシーリクエスト {#gov-privacy-requests}

構成を作成すると、結果として得られるオーディエンスは Adobe Experience Platform に保存されます。

その後、Adobe Experience Platform **Privacy Service** を通じて、これらのオーディエンスに対応するプロファイルデータにアクセスしたり、プロファイルデータを削除したりするプライバシーリクエストを行うことができます。このサービスでは、顧客データリクエストの管理に役立つ[ユーザーインターフェイス](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja){target="_blank"}と [RESTful API](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/overview){target="_blank"} を提供します。

>[!NOTE]
>
>Privacy Service について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ja){target="_blank"}を参照してください。

Adobe 連合オーディエンス構成から顧客データにアクセスし、削除する個別のリクエストを作成および管理できます。**アクセスリクエスト**&#x200B;および&#x200B;**削除リクエスト**&#x200B;を送信する手順について詳しくは、[リアルタイム顧客プロファイルドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/privacy){target="_blank"}を参照してください。

### 監査記録 {#gov-audit-trail}

監査記録機能は、環境に対して実行されたすべてのアクションとイベントの詳細な時系列の記録をリアルタイムで提供します。 監査証跡の詳細については、[&#x200B; 監査証跡の概要 &#x200B;](./admin/audit-trail.md) を参照してください。

## 詳細情報 {#learn}

<!-- Workflow + Workflow activities-->

連合オーディエンス構成、ガードレールおよび制限にアクセスする方法について詳しくは、[このページ](./start/access-prerequisites.md)を参照してください。

よくある質問への回答については、[Federated Audience Composition FAQ](./faq.md) を参照してください。

>[!CONTEXTUALHELP]
>id="dc_workflow_settings_execution"
>title="実行設定"
>abstract="このセクションでは、コンポジション履歴を保持する日数など、ワークフローの実行に関する設定を指定できます。"

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

