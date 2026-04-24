---
title: よくある質問
description: Adobe Experience Platform 連合オーディエンス構成に関するよくある質問です
exl-id: 68cc0ae5-5c41-425f-8b10-ab3515294006
TQID: https://experienceleague.adobe.com/Wd6WnteenqEV9ZEBs4-tgD8aRSSO1SwtEB4EetSUac4
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: fda4d9d7b45833d7e080ae80f42b7ca5ce36b3ad
workflow-type: tm+mt
source-wordcount: 975
ht-degree: 75%

---

# よくある質問 {#faq}

以下は、Adobe Experience Platform 連合オーディエンス構成に関するよくある質問のリストです。 また、Adobe Experience Platform セグメント化サービスに関するグローバル FAQ については、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq){target="_blank"}も参照してください。

## Federated Audience Compositionにアクセスするには、どのような権限が必要ですか？

+++ 回答

連合オーディエンス構成には、Adobe Real-time Customer Data Platform および Adobe Journey Optimizer Prime または Ultimate パッケージが必要です。 また、連合オーディエンス構成も購入する必要があります。

連合オーディエンス構成を使用するには、各ユーザーを各サンドボックス用に作成された特定のプロファイルに追加する必要があります。 詳しくは、[連合オーディエンス構成へのアクセス](./start/access-prerequisites.md)ページを参照してください。

+++

## サポートされているクラウドウェアハウスは何ですか？

+++ 回答

現在、次のクラウドウェアハウスがサポートされています。

* Amazon Redshift
* Azure Synapse Analytics
* Databricks
* Google BigQuery
* Microsoft Fabric
* Oracle
* Snowflake
* Vertica Analytics

データウェアハウスへの接続について詳しくは、[接続の概要](./connections/home.md)を参照してください。

+++

## 複数のデータウェアハウスを同じコンポジションでクエリできますか？

+++ 回答

はい、複数のウェアハウスに対して同じ構成でクエリを実行し、複数のソースからのデータを組み合わせることができます。  通常、各[&#x200B; コンポジションアクティビティ &#x200B;](./compositions/activities.md) （クエリ、エンリッチメント、分割など） アクティビティの設定、ターゲットとなるデータベース（フェデレーションデータアクセスの複数のケースが可能）、実行の結果を含む1つ以上のワークテーブルの出力に応じて、1つまたは複数のSQL ステートメントを実行します。 これらのワークテーブルは、連続するアクティビティの入力として使用されます。

+++

### 連合オーディエンス構成を使用してデータベース全体にアクセスできますか？

+++ 回答

いいえ、専用または共有のデータベース／スキーマへのアクセスはユーザーが設定します。 連合オーディエンス構成専用のスキーマを作成し、ビジネスケースのデータセットのみをコピー／共有することをお勧めします。
+++

## 専用スキーマ内のすべてのテーブルにアクセスできますか？

+++ 回答

はい、接続すると、連合オーディエンス構成を使用して、定義済みの初期権限に基づいてすべてのテーブルを検出し、ビジュアルスキーマエディターを使用して次の操作を実行できます。

* テーブルから列とプライマリキーを検出する
* これらのテーブルにわかりやすいラベルを作成する
* 各列にわかりやすいラベルを作成する
* 不要な列を非表示にする
* これらのテーブルの説明を保存する
+++

## Federated Audience Compositionに一時的なストレージはありますか？

+++ 回答

いいえ、連合オーディエンス構成はメタデータ（スキーマの説明）のみを保存します。 顧客データは転送されません。<!--The Audience export flow is done directly from Adobe Experience Platform Audience Portal (via [Destination](../connections/destinations.md)) to the customer database. The creation and update flow is done directly from your data warehouse database to Adobe Experience Platform Audience Portal.-->

+++

## Federated Audience Compositionは、ダウンストリームのシステムに送信するユーザーのリストの物理的なコピーを保存しますか？

+++ 回答

連合オーディエンス構成には、データの物理的なコピーは保存されません。 このデータを更新する頻度を定義するには、構成内で頻度を設定します。 結果のオーディエンスデータは、お客様のユースケースまたはアクションで必要とされる期間を超えて Adobe Experience Platform に保存されることはありません。

例：

* オーディエンスの作成の場合、オーディエンスはウェアハウス内に作成され、連合オーディエンス構成を使用して追加の構成タスクやデータ操作を実行した後で、Adobe Experience Platform オーディエンスポータル経由で結果のオーディエンスと関連属性を公開することができます。 オーディエンス定義と関連属性は、Adobe Experience Platform に渡されます。
外部で生成したオーディエンスの現在のデータの有効期限は 30 日です。 このデータの有効期限により、組織内に保存される余分なデータ量を削減できます。 データの有効期限が過ぎると、関連付けられたデータセットはデータセットインベントリ内に引き続き表示されますが、オーディエンスをアクティベートすることはできず、プロファイル数はゼロとして表示されます。 詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq#how-long-do-externally-generated-audiences-last-for){target="_blank"}を参照してください。

* オーディエンスのエンリッチメントの場合、既存の Adobe Experience Platform オーディエンスが出発点となります。 ここでは、次の 2 つのシナリオを確認します。
   1. 連合データウェアハウスから追加のオーディエンスペイロード属性を取り込みます。この場合、追加属性は、このオーディエンス定義の一部として渡されます。 外部で生成したオーディエンスのデータの有効期限は、上記と同じ 30 日間です。
   1. データウェアハウスに存在する追加属性に基づいて、既存の Adobe Experience Platform オーディエンスを絞り込みます。<!--For example, you have an audience of customers who have shown interest in a particular product on the website for the last two months. You now want to take this audience and further segment it using Federated Audience Composition to only include customers who have a high credit score. The credit score is deemed sensitive and individual credit score data points are not copied over from the data warehouse.-->
+++

## オーディエンス作成とオーディエンスエンリッチメントのユースケースパターンのデータが保持されていない場合、一時的にどのように保存されますか？

+++ 回答

結果のオーディエンスデータは、Adobe Experience Platform または連合オーディエンス構成に無期限に保持されるわけではありません。 ユースケースで必要な期間を超えて保持されることはありません。 オーディエンスペイロードの一部として取り込まれたオーディエンス属性は、オーディエンス定義の一部としてのみ保持されます。 保持期間はすべてのオーディエンスの TTL に基づき、デフォルトは 30 日です。

+++

## オーディエンスを削除できますか？

+++ 回答

はい、Audience Portal内でFederated Audience Composition オーディエンスを削除できます。

+++

## 複数のソースからのデータを組み合わせる場合、どのようにデータを結合するのでしょうか？ ID サービスを使用しますか？

+++ 回答

いいえ、構成中に ID サービスは使用しません。 コンポジションで使用される様々なソース間のデータは、CRM ID、ユーザーアカウント番号など、ユーザー定義のロジック（基礎となるモデルで表される）を介して結合されます。データウェアハウスで選択するオーディエンスの識別子として使用されるIDを選択する必要があります。 連合オーディエンス構成からの結果のオーディエンスでは、結果のデータセット内の ID の ID 名前空間を識別する必要があります。

+++

## Federated Audience Compositionでプライバシーリクエストを作成および管理するにはどうすればよいですか？

+++ 回答

アドビの連合オーディエンス構成から顧客データにアクセスして削除するための個別のリクエストは、次の 2 つの方法で送信できます。

* Adobe Experience Platform **Privacy Service UI** 経由。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja){target="_blank"}
* Adobe Experience Platform **Privacy Service API** 経由。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/overview){target="_blank"}

**アクセスリクエスト**&#x200B;および&#x200B;**削除リクエスト**&#x200B;を作成および管理するすべての手順について詳しくは、[リアルタイム顧客プロファイルドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/privacy){target="_blank"}を参照してください。

+++

<!--
+++How are customer consent preferences honored for externally generated audiences that are imported into Federated Audience Composition?

As customer data is captured from multiple channels, identity stitching and merge policies allow this data to be consolidated in a single Real-Time Customer Profile. Information on the customers' consent preferences are stored and evaluated at the profile level.

Downstream Real-Time CDP and Journey Optimizer destinations check each profile for consent preferences prior to activation. Each profile's consent information is compared against consent requirements for a particular destination. If the profile does not satisfy the requirements, that profile is not sent to a destination.

When an external audience is ingested into Federated Audience Composition, it is reconciliated with existing profiles using a primary ID such as email or ECID. As a result, the existing consent policies will remain in force throughout activation.

>[!NOTE]
>
>Since the payload variables are not stored in the profile but in the data lake, you should not include consent information in externally generated audiences. Instead, use other Adobe Experience Platform ingestion channels where profile data is imported.

+++
-->
