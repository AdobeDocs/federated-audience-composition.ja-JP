---
title: Experience Platform 連合オーディエンス構成の新機能
description: 最新の更新内容とリリースノート
exl-id: d4dcaf31-93cd-4a4e-888a-cf1bbdc4ca03
source-git-commit: d99bd98b5d63af55db223cf2e8dd3996d8012d24
workflow-type: ht
source-wordcount: '1244'
ht-degree: 100%

---

# リリースノート {#rn-new}

[!DNL Federated Audience Composition] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。すべての変更は、このリリースノートに統合されます。[!DNL Federated Audience Composition] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025年5月リリース {#fac-25-5}

### 新機能 {#fac-25-05-feature}

<table>
<thead>
<tr>
<th><strong>データモデルのキャンバス表示 - 一般公開</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>キャンバス表示を使用したデータモデルをすべてのユーザーが利用できるようになりました。</p>
<p>「データモデルのキャンバス表示」セクションでは、既存の表形式表示に加え、データモデルとそのリンクのビジュアライゼーションをキャンバスレイアウトで表示でき、エクスペリエンスが向上します。 </p>
<p>キャンバス表示について詳しくは、<a href="../data-management/gs-models.md">データモデルの概要</a>を参照してください。</p>
</br>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#fac-25-5-improvements}

このリリースには、次の機能強化が含まれています。

* **役割ベースのアクセス制御**

  5月のリリース以降、[!DNL Federated Audience Composition] は、アクセス制御に関する新しいきめ細かい権限をサポートします。ユーザーはこれらの権限をユーザーの役割に割り当てることで、[!DNL Federated Audience Composition] へのアクセスをより正確にすることができます。

  新しい権限について詳しくは、[連合オーディエンス構成アクセスガイド](feature-access.md)を参照してください。

## 2025年4月リリース {#fac-25-4}

### 新機能 {#fac-25-04-feature}

<table>
<thead>
<tr>
<th><strong>データモデルのキャンバス表示 - ベータ版</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>「データモデルのキャンバス表示」セクションでは、既存の表形式表示に加え、データモデルとそのリンクのビジュアライゼーションをキャンバスレイアウトで表示でき、エクスペリエンスが向上します。 </p>
<p>キャンバス表示を使用したデータモデルは現在、ベータ版として一部のユーザーのみが使用できます。</p>
<p>詳しくは、<a href="../data-management/gs-models.md">詳細なドキュメント</a>を参照してください。</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>製品知識のための AI アシスタントのサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、アドビの概念をナビゲートして理解し、特定の環境の運用上のインサイトを得るために設計されたユーザーインターフェイス機能です。連合オーディエンス構成を含め、Adobe Experience Cloud 全体の複数の製品で使用できます。</p>
<p>詳しくは、<a href="../start/ai-assistant.md">詳細なドキュメント</a>を参照してください。</p>
</br>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>プロファイルを保存アクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p> 連合オーディエンス構成では、プロファイルエンリッチメントのユースケースがサポートされるようになり、顧客は外部データウェアハウスのデータを使用して既存の Experience Platform プロファイルを強化できるようになりました。
</p>
<p>詳しくは、 <a href="../compositions/activities/save-profiles.md">詳細なドキュメント</a>を参照してください。</p>
</br>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#fac-25-4-improvements}

このリリースには、以下の機能強化が含まれています。

* **データモデル名**

  オーディエンスメニューの「**連合構成**」タブに ID の代わりにデータモデル名が表示されるようになり、明確さと全体的な使いやすさが向上しました。

* **オーディエンス**

  ユーザーが関連付けられていないデータモデルを選択した際、オーディエンスメニューには、選択したデータモデルの名前またはラベルが表示されるようになりました。

* **大規模なオーディエンスのエクスポート**

  連合オーディエンス構成は、ファイルサイズが 1 GB を超える大規模なオーディエンスのエクスポートをサポートするようになりました。

* **オーディエンスを保存アクティビティ**

  **オーディエンスを保存**アクティビティにメモが追加され、データ管理者と共同作業してオーディエンスの作成とエンリッチメント中に作成された新しいスキーマとデータセットにガバナンスラベルを適用するようユーザーに通知します。
  [データ使用ラベルの詳細情報を参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/user-guide)

### 互換性 {#fac-25-4-compat}

* **Amazon Redshift の安全な接続**

  この新しいリリースでは、連合オーディエンス構成が、Amazon Redshift データベースへの安全なプライベートリンク接続をサポートします。[詳細情報](../connections/federated-db.md#amazon-redshift)

* **Google BigQuery**

  この新しいリリースでは、連合オーディエンス構成が、Google BigQuery データベースへの安全な VPN 接続をサポートします。[詳細情報](../connections/federated-db.md#google-bigquery)

## 2025年3月リリース {#fac-25-3}

### 機能強化 {#fac-25-3-improvements}

このリリースには、以下の機能強化が含まれています。

* **連合オーディエンス構成権限**

  3 月リリース以降、[!DNL Federated Audience Composition] では、**連合データを管理**&#x200B;権限を付与されたユーザーに対して&#x200B;**連合データ管理**&#x200B;および&#x200B;**連合構成**&#x200B;インターフェイスへのアクセス権の適用を開始する予定です。

  [!DNL Federated Audience Composition] ユーザーインターフェイスに引き続きアクセスするには、管理者に連絡して、自分の役割にこの権限を追加してもらうことをお勧めします。

  この権限を割り当てる方法について詳しくは、[詳細なドキュメント](feature-access.md)を参照してください。

<!--
* **Data model Canvas view**

    The Canvas view for the Data Models section improves the experience by enabling the visualization of data models and their links in a canvas layout, alongside the existing tabular view. [Learn more](../data-management/gs-models.md)

* **AI Assistant**

    AI Assistant is a user interface feature designed to help you navigate and understand Adobe concepts and get operational insights for your specific environment. It is available in several products across Adobe Experience Cloud, including Federated Audience Composition. 
-->


### 互換性 {#fac-25-3-compat}

* **Databricks 接続**

  この新しいリリースでは、連合オーディエンス構成が、Databricks データベース接続のプライベートリンク接続をサポートするようになりました。
これには、プライベートリンク経由で Amazon Web Services（AWS）でホストされている Databricks データベースへの安全な接続と、VPN 経由で Microsoft Azure でホストされている Databricks データベースへの安全な接続が含まれます。[詳細情報](../connections/federated-db.md#databricks)

* **B2B CDP のお客様のサポート**

  企業間（B2B）顧客データプラットフォーム（CDP）のお客様は、個人ベースのオーディエンスのユースケースで連合オーディエンス構成を使用できるようになりました。

* **Snowflake の安全な接続**

  この新しいリリースでは、連合オーディエンス構成が、Microsoft Azure でホストされている Snowflake データベースへの安全なプライベートリンク接続をサポートします。[詳細情報](../connections/federated-db.md#snowflake)

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
>以前は一部の組織（LA）に対して提供されていた Adobe Experience Platform 連合オーディエンス構成が、すべてのユーザー（GA）に対して提供されるようになりました。この機能は、提供されている内容に基づいてアクティブ化され、関連付けられている権限がある場合にのみ表示されます。[詳細情報](access-prerequisites.md)
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

連合オーディエンス構成は、エンタープライズデータウェアハウスへの柔軟で拡張されたアクセスを企業に提供し、重要なエンタープライズデータセットを使用してオーディエンスを構成し、ブランド主導の瞬間的なエクスペリエンスを強化します。この新しいアプローチでは、[Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/home){target="_blank"} や [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} のユーザーとして、既存のデータウェアハウスからオーディエンスデータを直接統合して、Adobe Experience Platform オーディエンスを 1 つのシステムで強化できます。

連合オーディエンス構成は、ウェアハウスデータセットを使用してオーディエンスを柔軟に構成する必要がある企業に対する市場の需要の高まりに対応します。これにより、企業はデータの移動を削減しながら、重要なオーディエンスデータをマーケティングチームが使用できるようにし、ユースケースの要件を満たして、パーソナライズされたエクスペリエンスを強化できます。

連合オーディエンス構成機能について詳しくは、[このページ](get-started.md)および[よくある質問](faq.md)を参照してください。

連合オーディエンス構成にアクセスするための前提条件と現在のガードレールについて詳しくは、[このページ](access-prerequisites.md)を参照してください。
