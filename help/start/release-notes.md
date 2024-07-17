---
title: Federated Audience Composition の新機能
description: 最新のアップデートとリリースノート
badge: label="限定提供" type="Informative"
source-git-commit: 082bdccd7bc53d6c7520a778b65b2127a62e28a4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 14%

---


# リリースノート {#rn-new}

## Federated Audience Composition （LA） {#rn-la}

Federated Audience Composition は、パーソナライゼーションのユースケースを強化するために、エンタープライズデータウェアハウスへの柔軟なアクセスと拡張リーチを提供するアドオンです。

Federated Audience Composition を使用すると、企業は様々なユースケースでの使用率を高めるためにデータを作成できます。 この新しいアプローチでは、[Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/home){target="_blank"} または [Adobe Journey Optimizer](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} のユーザーとして、既存の Data Warehouse からデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで強化できます。

データセットやオーディエンスをAdobe Experience Platformに取り込む代わりに、Federated Audience コンポジションを使用して、特定のセグメント化やアクティベーションのユースケースに必要な特定のオーディエンスや属性をウェアハウスから取り出すことで、データウェアハウスからAdobe Experience Platformにコピーされるデータの量を減らし、機密データがウェアハウス外で保持されないようにすることができるようになりました。


>[!AVAILABILITY]
>
>Federated Audience Composition は現在、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。
>
>現時点では、Adobe **Healthcare Shield** および **Privacy and Security Shield** アドオン製品を購入したお客様は、この機能を使用できません。


## 前提条件とガードレール {#rn-guardrails}

* Data Warehouse へのアクセスを有効にし、Federated Audience Composition を使用するには、IP アドレスが許可リストに追加されている必要があります。 Adobeに IP アドレスを追加するには、許可リスト担当者にお問い合わせください。

* エンタイトルメント、製品の制限、パフォーマンスガードレールの一覧については、[Adobe Real-time Customer Data Platform ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails){target="_blank"} を参照してください。
