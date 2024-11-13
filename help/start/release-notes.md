---
title: Experience Platform 連合オーディエンス構成の新機能
description: 最新の更新内容とリリースノート
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
source-git-commit: 65052ffcd8c70817aa428bea7f8b6baa0a49a1b0
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 92%

---

# リリースノート {#rn-new}

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。すべての変更は、このリリースノートに統合されます。[!DNL Federated Audience Composition] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2024年10月リリース {#fac-24-10}

>[!AVAILABILITY]
>
>以前は一連の組織（LA）で使用できましたが、Adobe Experience Platform Federated Audience Composition はすべてのユーザー（GA）が使用できるようになりました。 このアドオンは、提供されるに基づいてアクティブ化され、関連する権限でのみ表示されます。 [詳細情報](access-prerequisites.md)
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

連合オーディエンス構成は、エンタープライズデータウェアハウスへの柔軟で拡張されたアクセスを企業に提供し、重要なエンタープライズデータセットを使用してオーディエンスを構成し、ブランド主導の瞬間的なエクスペリエンスを強化するアドオン機能です。この新しいアプローチでは、[Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/home){target="_blank"} や [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} のユーザーとして、既存のデータウェアハウスからオーディエンスデータを直接統合して、Adobe Experience Platform オーディエンスを 1 つのシステムで強化できます。

連合オーディエンス構成は、ウェアハウスデータセットを使用してオーディエンスを柔軟に構成する必要がある企業に対する市場の需要の高まりに対応します。これにより、企業はデータの移動を削減しながら、重要なオーディエンスデータをマーケティングチームが使用できるようにし、ユースケースの要件を満たして、パーソナライズされたエクスペリエンスを強化できます。 

連合オーディエンス構成機能について詳しくは、[このページ](get-started.md)および[よくある質問](faq.md)を参照してください。

連合オーディエンス構成にアクセスするための前提条件と現在のガードレールについて詳しくは、[このページ](access-prerequisites.md)を参照してください。

