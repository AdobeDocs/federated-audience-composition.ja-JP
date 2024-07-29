---
title: Federated Audience コンポジションの前提条件とガードレール
description: Federated Audience Composition の前提条件、権限およびガードレールについて説明します
badge: label="限定提供" type="Informative"
source-git-commit: f549f1611bfe6deb6dc684e3a0d9c968ba7c184a
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 3%

---

# 前提条件とガードレール {#fac-access}

Federated Audience Composition には、Adobe Real-time Customer Data PlatformやAdobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。 この機能にアクセスするには、Federated Audience Composition アドオンを購入する必要があります。

>[!AVAILABILITY]
>
>Adobeから「ようこそ」メール通知を受信した後、インターフェイスが更新され、使用可能な機能が使用可能になるまで、さらに数時間かかる場合があります。

## 権限 {#permissions}

Federated Audience Composition アドオンを購入すると、その時点でアクティブなサンドボックスごとに製品プロファイルが作成されます。 この製品プロファイルは、**Adobe Experience Platform** Admin Consoleカードの下のサンドボックスに作成され、次の命名規則に従います。`ACP_FAC - <<SandboxName>> - admin.` 特定のサンドボックスの Federated Audience コンポジションにアクセスするには、そのサンドボックス用に作成された製品プロファイルにユーザーを追加する必要があります。

例えば、「fac-test」という名前の新しいサンドボックスがアクティブ化されると、対応する製品プロファイル「ACP_FAC - fac-test - admin」が作成されます。 このサンドボックスで Federated Audience Composition にアクセスするには、ユーザーをこの製品プロファイルに追加する必要があります。

## IP の許可リストへの登録 {#ip}

Federated Audience Composition がデータベースに安全にアクセスできるようにするには、Adobe担当者に連絡して、データベースにアクセスする Federated Audience Composition サーバーの IP アドレスを取得してください。

これらの IP アドレスを許可リストに追加して、Federated Audience Composition のアクセス権を付与します。」

## ガードレールと制限 {#fac-guardrails}

* Federated Audience Composition は、プライバシーとセキュリティシールドと互換性があり、医療業界を除くすべての業界で使用できます。 現在、Federated Audience Composition は、正常性データの取り込みを検討しているお客様にはライセンスを付与できません。 [詳細情報](https://experienceleague.adobe.com/en/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield){target="_blank"}

* [Adobe Real-time Customer Data Platform ドキュメントに記載されている使用権限、製品の制限事項、パフォーマンスガードレールは ](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} このアドオンに適用されます。
