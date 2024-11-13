---
title: 連合オーディエンス構成の前提条件とガードレール
description: 連合オーディエンス構成の前提条件、権限およびガードレールについて説明します
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
source-git-commit: 65052ffcd8c70817aa428bea7f8b6baa0a49a1b0
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 92%

---

# 前提条件とガードレール {#fac-access}

連合オーディエンス構成には、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。この機能にアクセスするには、連合オーディエンス構成アドオンを購入しておく必要があります。

>[!AVAILABILITY]
>
>アドビからウェルカムメール通知を受信した後、インターフェイスが更新され、機能が使用可能になるまで、さらに数時間かかる場合があります。

## サポート対象システム {#supported-systems}

Federated Audience Composition は、次のクラウドウェアハウスをサポートしています。

* Amazon Redshift
* Azure Synapse
* Databricks
* Google BigQuery
* Snowflake
* Vertica Analytics

これらのシステムとの接続を作成する方法については、[ このページ ](../connections/connections.md) を参照してください。

## 権限 {#permissions}

連合オーディエンス構成アドオンを購入すると、この時点でアクティブになっているサンドボックスごとに製品プロファイルが作成されます。この製品プロファイルは、Admin Console の **Adobe Experience Platform** 製品カードの下に作成され、次の命名規則に従います。`ACP_FAC - <<SandboxName>> - admin.` 特定のサンドボックスの連合オーディエンス構成にアクセスするには、このサンドボックス用に作成された製品プロファイルにユーザーを追加する必要があります。

例えば、「fac-test」という名前の新しいサンドボックスをアクティブ化すると、対応する製品プロファイル「ACP_FAC - fac-test - admin」が作成されます。このサンドボックスで連合オーディエンス構成にアクセスするには、ユーザーをこの製品プロファイルに追加する必要があります。

## IP 許可リスト {#ip}

連合オーディエンス構成でデータベースに安全にアクセスできるようにするには、アドビ担当者に連絡して、データベースにアクセスする連合オーディエンス構成サーバーの IP アドレスを取得してください。

連合オーディエンス構成のアクセス権を付与するには、これらの IP アドレスを許可リストに追加します。

## ガードレールと制限 {#fac-guardrails}

* 連合オーディエンス構成は現在、[ヘルスデータを取得](https://experienceleague.adobe.com/ja/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}するお客様と Adobe Journey Optimizer Privacy and Security Shield のお客様は使用できません。[詳細情報](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences){target="_blank"}。

<!--
* Federated Audience Composition is compatible with Privacy & Security Shield and can be used in all verticals except for healthcare industries. Currently, Federated Audience Composition cannot be licensed to customers looking to ingest health data. [Learn more](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}-->

* このアドオンに適用されるエンタイトルメント、製品の制限、パフォーマンスガードレールの一覧について詳しくは、[Adobe Real-time Customer Data Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}を参照してください。
