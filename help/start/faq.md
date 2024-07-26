---
title: よくある質問
description: Adobe Experience Platform Federated Audience コンポジションに関するよくある質問です
badge: label="限定提供" type="Informative"
exl-id: 68cc0ae5-5c41-425f-8b10-ab3515294006
source-git-commit: 3384c816e64b93a80b8e9b3e61dab74fa098889f
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---

# よくある質問 {#faq}

Adobe Experience Platform Federated Audience Composition に関するよくある質問のリストを以下に示します。 Adobe Experience Platform セグメント化サービスに関するグローバル FAQ は、[ このページ ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq){target="_blank"} でも入手できます。


+++Federated Audience Composition にアクセスするには、どのような権限が必要ですか？

Federated Audience Composition には、Adobe Real-time Customer Data PlatformおよびAdobe Journey Optimizer Prime または Ultimate パッケージが必要です。 Federated Audience コンポジションには、特定の権限はありません。 この機能にアクセスするための唯一の前提条件は、Federated Audience Composition アドオンを購入することです。

+++

+++どのクラウドウェアハウスに対応していますか？

このリリースでは、Federated Audience Composition は次と互換性があります。

* Amazon Redshift
* Azure synapse
* Google BigQuery
* Snowflake
* Vertica Analytics

+++


+++複数のデータウェアハウスに対して同じ構成でクエリを実行できますか？

はい。複数のウェアハウスを同じ構成でクエリでき、複数のソースからのデータを組み合わせることができます。  通常、各 [ コンポジションアクティビティ ](../compositions/orchestrate-activities.md) （クエリ、エンリッチメント、分割など） アクティビティの設定、ターゲットとなるデータベース（Federated Data Access のケースが複数ある場合があります）、および実行結果を含む 1 つ以上のワークテーブルの出力に応じて、1 つまたは複数の SQL 文を実行します。 これらのワークテーブルは、連続するアクティビティの入力として使用されます。

+++

+++ Federated Audience Composition を使用してデータベース全体にアクセスすることはできますか。

いいえ、専用または共有のデータベース/スキーマへのアクセスを設定するかどうかは、ユーザー次第です。 Federated Audience Composition 用の専用のスキーマを作成し、ビジネスケースのデータセットのみをコピー/共有することをお勧めします。
+++



+++専用スキーマのすべてのテーブルにアクセスできますか？

はい。接続したら、Federated Audience Composition を使用して、定義された初期権限に基づいてすべてのテーブルを検出できます。その後、ビジュアルスキーマエディターを使用して、次の操作を実行できます。

* テーブルから列とプライマリキーを検出
* これらのテーブルにわかりやすいラベルを作成する
* 各列にわかりやすいラベルを作成します
* 不要な列を非表示
* これらのテーブルの説明を保存
+++


+++Federated Audience コンポジションに一時的なストレージはありますか？

いいえ。Federated Audience 構成には、メタデータ（スキーマの説明）のみが格納されます。 顧客データが転送されていません。<!--The Audience export flow is done directly from Adobe Experience Platform Audience Portal (via [Destination](../connections/destinations.md)) to the customer database. The creation and update flow is done directly from your data warehouse database to Adobe Experience Platform Audience Portal.-->

+++

+++Federated Audience Composition には、ダウンストリームシステムに送信するユーザーのリストの物理的なコピーが保存されますか？

Federated Audience Composition では、データの物理的なコピーは管理されません。 頻度は、このデータが更新される頻度を定義するためにコンポジションで設定されます。 結果のオーディエンスデータは、お客様のユースケースやアクションで必要とされる期間を超えて、Adobe Experience Platformによって保存されることはありません。

例：

* オーディエンスを作成した場合、オーディエンスはウェアハウスに作成され、追加のコンポジションタスクやデータ操作に Federated Audience Composition を使用してから、Adobe Experience Platform Audience ポータルを介して結果オーディエンスおよび関連する属性を公開できます。 オーディエンス定義と関連属性は、Adobe Experience Platformに渡されます。
外部で生成されたオーディエンスの現在のデータ有効期限は 30 日であることに注意してください。 このデータの有効期限により、組織内に保存される過剰なデータの量が減ります。 データの有効期限が過ぎても、関連するデータセットはデータセットインベントリ内に引き続き表示されますが、オーディエンスをアクティブ化することはできません。また、プロファイル数は 0 と表示されます。 詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#how-long-do-externally-generated-audiences-last-for){target="_blank"}を参照してください。

* オーディエンスエンリッチメントの場合、開始点は既存のAdobe Experience Platform オーディエンスです。 次の 2 つのシナリオを見ることができます。
   1. フェデレーション Data Warehouse から追加のオーディエンスペイロード属性を取り込みます。この場合、追加される追加の属性は、このオーディエンス定義の一部として提供されます。 外部で生成されたオーディエンスのデータの有効期限は、上記と同じ（30 日）です。
   1. Data Warehouse に存在する追加の属性に基づいて、既存のAdobe Experience Platform オーディエンスを絞り込みます。<!--For example, you have an audience of customers who have shown interest in a particular product on the website for the last two months. You now want to take this audience and further segment it using Federated Audience Composition to only include customers who have a high credit score. The credit score is deemed sensitive and individual credit score data points are not copied over from the data warehouse.-->
+++

+++オーディエンス作成およびオーディエンスエンリッチメントのユースケースのパターンに関するデータが保持されていない場合、そのデータは一時的にどのように保存されますか？

結果のオーディエンスデータは、Adobe Experience Platformや Federated Audience Composition では無期限に保持されません。 ユースケースで必要とされる期間を超えて保持されることはありません。 オーディエンスペイロードの一部として取り込まれたオーディエンス属性は、オーディエンス定義の一部としてのみ保持されます。 永続性の期間は、すべてのオーディエンスの TTL に基づきます（デフォルトは 30 日）。

+++

+++アップロードしたカスタムオーディエンスを削除できますか？

いいえ。現在のバージョンでは、カスタムでアップロードしたオーディエンスを削除できません。<!--that are not used in downstream activation directly in Audience Portal by simply selecting delete from the actions menu. Learn more in [Adobe Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#how-do-i-put-an-audience-in-the-deleted-state){target="_blank"}.-->

+++

+++複数のソースのデータを組み合わせる場合、どのようにデータを結合するか？ ID サービスを使用していますか？

いいえ。コンポジション中は ID サービスは利用されません。 コンポジションで使用される様々なソース間のデータは、ユーザー定義のロジック（基になるモデルで表現されたもの）を介して結合されます（CRM ID、ユーザーアカウント番号など）。 データウェアハウスで選択するために、オーディエンスの識別子として使用される ID を選択する必要があります。 Federated Audience Composition から得られたオーディエンスでは、結果のデータセットで ID の ID 名前空間を識別する必要があります。

+++

<!--
+++If I want to combine federated data with datasets that live in Adobe Experience Platform, how is this done?

Likewise, the Identity Service is not being leveraged in this scenario either. The data model underpinning a composition needs to express how the data warehouse data and the audience to be enriched are related. e.g. assume an existing audience in Adobe Experience Platform contains several attributes, among which is the CRM ID. Assume transactional data is in the data warehouse containing purchases with various attributes, including the CRM ID of the purchaser. The end-user would have to specify that the CRM ID for both objects is used to stitch the two objects together.

+++
-->
