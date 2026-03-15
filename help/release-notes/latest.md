---
title: Federated Audience Composition リリースノート
description: Federated Audience コンポジションの最新のアップデートとリリースノートです。
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
source-git-commit: 7d12773b36cb963f3d4251a9b88486864056a0fb
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 11%

---


# リリースノート

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。 これらのリリースノートでは、すべての変更がまとめられています。[!DNL Federated Audience Composition] [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2026 年 2 月リリース {#fac-26-02}

Federated Audience Composition の 2 月のリリースでは、次の機能がサポートされています。

### 新機能 {#fac-26-02-feature}

| フィールドエンリッチメントのサポート |
| --- |
| これで、コンポジション内でフィールドを保存アクティビティを使用できます。 フィールドを保存アクティビティを使用すると、外部ウェアハウスのデータを統合してExperience Platform スキーマを強化し、追加の属性でExperience Platform スキーマを強化できます。 フィールドを保存アクティビティは、B2B と B2C の両方のスキーマをサポートしています。 このアクティビティの使用方法について詳しくは、[&#x200B; アクティビティの概要 &#x200B;](../compositions/activities.md#save-fields) を参照してください。 |

| Databricks の高度な認証サポート |
| --- |
| サービスプリンシパル認証または OAuth 2.0 を使用して、Databricks を使用して Federated Audience Composition に接続できるようになりました。 接続の作成について詳しくは、[&#x200B; 接続の概要 &#x200B;](../connections/home.md#create) を参照してください。 |

## 2026 年 1 月リリース {#fac-26-01}

Federated Audience Composition の 1 月のリリースでは、次の新機能と機能強化がサポートされています。

### 新機能 {#fac-26-01-feature}

| Azure Synapse サービスプリンシパル認証のサポート |
| --- |
| サービスプリンシパルを使用して、Azure Synapseで Federated Audience Composition に接続できるようになりました。 接続の作成について詳しくは、[&#x200B; 接続の概要 &#x200B;](../connections/home.md#create) を参照してください。 |

| Amazon Web Services（AWS）のAdobe Experience Platformのお客様向けの提供 |
| --- |
| Experience Platform インスタンスがAWS上にある場合、Federated Audience Composition を使用できるようになりました。 AWSのExperience Platformについて詳しくは、[&#x200B; マルチクラウドの概要 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/multi-cloud) を参照してください。 |

### 機能強化 {#fac-26-01-improvements}

このリリースには、次の機能強化が含まれています。

- **オーディエンスのデータ有効期限の設定**

  コンポジションで **オーディエンスを保存** アクティビティを使用する際に、データの有効期限を設定できるようになりました。

  Federated Audience Composition のデータ有効期限について詳しくは、[&#x200B; アクティビティガイド &#x200B;](../compositions/activities.md#save-audience) を参照してください。
