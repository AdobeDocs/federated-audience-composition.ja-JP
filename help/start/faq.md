---
title: よくある質問
description: Adobe Experience Platform 連合オーディエンス構成に関するよくある質問です
badge: label="限定提供" type="Informative"
exl-id: 68cc0ae5-5c41-425f-8b10-ab3515294006
source-git-commit: de5955ad481061c6f8e488c86fc9666736a2fa1e
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 91%

---

# よくある質問 {#faq}

以下は、Adobe Experience Platform 連合オーディエンス構成に関するよくある質問のリストです。また、Adobe Experience Platform セグメント化サービスに関するグローバル FAQ については、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq){target="_blank"}も参照してください。


+++連合オーディエンス構成にアクセスするために必要な権限は何ですか？

連合オーディエンス構成には、Adobe Real-time Customer Data Platform および Adobe Journey Optimizer Prime または Ultimate パッケージが必要です。また、連合オーディエンス構成アドオンを購入しておく必要もあります。

連合オーディエンス構成を使用するには、各ユーザーを各サンドボックス用に作成された特定のプロファイルに追加する必要があります。詳しくは、[連合オーディエンス構成へのアクセス](access-prerequisites.md)ページを参照してください。

+++

+++どのようなクラウドウェアハウスがサポートされていますか？

Federated Audience Composition でサポートされているシステムのリストについては、[ このページ ](../start/access-prerequisites.md#supported-systems) を参照してください。

+++


+++複数のデータウェアハウスに対して同じ構成でクエリを実行できますか？

はい、複数のウェアハウスに対して同じ構成でクエリを実行し、複数のソースからのデータを組み合わせることができます。通常、各 [ 構成アクティビティ ](../compositions/orchestrate-activities.md) （クエリ、エンリッチメント、分割など）は、アクティビティの設定、ターゲットとなるデータベース（Federated Data Access の場合が複数あります）、および実行結果を含む 1 つ以上のワークテーブルの出力に応じて、1 つまたは複数の SQL 文を実行します。 これらの作業用テーブルは、連続するアクティビティの入力として使用されます。

+++

+++ 連合オーディエンス構成を使用してデータベース全体にアクセスできますか？

いいえ、専用または共有のデータベース／スキーマへのアクセスはユーザーが設定します。連合オーディエンス構成専用のスキーマを作成し、ビジネスケースのデータセットのみをコピー／共有することをお勧めします。
+++

+++専用スキーマ内のすべてのテーブルにアクセスできますか？

はい、接続すると、連合オーディエンス構成を使用して、定義済みの初期権限に基づいてすべてのテーブルを検出し、ビジュアルスキーマエディターを使用して次の操作を実行できます。

* テーブルから列とプライマリキーを検出する
* これらのテーブルにわかりやすいラベルを作成する
* 各列にわかりやすいラベルを作成する
* 不要な列を非表示にする
* これらのテーブルの説明を保存する
+++

+++連合オーディエンス構成に一時的なストレージはありますか？

いいえ、連合オーディエンス構成はメタデータ（スキーマの説明）のみを保存します。顧客データは転送されません。<!--The Audience export flow is done directly from Adobe Experience Platform Audience Portal (via [Destination](../connections/destinations.md)) to the customer database. The creation and update flow is done directly from your data warehouse database to Adobe Experience Platform Audience Portal.-->

+++

+++連合オーディエンス構成には、ダウンストリームシステムに送信する人物のリストの物理的なコピーが保存されますか？

連合オーディエンス構成には、データの物理的なコピーは保存されません。このデータを更新する頻度を定義するには、構成内で頻度を設定します。結果のオーディエンスデータは、お客様のユースケースまたはアクションで必要とされる期間を超えて Adobe Experience Platform に保存されることはありません。

例：

* オーディエンスの作成の場合、オーディエンスはウェアハウス内に作成され、連合オーディエンス構成を使用して追加の構成タスクやデータ操作を実行した後で、Adobe Experience Platform オーディエンスポータル経由で結果のオーディエンスと関連属性を公開することができます。オーディエンス定義と関連属性は、Adobe Experience Platform に渡されます。
外部で生成したオーディエンスの現在のデータの有効期限は 30 日です。このデータの有効期限により、組織内に保存される余分なデータ量を削減できます。データの有効期限が過ぎると、関連付けられたデータセットはデータセットインベントリ内に引き続き表示されますが、オーディエンスをアクティベートすることはできず、プロファイル数はゼロとして表示されます。詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq#how-long-do-externally-generated-audiences-last-for){target="_blank"}を参照してください。

* オーディエンスのエンリッチメントの場合、既存の Adobe Experience Platform オーディエンスが出発点となります。ここでは、次の 2 つのシナリオを確認します。
   1. 連合データウェアハウスから追加のオーディエンスペイロード属性を取り込みます。この場合、追加属性は、このオーディエンス定義の一部として渡されます。外部で生成したオーディエンスのデータの有効期限は、上記と同じ 30 日間です。
   1. データウェアハウスに存在する追加属性に基づいて、既存の Adobe Experience Platform オーディエンスを絞り込みます。<!--For example, you have an audience of customers who have shown interest in a particular product on the website for the last two months. You now want to take this audience and further segment it using Federated Audience Composition to only include customers who have a high credit score. The credit score is deemed sensitive and individual credit score data points are not copied over from the data warehouse.-->
+++

+++オーディエンスの作成とオーディエンスエンリッチメントのユースケースパターンのデータが保持されていない場合、このデータはどのようにして一時的に保存されますか？

結果のオーディエンスデータは、Adobe Experience Platform または連合オーディエンス構成に無期限に保持されるわけではありません。ユースケースで必要な期間を超えて保持されることはありません。オーディエンスペイロードの一部として取り込まれたオーディエンス属性は、オーディエンス定義の一部としてのみ保持されます。保持期間はすべてのオーディエンスの TTL に基づき、デフォルトは 30 日です。

+++

+++カスタムアップロードしたオーディエンスを削除できますか？

いいえ。現在のバージョンでは、カスタムでアップロードしたオーディエンスを削除できません。-->

+++

+++複数のソースからデータを組み合わせる場合、データはどのように結合されますか？ID サービスを使用しますか？

いいえ、構成中に ID サービスは使用しません。構成で使用する様々なソース間のデータは、CRM ID、ユーザーアカウント番号など、ユーザー定義のロジック（基になるモデルで表現される）を通じて結合されます。データウェアハウスで選択するオーディエンスの識別子として使用される ID を選択する必要があります。連合オーディエンス構成からの結果のオーディエンスでは、結果のデータセット内の ID の ID 名前空間を識別する必要があります。

+++
