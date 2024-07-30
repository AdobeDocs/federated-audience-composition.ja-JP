---
title: Federated Audience コンポジションの前提条件とガードレール
description: Federated Audience Composition の前提条件、権限およびガードレールについて説明します
badge: label="限定提供" type="Informative"
source-git-commit: 75fa26d74931d63c94e138fe29d85088932acd7f
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 13%

---

# 前提条件とガードレール {#fac-access}

Federated Audience Composition には、Adobe Real-time Customer Data PlatformやAdobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。 この機能にアクセスするには、Federated Audience Composition アドオンを購入する必要があります。

>[!AVAILABILITY]
>
>アドビからウェルカムメール通知を受信した後、インターフェイスが更新され、機能が使用可能になるまで、さらに数時間かかる場合があります。

## 権限 {#permissions}

Federated Audience Composition アドオンを購入すると、その時点でアクティブなサンドボックスごとに製品プロファイルが作成されます。 この製品プロファイルは、**Adobe Experience Platform** Admin Consoleカードの下のサンドボックスに作成され、次の命名規則に従います。`ACP_FAC - <<SandboxName>> - admin.` 特定のサンドボックスの Federated Audience コンポジションにアクセスするには、そのサンドボックス用に作成された製品プロファイルにユーザーを追加する必要があります。

例えば、「fac-test」という名前の新しいサンドボックスがアクティブ化されると、対応する製品プロファイル「ACP_FAC - fac-test - admin」が作成されます。 このサンドボックスで Federated Audience Composition にアクセスするには、ユーザーをこの製品プロファイルに追加する必要があります。

## IP の許可リストへの登録 {#ip}

Federated Audience Composition がデータベースに安全にアクセスできるようにするには、Adobe担当者に連絡して、データベースにアクセスする Federated Audience Composition サーバーの IP アドレスを取得してください。

これらの IP アドレスを許可リストに追加して、Federated Audience Composition のアクセス権を付与します。

## ガードレールと制限 {#fac-guardrails}

* Federated Audience Composition は、現在、Healthcare Shield およびプライバシーとセキュリティシールドでは使用できません。

<!--
* Federated Audience Composition is compatible with Privacy & Security Shield and can be used in all verticals except for healthcare industries. Currently, Federated Audience Composition cannot be licensed to customers looking to ingest health data. [Learn more](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}-->

* [Adobe Real-time Customer Data Platform ドキュメントに記載されている使用権限、製品の制限事項、パフォーマンスガードレールは ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"} このアドオンに適用されます。
