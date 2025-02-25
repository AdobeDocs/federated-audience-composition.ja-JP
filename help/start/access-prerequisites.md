---
title: 連合オーディエンス構成の前提条件とガードレール
description: 連合オーディエンス構成の前提条件、権限およびガードレールについて説明します
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
source-git-commit: ed72ae722ffd5fbf14f491630b748a5009f4ebc5
workflow-type: ht
source-wordcount: '260'
ht-degree: 100%

---

# 前提条件とガードレール {#fac-access}

連合オーディエンス構成には、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。この機能にアクセスするには、連合オーディエンス構成アドオンを購入しておく必要があります。

>[!AVAILABILITY]
>
>アドビからウェルカムメール通知を受信した後、インターフェイスが更新され、機能が使用可能になるまで、さらに数時間かかる場合があります。

## サポートされているシステム {#supported-systems}

連合オーディエンス構成は、次のクラウドウェアハウスをサポートしています。

* Amazon Redshift
* Azure Synapse
* Databricks
* Google BigQuery
* Snowflake
* Vertica Analytics

これらのシステムとの接続を作成する方法について詳しくは、[このページ](../connections/connections.md)を参照してください。

## サンドボックス

連合オーディエンス構成アドオンを購入すると、2 つのサンドボックスを使用できます。その他のサンドボックスプロビジョニングリクエストについて詳しくは、アドビ担当者にお問い合わせください。

## 権限 {#permissions}

連合オーディエンス構成にアクセスするには、購入時に作成されたサンドボックス固有の製品プロファイルにユーザーを追加し、**[!UICONTROL 連合データを管理]**&#x200B;権限を割り当てる必要があります。[詳細情報](feature-access.md)

## IP 許可リスト {#ip}

連合オーディエンス構成でデータベースに安全にアクセスできるようにするには、データベースにアクセスする連合オーディエンス構成サーバーの IP アドレスを承認する必要があります。これらの IP アドレスは、Adobe Experience Platform ユーザーインターフェイスで連合データベースを追加する際に表示されます。[詳細情報](../connections/connections.md)

連合オーディエンス構成のアクセス権を付与するには、これらの IP アドレスを許可リストに追加します。

## ガードレールと制限 {#fac-guardrails}

* 連合オーディエンス構成は現在、[正常性データを取り込み中の](https://experienceleague.adobe.com/ja/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield)お客様は利用できません{target="_blank"}。[詳細情報](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences){target="_blank"}

<!--
* Federated Audience Composition is compatible with Privacy & Security Shield and can be used in all verticals except for healthcare industries. Currently, Federated Audience Composition cannot be licensed to customers looking to ingest health data. [Learn more](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}-->

* このアドオンに適用されるエンタイトルメント、製品の制限、パフォーマンスガードレールの一覧について詳しくは、[Adobe Real-time Customer Data Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}を参照してください。
