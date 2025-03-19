---
title: Experience Platform 連合オーディエンス構成の新機能
description: 最新の更新内容とリリースノート
hide: true
hidefromtoc: true
exl-id: 23ea1a5d-a0e4-4f47-b0f8-56009bbc0a4a
source-git-commit: 4b70d9e84a0089ffc4d3088bd21fb3803143ad38
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 69%

---

# リリースノート {#rn-new}

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。すべての変更は、このリリースノートに統合されます。[!DNL Federated Audience Composition] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 3 月リリース {#fac-25-3}

### 機能強化 {#fac-25-3-improvements}

このリリースには、以下の改善点が含まれています。

* **Federated Audience Composition の権限**

  3 月のリリース以降、[!DNL Federated Audience Composition] は、「Federated Data の管理 **権限を付与されたユーザーに対する** Federated Data Management **および** Federated Composition **インターフェイスのアクセスの適用を開始する予** です。

  [!DNL Federated Audience Composition] ユーザーインターフェイスへのアクセスを続行するには、ユーザーが管理者に連絡して、この権限を自分の役割に追加してもらうことをお勧めします。

  この権限の割り当て方法については、[ 詳細なドキュメント ](feature-access.md) を参照してください。

<!--
* **Data model Canvas view**

    The Canvas view for the Data Models section improves the experience by enabling the visualization of data models and their links in a canvas layout, alongside the existing tabular view. [Learn more](../data-management/gs-models.md)
-->

* **AI アシスタント**

  AI アシスタントは、Adobeの概念をナビゲートして理解し、特定の環境の運用に関するインサイトを取得するのに役立つように設計されたユーザーインターフェイス機能です。 Federated Audience Composition など、Adobe Experience Cloud全体の複数の製品で使用できます。

### 互換性 {#fac-25-3-compat}

* **Databricks 接続**

  この新しいリリースでは、Federated Audience Composition で、Databricks データベース接続のプライベートリンク接続がサポートされるようになりました。
また、Amazon Web Services（AWS）およびMicrosoft Azure でホストされる Databricks データベースへの安全な接続も可能になります。 [詳細情報](../connections/federated-db.md#databricks)

* **B2B CDP のお客様のサポート**

  Federated Audience Composition は、人物ベースのオーディエンスのユースケースで、B2B （Business to Business）の Customer Data Platform （CDP）のお客様が利用できるようになりました。

* **Snowflakeで保護された接続**

  この新しいリリースでは、Federated Audience Composition は、Microsoft Azure でホストされるSnowflake データベースへの安全なプライベートリンク接続をサポートします。 [詳細情報](../connections/federated-db.md#snowflake)

## 2025年2月リリース {#fac-25-2}

このリリースでは、以下に示す変更が含まれています。

* **Microsoft Fabric のサポート**

  連合オーディエンス構成を通じて Microsoft Fabricデータベースへの接続を確立できるようになりました。[詳細情報](../connections/federated-db.md)

* **Amazon Redshift Spectrum のサポート**

  Amazon Redshift データベース接続で Amazon Redshift Spectrum がサポートされるようになりました。[詳細情報](../connections/federated-db.md#amazon-redshift)

* **スキーマ作成エクスペリエンスの強化**

  スキーマの作成プロセスは、より直感的で操作しやすいように設計された、更新されたユーザーインターフェイスを通じて改善されました。これらの機能強化により、データ担当者はよりスムーズで効率的にデータモデルを開発できます。[詳細情報](../customer/schemas.md)

* **Databricks に対するオーディエンスエンリッチメントのサポート**

  オーディエンスを読み取りフローで Databricks を使用できるようになりました。これにより、Databricks データベースのアクティビティが有効になり、新しい宛先として設定できます。[詳細情報](../connections/destinations.md)

## 2024年11月リリース {#fac-24-11}

### 機能強化 {#fac-24-11-improvements}

このリリースには、以下の機能強化が含まれています。

* **IP アドレス許可リスト**

  Adobe Experience Platform ユーザーインターフェイスで連合データベースを追加する際に、連合オーディエンス構成インスタンスに関連付けられた IP アドレスを直接表示できるようになりました。これにより、これらの IP を簡単にコピーして承認し、データベースに接続して、セキュリティと柔軟性を向上させることができます。[詳細情報](../connections/connections.md)

## 2024年10月リリース {#fac-24-10}

>[!AVAILABILITY]
>
>以前は一部の組織（LA）に対して提供されていた Adobe Experience Platform 連合オーディエンス構成が、すべてのユーザー（GA）に対して提供されるようになりました。この機能は、のオファーに基づいてアクティブ化され、関連する権限でのみ表示されます。 [詳細情報](access-prerequisites.md)
>

### 互換性 {#fac-24-10-compat}

この新しいリリースでは、連合オーディエンス構成が、以下にリストされているシステムと互換性を持つようになりました。

* **Databricks のサポート**

  連合オーディエンス構成を通じて Databricks データベースへの接続を確立できるようになりました。[詳細情報](../connections/federated-db.md#databricks)

* **AWS PrivateLink を介した Snowflake への安全なアクセスのサポート**

  プライベートリンクを介した外部 Snowflake データウェアハウスへの安全なアクセスがサポートされるようになりました。Snowflake アカウントは、Amazon Web Services（AWS）でホストされ、連合オーディエンス構成環境と同じ地域に配置されている必要があります。Snowflake アカウントへの安全なアクセスの設定について詳しくは、アドビ担当者にお問い合わせください。[詳細情報](../connections/federated-db.md#snowflake)

* **Amazon Redshift Serverless のサポート**

  この新しいリリースでは、連合オーディエンス構成が、[Amazon Redshift Serverless](https://aws.amazon.com/jp/redshift/redshift-serverless/){target="_blank"} をサポートするようになりました。

### 機能強化 {#fac-24-10-improvements}

このリリースでは、以下に示す機能強化が含まれています。

* **既存のスキーマの更新**

  連合データベースで列を作成、変更、削除する際に、対応するスキーマの「**[!UICONTROL スキーマを更新]**」ボタンをクリックして、変更を検出および適用できるようになりました。[詳細情報](../customer/schemas.md#schema-refresh)

* **新しい構成とのデータモデルの関連付け**

  構成を作成する際に、構成に関連付けるデータモデルを選択できるようになりました。この新しいオプションを使用すると、関連付けたデータモデルのテーブルのみが使用可能になるので、アクティビティの設定が簡単になります。[詳細情報](../compositions/create-composition.md)

## 2024年7月リリース - 連合オーディエンス構成（LA） {#fac-la}

Federated Audience Composition を使用すると、企業はエンタープライズデータウェアハウスへの柔軟かつ拡張されたアクセス権を利用して、重要なエンタープライズデータセットと、ブランド主導の即時エクスペリエンスを活用したオーディエンスを作成できます。 この新しいアプローチでは、[Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/home){target="_blank"} や [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} のユーザーとして、既存のデータウェアハウスからオーディエンスデータを直接統合して、Adobe Experience Platform オーディエンスを 1 つのシステムで強化できます。

Federated Audience Composition は、オーディエンスをウェアハウスのデータセットで柔軟に構成する必要がある企業に対する、市場の需要の高まりに対応しています。 これにより、企業はデータの移動を削減しながら、重要なオーディエンスデータをマーケティングチームが使用できるようにし、ユースケースの要件を満たして、パーソナライズされたエクスペリエンスを強化できます。

連合オーディエンス構成機能について詳しくは、[このページ](get-started.md)および[よくある質問](faq.md)を参照してください。

連合オーディエンス構成にアクセスするための前提条件と現在のガードレールについて詳しくは、[このページ](access-prerequisites.md)を参照してください。
