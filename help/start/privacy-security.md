---
title: Federated Audience コンポジションのプライバシーとセキュリティ
description: Federated Audience Composition で、データガバナンス、同意適用、アクセス制御、データ暗号化、プライバシーコンプライアンスなどの機能を含む、ユーザーデータのプライバシーとセキュリティを扱う方法について説明します。
source-git-commit: b505a4f0ac9ac7350e2879f4f54f93a69b73f96c
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---


# Federated Audience コンポジションのプライバシーとセキュリティ

Federated Audience Composition は、処理中のデータを保護するために、多数のセキュリティ手法に準拠しています。

## Privacy Service {#privacy}

Federated Audience Composition は、使用するAdobe Experience PlatformおよびAdobe Journey Optimizerのフェデレーティッドデータを提供します。 ただし、Federated Audience Composition では、どのデータウェアハウスの顧客データも保存 **されません**。 その結果、Adobe Experience Platform Privacy Serviceを使用して、データ主体およびデータ削除リクエストに準拠できます。

例えば、コンポジションキャンバスの保存アクティビティブロックを使用してオーディエンスを作成すると、結果オーディエンスが外部オーディエンスとしてExperience Platformのデータレイクに保存されます。 この外部オーディエンスは、ID フィールドと ID 名前空間でマークされます。 その結果、Privacy Serviceを使用して、外部オーディエンスと共にこれらのプロファイルにアクセスし、削除できます。

または、コンポジションキャンバスで「プロファイルを保存」アクティビティを使用してプロファイルエンリッチメントを作成した後、結果のエンリッチメントをプロファイル対応のスキーマおよびプロファイル対応のデータセットとしてExperience Platformに保存します。 このエンリッチメントデータは、ID フィールドと ID 名前空間でマークされます。 その結果、Privacy Serviceを使用して、これらのプロファイルにアクセスし、消去できます。

Privacy Serviceについて詳しくは、[Privacy Serviceの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/home){target="_blank"} を参照してください。

### プライバシーリクエスト {#privacy-requests}

Privacy Serviceでは、個々のプライバシーリクエストを作成および管理し、Federated Audience Composition から顧客データにアクセスして削除できます。 Privacy Serviceは、カスタマーデータのリクエストの管理に役立つ [ ユーザーインターフェイス ](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=ja){target="_blank"} と [RESTful API](https://experienceleague.adobe.com/ja/docs/experience-platform/privacy/api/overview){target="_blank"} の両方を提供します。

プライバシーリクエストの作成と管理について詳しくは、[Privacy Service UI ガイドのプライバシージョブ ](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/ui/user-guide){target="_blank"} を参照してください。

## 同意ポリシーの適用 {#consent}

Federated Audience Composition は、Experience Platformを通じて、同意の自動適用を可能にするツールを提供し、顧客に提供された同意に基づいてオーディエンスをアクティベートできるようにします。

例えば、コンポジションキャンバスの保存アクティビティブロックを使用してオーディエンスを作成すると、結果オーディエンスが外部オーディエンスとしてExperience Platformのデータレイクに保存されます。 Experience Platformでは、アクティベーション時の同意検証を自動的にサポートします。 詳しくは、[ セグメント化サービスに関する FAQ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/faq#consent){target="_blank"} を参照してください。

または、コンポジションキャンバスで「プロファイルを保存」アクティビティを使用してプロファイルエンリッチメントを作成すると、結果のエンリッチメントがプロファイル対応のスキーマとプロファイル対応のデータセットとしてExperience Platformに保存されます。 既存のプロファイルの場合、使用可能な同意属性はアクティブ化中に自動的に適用されます。 新規プロファイルの場合、プロファイルの取り込み時に指定された同意属性がアクティブ化時に自動的に適用されます。 プロファイルに対する同意の適用について詳しくは、[ 同意および環境設定フィールドグループガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/consents){target="_blank"} を参照してください。

同意の適用について詳しくは、[ ポリシー管理 UI ガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide#consent-policy){target="_blank"} を参照してください。

## データライフサイクル {#data-lifecycle}

Federated Audience Composition は、どのデータウェアハウスのカスタマーデータも保存 **しないので** Experience Platformを使用してデータライフサイクルを処理できます。 高度なデータライフサイクル管理を使用すると、データセットとレコードレベルの両方でデータライフサイクルを管理できます。

例えば、コンポジションキャンバスで保存アクティビティブロックを使用してオーディエンスを作成すると、結果オーディエンスが外部オーディエンスとしてExperience Platformのデータレイクに保存されます。 このデータは Federated Audience Composition に保存 **れていないので** Audience Portal でオーディエンスが削除されると、オーディエンスデータと対応するデータセットは自動的に削除されます。

または、コンポジションキャンバスで「プロファイルを保存」アクティビティを使用してプロファイルエンリッチメントを作成すると、結果のエンリッチメントがプロファイル対応のスキーマとプロファイル対応のデータセットとしてExperience Platformに保存されます。 その結果、データライフサイクルを使用してプロファイルにアクセスし、クリーンアップできます。

データライフサイクルの使用について詳しくは、[ データライフサイクルの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/data-lifecycle/home){target="_blank"} を参照してください。

## データ使用ラベル {#data-usage-labels}

データ使用ラベルを使用すると、データに適用されるガバナンスポリシーに基づいて、データセットとフィールドを分類できます。 コンポジションを使用してオーディエンスを作成したら、結果のスキーマに適切なデータラベルを適用して、必要な使用制限に従っていることを確認できます。

データラベルの使用について詳しくは、[ データ使用ラベルの概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview){target="_blank"} を参照してください。

## 暗号化 {#encryption}

柔軟なオーディエンス構成は、保存データ暗号化、転送中データ暗号化、顧客管理キーによる暗号化を提供します。

保存データは、Federated Audience Composition 内で使用される顧客データを指します。 データはクラウドサービスプロバイダーによって暗号化され、暗号化された形式で Federated Audience Composition で使用されます。

送信中のデータとは、Federated Audience Composition でコンポーネント間を移動する際の顧客データを指します。 データは、HTTPS 経由で TLS 1.3 を使用する Federated Audience Composition コンポーネント全体を通じて暗号化されたままになります。

Adobeでのデータ暗号化の処理方法について詳しくは、[Experience Platformでのデータ暗号化 ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption){target="_blank"} に関するガイドを参照してください。

### 顧客管理キー {#customer-managed-keys}

顧客管理キーを使用すると、独自の暗号化キーを使用してデータを暗号化できるので、データを制御できます。 Federated Audience Composition は顧客データを保存 **ないので** 結果として得られるオーディエンスとエンリッチメントでは顧客管理キーを直接使用できます。キーはExperience Platformのデータレイクに保存されるからです。

顧客管理キーについて詳しくは、[ 顧客管理キーガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview){target="_blank"} を参照してください。

## 監査ログ {#audit-log}

Federated Audience Composition で実行されたすべての作成、読み取り、更新、削除の操作は、監査記録に記録されます。 この監査ログを使用して、これらのアクションを追跡し、アカウンタビリティを適用し、コンプライアンス監査をサポートできます。

詳しくは、[ 監査記録の概要 ](/help/admin/audit-trail.md){target="_blank"} を参照してください。

## アクセス制御 {#access-control}

Federated Audience Composition へのアクセスは、フィールドレベルと役割ベースのレベルの両方で制御できます。 これらのアクセス制御を使用して、データガバナンスポリシーを適用し、機密情報の漏洩を制限し、アクセスをユーザーの責任に合わせることができます。

Federated Audience Composition のアクセス制御の詳細については、[Access Federated Audience Composition ガイド ](/help/start/feature-access.md){target="_blank"} を参照してください。

## データのローカリゼーション {#data-localization}

Federated Audience Composition には顧客データは保存 **れません**。 その結果、データを同じ領域に保持するために、外部データベースを一致するサンドボックス領域と **のみ** 接続する必要があります。 別の地域のデータベースをサンドボックスに接続した場合、Adobeはデータのローカライゼーションを **担当しません**。

## 次の手順 {#next-steps}

このガイドを読むことで、データガバナンス、プライバシーコンプライアンス、同意の実施、データライフサイクル管理、アクセス制御など、Federated Audience Composition で使用されるプライバシーとセキュリティの機能について理解が深まりました。
