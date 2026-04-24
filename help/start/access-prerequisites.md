---
title: 連合オーディエンス構成の前提条件とガードレール
description: 連合オーディエンス構成の前提条件、権限およびガードレールについて説明します
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
TQID: https://experienceleague.adobe.com/VBIotVn1VyiFJChb3mM0VDLUSbG9aQOmbfGnfGgqvhU
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
subfeature_v2:
  - id: b75843fa-0a67-4a44-a6b1-cc627b0481dc
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: fda4d9d7b45833d7e080ae80f42b7ca5ce36b3ad
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 100%

---

# 前提条件とガードレール {#fac-access}

連合オーディエンス構成には、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。 この機能にアクセスするには、連合オーディエンス構成アドオンを購入しておく必要があります。

>[!AVAILABILITY]
>
>アドビからウェルカムメール通知を受信した後、インターフェイスが更新され、機能が使用可能になるまで、さらに数時間かかる場合があります。

## サポートされているシステム {#supported-systems}

連合オーディエンス構成は、次のクラウドウェアハウスをサポートしています。

* Amazon Redshift
* Azure Synapse
* Databricks
* Google BigQuery
* Snowflake
* Vertica Analytics
* Microsoft Fabric

これらのシステムとの接続を作成する方法について詳しくは、[接続の概要](../connections/home.md)を参照してください。

## サンドボックス

連合オーディエンス構成を購入すると、2 つのサンドボックスを使用できます。 その他のサンドボックスプロビジョニングリクエストについて詳しくは、アドビ担当者にお問い合わせください。

アクティブな連合オーディエンス構成サンドボックスのリストを表示するには、次の手順に従います。

1. 連合オーディエンス構成から、**[!UICONTROL 管理]**&#x200B;の下にある&#x200B;**[!UICONTROL ライセンス使用状況]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL データ取り出しの合計量]**&#x200B;の ![](assets/do-not-localize/Smock_InfoOutline_18_N.svg) アイコンを選択して、サンドボックスのプロパティにアクセスします。

   ![](assets/sandbox_1.png)

1. サンドボックスに関する情報がプロパティポップオーバーに表示されます。

   ![](assets/sandbox_2.png)

## 権限 {#permissions}

連合オーディエンス構成にアクセスするには、購入時に作成されたサンドボックス固有の製品プロファイルにユーザーを追加し、**[!UICONTROL 連合データを管理]**&#x200B;権限を割り当てる必要があります。 [詳細情報](/help/governance-privacy-security/access-control.md)

## IP 許可リスト {#ip}

連合オーディエンス構成でデータベースに安全にアクセスできるようにするには、データベースにアクセスする連合オーディエンス構成サーバーの IP アドレスを承認する必要があります。 これらの IP アドレスは、Adobe Experience Platform ユーザーインターフェイスで連合データベースを追加する際に表示されます。 [詳細情報](../connections/home.md)

連合オーディエンス構成のアクセス権を付与するには、これらの IP アドレスを許可リストに追加します。

## 結合ポリシー {#merge-policies}

サンドボックスで&#x200B;**データセットの優先順位**&#x200B;結合ポリシーを使用している場合は、アドビカスタマーケアに連絡して、`Halos UPS` のデータセットを結合ポリシーに追加してください。

結合ポリシーについて詳しくは、[結合ポリシーの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/merge-policies/overview)を参照してください。

## ガードレールと制限 {#fac-guardrails}

* 連合オーディエンス構成に適用されるエンタイトルメント、製品の制限、パフォーマンスガードレールの一覧について詳しくは、[Adobe Real-time Customer Data Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}を参照してください。

* 連合オーディエンス構成は、ファイルサイズが 1 GB を超える大規模なオーディエンスのエクスポートをサポートしています。 最適なパフォーマンスを得るために、推奨される最大ファイルサイズは 20 GB までです。
