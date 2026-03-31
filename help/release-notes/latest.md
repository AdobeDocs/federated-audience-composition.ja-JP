---
title: Federated Audience Composition リリースノート
description: Federated Audience Compositionの最新のアップデートとリリースノート。
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
source-git-commit: d3a97b5887778f910ca8f09f7cb8fa99360a612c
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 8%

---


# リリースノート

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。 すべての変更点は、このリリースノートに統合されています。[!DNL Federated Audience Composition] は[!DNL Adobe Experience Platform]上でネイティブに構築され、最新のイノベーションと機能強化を継承しています。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 26年3月リリース {#fac-26-03}

Federated Audience Compositionの3月リリースでは、次の機能をサポートしています。

### 新機能 {#fac-26-03-feature}

| AIを活用したセグメンテーション |
| --- |
| AI アシスタント内で連合オーディエンスの構成を自律的に作成できるようになりました。 AI アシスタントを使用してオーディエンスを作成する場合、AI アシスタントは、承認後、ブラウザー内で実行されるプランを生成します。 AI アシスタントを使用してオーディエンスを作成する方法について詳しくは、[AI アシスタントの概要](/help/start/ai-assistant.md)を参照してください。 |

| 運用インサイト用AI アシスタント |
| --- |
| 連合オーディエンス構成内の運用上のインサイトについて、AI アシスタントに質問できるようになりました。 サポートされている領域には、接続、スキーマ、データモデルなどがあります。 このリリースでは、連合コンポジションは&#x200B;**サポートされていません**。 連合オーディエンス構成のAI アシスタントについて詳しくは、[AI アシスタントの概要](/help/start/ai-assistant.md)を参照してください。 |

## 26/2月リリース {#fac-26-02}

Federated Audience Compositionの2月リリースでは、次の機能をサポートしています。

### 新機能 {#fac-26-02-feature}

| フィールド強化サポート |
| --- |
| コンポジション内で「フィールドを保存」アクティビティを使用できるようになりました。 フィールドを保存アクティビティを使用すると、外部ウェアハウスからのデータをフェデレーションしてExperience Platform スキーマを強化し、追加の属性を使用してExperience Platform スキーマを強化できます。 フィールドを保存アクティビティでは、B2B スキーマとB2C スキーマの両方をサポートしています。 このアクティビティの使用について詳しくは、[&#x200B; アクティビティの概要](../compositions/activities.md#save-fields)を参照してください。 |

| Databricksの高度な認証サポート |
| --- |
| サービスプリンシパル認証またはOAuth 2.0を使用して、Databricksで連合オーディエンス構成に接続できるようになりました。 接続の作成について詳しくは、[接続の概要](../connections/home.md#create)を参照してください。 |

## 26年1月リリース {#fac-26-01}

Federated Audience Compositionの1月リリースでは、次の新機能と機能強化がサポートされています。

### 新機能 {#fac-26-01-feature}

| Azure Synapse Service プリンシパル認証のサポート |
| --- |
| サービスプリンシパルを使用して、Azure Synapseで連合オーディエンス構成に接続できるようになりました。 接続の作成について詳しくは、[接続の概要](../connections/home.md#create)を参照してください。 |

| Amazon Web Services（AWS）でのAdobe Experience Platformのお客様の利用状況 |
| --- |
| Experience Platform インスタンスがAWS上にある場合、連合オーディエンス構成を使用できるようになりました。 AWS上のExperience Platformについて詳しくは、[&#x200B; マルチクラウドの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/multi-cloud)を参照してください。 |

### 機能強化 {#fac-26-01-improvements}

このリリースには、次の改善点が含まれています。

- **オーディエンスのデータ有効期限の設定**

  コンポジションで&#x200B;**オーディエンスを保存** アクティビティを使用する際に、データの有効期限を設定できるようになりました。

  Federated Audience Compositionのデータ有効期限について詳しくは、[&#x200B; アクティビティガイド &#x200B;](../compositions/activities.md#save-audience)を参照してください。
