---
title: Federated Audience Composition リリースノート
description: Federated Audience Compositionの最新のアップデートとリリースノート。
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
TQID: https://experienceleague.adobe.com/AqtqibUr1TNXwQ9lrtVoQ3CBNwyjSMS64e4s8y4iTSc
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
source-git-commit: 8da27489f6767e837828456b2b11c8238ea6a0a4
workflow-type: tm+mt
source-wordcount: 726
ht-degree: 12%

---

# リリースノート

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。 すべての変更は、このリリースノートに統合されます。 [!DNL Federated Audience Composition] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2026年6月リリース {#fac-26-06}

Federated Audience Compositionの6月リリースでは、次の機能をサポートしています。

| GOOGLE [!DNL BigQuery]の[!DNL Apigee] ゲートウェイをサポートするREST API コネクタ |
| --- |
| REST API コネクタを使用してGoogle [!DNL BigQuery]に接続できるようになりました。サービスアカウント認証を使用する場合は、[!DNL Apigee] ゲートウェイを介して接続をルーティングするオプションがあります。 [!DNL Apigee]を使用した接続について詳しくは、[接続の概要](/help/connections/home.md#apigee)を参照してください。 |

## 26年5月リリース {#fac-26-05}

Federated Audience Compositionの5月リリースでは、次の機能をサポートしています。

| Google [!DNL BigQuery]のWorkload Identity Federation （WIF）認証 |
| --- |
| WIF認証を使用してGoogle [!DNL BigQuery]に接続できるようになりました。 WIF認証を使用した接続について詳しくは、[接続の概要](/help/connections/home.md#wif-configuration)を参照してください。 |

### 機能強化 {#fac-26-05-improvements}

このリリースには、次の改善点が含まれています。

- **Adobe Journey OptimizerのFederated Audience Composition オーディエンスを使用したマルチエンティティターゲティング オーディエンスの読み取りジャーニー**

  Journey OptimizerでFAC オーディエンス属性を補足識別子として活用できるようになりました。オーディエンスを読み取りジャーニー。 これにより、アカウントや購読レベルなどの複数のエンティティでオーディエンスをアクティブ化できます。

  詳しくは、ジャーニーのガイド [&#128279;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/supplemental-identifier)で補足識別子を使用するを参照してください。

## 2026年4月リリース {#fac-26-04}

Federated Audience Compositionの4月リリースでは、次の機能と機能強化がサポートされています。

### 新機能 {#fac=26-04-feature}

| 新しいコネクタ - Teradata |
| --- |
| Teradata コネクタは、Federated Audience Compositionで使用できるようになりました。 Teradata コネクタを使用して、オーディエンスの作成とオーディエンスエンリッチメントのユースケースを行うことができます。 Teradata コネクタについて詳しくは、[connections overview](/help/connections/home.md)を参照してください。 |

### 機能強化 {#fac-26-04-improvements}

このリリースには、次の改善点が含まれています。

- **Snowflakeの暗号化されていないキーのサポート**

  キーペア認証を使用してSnowflake data warehouseに接続する際に、暗号化されていないキーを使用できるようになりました。

  Snowflakeでの暗号化されていないキーの使用について詳しくは、[connections overview](/help/connections/home.md)を参照してください。

## 2026年3月リリース {#fac-26-03}

Federated Audience Compositionの3月リリースでは、次の機能をサポートしています。

### 新機能 {#fac-26-03-feature}

| AIを活用したセグメンテーション |
| --- |
| AI アシスタント内で連合オーディエンスの構成を自律的に作成できるようになりました。 AI アシスタントを使用してオーディエンスを作成する場合、AI アシスタントは、承認後、ブラウザー内で実行されるプランを生成します。 AI アシスタントを使用してオーディエンスを作成する方法について詳しくは、[AI アシスタントの概要](/help/start/ai-assistant.md)を参照してください。 |

| 運用インサイト用AI アシスタント |
| --- |
| 連合オーディエンス構成内の運用上のインサイトについて、AI アシスタントに質問できるようになりました。 サポートされている領域には、接続、スキーマ、データモデルなどがあります。 このリリースでは、連合コンポジションは&#x200B;**サポートされていません**。 連合オーディエンス構成のAI アシスタントについて詳しくは、[AI アシスタントの概要](/help/start/ai-assistant.md)を参照してください。 |

## 2026年2月リリース {#fac-26-02}

Federated Audience Compositionの2月リリースでは、次の機能をサポートしています。

### 新機能 {#fac-26-02-feature}

| フィールド強化サポート |
| --- |
| コンポジション内で「フィールドを保存」アクティビティを使用できるようになりました。 フィールドを保存アクティビティを使用すると、外部ウェアハウスからのデータをフェデレーションしてExperience Platform スキーマを強化し、追加の属性を使用してExperience Platform スキーマを強化できます。 フィールドを保存アクティビティでは、B2B スキーマとB2C スキーマの両方をサポートしています。 このアクティビティの使用について詳しくは、[&#x200B; アクティビティの概要](../compositions/activities.md#save-fields)を参照してください。 |

| Databricksの高度な認証サポート |
| --- |
| サービスプリンシパル認証またはOAuth 2.0を使用して、Databricksで連合オーディエンス構成に接続できるようになりました。 接続の作成について詳しくは、[接続の概要](../connections/home.md#create)を参照してください。 |

## 2026年1月リリース {#fac-26-01}

Federated Audience Compositionの1月リリースでは、次の新機能と機能強化がサポートされています。

### 新機能 {#fac-26-01-feature}

| Azure Synapse Service プリンシパル認証のサポート |
| --- |
| サービスプリンシパルを使用して、Azure Synapseで連合オーディエンス構成に接続できるようになりました。 接続の作成について詳しくは、[接続の概要](../connections/home.md#create)を参照してください。 |

| Amazon Web Services（AWS）でのAdobe Experience Platformのお客様の利用状況 |
| --- |
| Experience Platform インスタンスがAWS上にある場合、連合オーディエンス構成を使用できるようになりました。 AWS上のExperience Platformについて詳しくは、[&#x200B; マルチクラウドの概要](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud)を参照してください。 |

### 機能強化 {#fac-26-01-improvements}

このリリースには、次の改善点が含まれています。

- **オーディエンスのデータ有効期限の設定**

  コンポジションで&#x200B;**オーディエンスを保存** アクティビティを使用する際に、データの有効期限を設定できるようになりました。

  Federated Audience Compositionのデータ有効期限について詳しくは、[&#x200B; アクティビティガイド &#x200B;](../compositions/activities.md#save-audience)を参照してください。
