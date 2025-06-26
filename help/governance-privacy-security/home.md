---
title: 連合オーディエンス構成のプライバシーとセキュリティ
description: 連合オーディエンス構成で、データガバナンス、同意の適用、アクセス制御、データ暗号化、プライバシーコンプライアンスなどの機能を含む、ユーザーデータのプライバシーとセキュリティを処理する方法について説明します。
exl-id: 677e26e7-1294-4f62-a5ce-17b65e84c65e
source-git-commit: 7429577d99d2f163e7084db056005fe641d1bcf3
workflow-type: tm+mt
source-wordcount: '1182'
ht-degree: 77%

---

# データガバナンス、プライバシー、セキュリティ

>[!IMPORTANT]
>
>Federated Audience Composition は完全に HIPAA に準拠しており、Healthcare Shield のお客様だけでなく、Privacy and Security Shield のお客様も使用できます。

Federated Audience Composition には、ビジネスプラクティス、法的義務および開発プロセスに準拠できるサービスとツールがいくつか用意されています。

これらのサービスは、次の 3 つのカテゴリに分類できます。

- [データガバナンス](#data-governance)
- [プライバシー](#privacy)
- [セキュリティ](#security)

## データガバナンス {#data-governance}

データガバナンスを使用して顧客データを管理および識別し、組織または法規制によって定義された制限に従って適切にラベル付けされていることを確認できます。

### データ使用ラベル {#data-usage-labels}

データ使用ラベルを使用して、データに適用されるガバナンスポリシーに基づいてデータセットとフィールドを分類できます。 構成を使用してオーディエンスを作成したら、その結果作成されたスキーマに適切なデータラベルを適用して、必須の使用制限に準拠していることを確認できます。

Federated Audience Composition でのデータラベルの使用について詳しくは、[ アクセスラベルの適用 ](../compositions/gs-compositions.md#access-labels){target="_blank"} の節を参照してください。

## プライバシー

Federated Audience Composition :Adobe Experience PlatformおよびAdobe Journey Optimizerが使用するフェデレーティッドデータを提供し、ユーザーのデータのプライバシーが確実に尊重されるようにします。

### Privacy Service {#privacy-service}

Federated Audience Composition は、どのデータウェアハウスのカスタマーデータも保存 **しないので** Adobe Experience Platform Privacy Serviceを使用して、データ主体とデータ削除のリクエストに準拠することができます。

例えば、構成キャンバスでアクティビティを保存ブロックを使用してオーディエンスを作成すると、その結果作成されたオーディエンスは、外部オーディエンスとして Experience Platform のデータレイクに保存されます。この外部オーディエンスは、ID フィールドと ID 名前空間でマークされます。その結果、Privacy Service を使用して、外部オーディエンスと共にこれらのプロファイルにアクセスし、削除できます。

または、構成キャンバスでプロファイルを保存アクティビティを使用してプロファイルエンリッチメントを作成すると、その結果作成されたエンリッチメントは、プロファイル対応スキーマおよびプロファイル対応データセットとして Experience Platform に保存されます。このエンリッチメントデータは、ID フィールドと ID 名前空間でマークされます。その結果、Privacy Service を使用して、これらのプロファイルにアクセスし、削除できます。

Privacy Service について詳しくは、[Privacy Service の概要](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/home){target="_blank"}を参照してください。

### プライバシーリクエスト {#privacy-requests}

Privacy Service では、連合オーディエンス構成から顧客データにアクセスし、削除する個別のプライバシーリクエストを作成および管理できます。Privacy Service では、顧客データのリクエストの管理に役立つ[ユーザーインターフェイス](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja){target="_blank"}と [RESTful API](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/overview){target="_blank"} の両方を提供します。

プライバシーリクエストの作成と管理について詳しくは、[Privacy Service UI ガイドのプライバシージョブ](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/ui/user-guide){target="_blank"}を参照してください。

### 同意ポリシーの適用 {#consent}

連合オーディエンス構成では、Experience Platform を通じて、同意の適用を自動化し、顧客に提供された同意に基づいてオーディエンスをアクティブ化できるようにするツールを提供します。

例えば、構成キャンバスでアクティビティを保存ブロックを使用してオーディエンスを作成すると、その結果作成されたオーディエンスは、外部オーディエンスとして Experience Platform のデータレイクに保存されます。Experience Platform では、アクティベーション中に同意の検証を自動的にサポートします。詳しくは、[セグメント化サービスに関する FAQ](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/faq#consent){target="_blank"} を参照してください。

または、構成キャンバスでプロファイルを保存アクティビティを使用してプロファイルエンリッチメントを作成すると、その結果作成されたエンリッチメントは、プロファイル対応スキーマおよびプロファイル対応データセットとして Experience Platform に保存されます。既存のプロファイルの場合、使用可能な同意属性は、アクティベーション中に自動的に適用されます。新規プロファイルの場合、プロファイルの取り込み中に提供された同意属性は、アクティベーション中に自動的に適用されます。プロファイルに対する同意の適用について詳しくは、[同意および環境設定フィールドグループガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/field-groups/profile/consents){target="_blank"}を参照してください。

同意の適用について詳しくは、[ポリシーの管理 UI ガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/policies/user-guide#consent-policy){target="_blank"}を参照してください。

### データライフサイクル {#data-lifecycle}

連合オーディエンス構成では、いずれのデータウェアハウスからも顧客データは保存され&#x200B;**ない**&#x200B;ので、Experience Platform を使用してデータライフサイクルを管理できます。高度なデータライフサイクル管理を使用すると、データセットレベルとレコードレベルの両方でデータライフサイクルを管理できます。

例えば、構成キャンバスでアクティビティを保存ブロックを使用してオーディエンスを作成すると、その結果作成されたオーディエンスは、外部オーディエンスとして Experience Platform のデータレイクに保存されます。このデータは連合オーディエンス構成に保存され&#x200B;**ない**&#x200B;ので、オーディエンスポータルでオーディエンスを削除すると、オーディエンスデータと対応するデータセットは自動的に削除されます。

または、構成キャンバスでプロファイルを保存アクティビティを使用してプロファイルエンリッチメントを作成すると、その結果作成されたエンリッチメントは、プロファイル対応スキーマおよびプロファイル対応データセットとして Experience Platform に保存されます。その結果、データライフサイクルを使用して、プロファイルにアクセスし、削除できます。

データライフサイクルについて詳しくは、[データライフサイクルの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/data-lifecycle/home){target="_blank"}を参照してください。

## セキュリティ {#security}

データセキュリティにより、Federated Audience Composition でデータが保護されます。

### 暗号化 {#encryption}

Federated Audience Composition は、保存データ暗号化、転送中データ暗号化、顧客管理キーによる暗号化を提供します。

保存データは、連合オーディエンス構成内で使用される顧客データを指します。データは、クラウドサービスプロバイダーによって暗号化され、暗号化された形式で連合オーディエンス構成で使用されます。

転送中のデータは、連合オーディエンス構成でコンポーネント間を移動する際の顧客データを指します。データは、HTTPS 経由の TLS 1.3 を使用して、連合オーディエンス構成コンポーネントを通じて暗号化されたままになります。

アドビでのデータ暗号化の処理方法について詳しくは、[Experience Platform でのデータ暗号化](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/governance-privacy-security/encryption){target="_blank"}に関するガイドを参照してください。

### 顧客管理キー {#customer-managed-keys}

顧客管理キーを使用すると、独自の暗号化キーを使用してデータを暗号化できるので、データを制御できます。連合オーディエンス構成では、顧客データは保存され&#x200B;**ない**&#x200B;ので、その結果作成されるオーディエンスとエンリッチメントに顧客管理キーを直接使用できます。顧客管理キーは、Experience Platform のデータレイクに保存されるからです。

顧客管理キーについて詳しくは、[顧客管理キーガイド](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview){target="_blank"}を参照してください。

### 監査ログ {#audit-log}

連合オーディエンス構成で実行したすべての作成、読み取り、更新、削除の操作は、監査記録に記録されます。この監査ログを使用すると、これらのアクションを追跡し、アカウンタビリティを強化し、コンプライアンス監査をサポートできます。

詳しくは、[監査記録の概要](/help/admin/audit-trail.md){target="_blank"}を参照してください。

### アクセス制御 {#access-control}

連合オーディエンス構成へのアクセスは、フィールドレベルと役割ベースレベルの両方で制御できます。これらのアクセス制御を使用すると、データガバナンスポリシーを適用し、機密情報の公開を制限し、アクセスをユーザーの責任に合わせて調整できます。

Federated Audience Composition のアクセス制御の詳細については、[ アクセス制御ガイド ](/help/governance-privacy-security/access-control.md){target="_blank"} を参照してください。

### データのローカライゼーション {#data-localization}

連合オーディエンス構成では、顧客データは保存され&#x200B;**ません**。その結果、データを同じ地域内に保持するには、外部データベースを一致するサンドボックス地域に&#x200B;**のみ**&#x200B;接続する必要があります。別の地域のデータベースをサンドボックスに接続する場合、アドビではデータのローカライゼーションについては責任を負い&#x200B;**ません**。

## 次の手順 {#next-steps}

このガイドを読むことで、データ使用ラベル、プライバシーコンプライアンス、同意の適用、データライフサイクル管理、アクセス制御など、Federated Audience Composition で使用されるデータガバナンス、プライバシー、セキュリティの機能について理解が深まりました。
