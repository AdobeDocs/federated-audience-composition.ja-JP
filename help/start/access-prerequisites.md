---
title: 連合オーディエンス構成の前提条件とガードレール
description: 連合オーディエンス構成の前提条件、権限およびガードレールについて説明します
exl-id: 661a838f-146e-4d68-bb2d-319827caee3a
source-git-commit: a9410b26629a39b27466ef587e2ff0a1122b9868
workflow-type: ht
source-wordcount: '322'
ht-degree: 100%

---

# 前提条件とガードレール {#fac-access}

連合オーディエンス構成には、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer **Prime** または **Ultimate** パッケージが必要です。この機能にアクセスするには、連合オーディエンス構成アドオンを購入しておく必要があります。

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

これらのシステムとの接続を作成する方法について詳しくは、[このページ](../connections/connections.md)を参照してください。

## サンドボックス

連合オーディエンス構成を購入すると、2 つのサンドボックスを使用できます。その他のサンドボックスプロビジョニングリクエストについて詳しくは、アドビ担当者にお問い合わせください。

アクティブな連合オーディエンス構成サンドボックスのリストを表示するには、次の手順に従います。

1. 連合オーディエンス構成から、**[!UICONTROL 管理]**&#x200B;の下にある&#x200B;**[!UICONTROL ライセンス使用状況]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL データ取り出しの合計量]**&#x200B;の ![](assets/do-not-localize/Smock_InfoOutline_18_N.svg) アイコンをクリックして、サンドボックスのプロパティにアクセスします。

   ![](assets/sandbox_1.png)

1. サンドボックスに関する情報がプロパティポップオーバーに表示されます。

   ![](assets/sandbox_2.png)

## 権限 {#permissions}

連合オーディエンス構成にアクセスするには、購入時に作成されたサンドボックス固有の製品プロファイルにユーザーを追加し、**[!UICONTROL 連合データを管理]**&#x200B;権限を割り当てる必要があります。[詳細情報](/help/governance-privacy-security/access-control.md)

## IP 許可リスト {#ip}

連合オーディエンス構成でデータベースに安全にアクセスできるようにするには、データベースにアクセスする連合オーディエンス構成サーバーの IP アドレスを承認する必要があります。これらの IP アドレスは、Adobe Experience Platform ユーザーインターフェイスで連合データベースを追加する際に表示されます。[詳細情報](../connections/connections.md)

連合オーディエンス構成のアクセス権を付与するには、これらの IP アドレスを許可リストに追加します。

## ガードレールと制限 {#fac-guardrails}

* 連合オーディエンス構成に適用されるエンタイトルメント、製品の制限、パフォーマンスガードレールの一覧について詳しくは、[Adobe Real-time Customer Data Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/guardrails){target="_blank"}を参照してください。

* 連合オーディエンス構成は、ファイルサイズが 1 GB を超える大規模なオーディエンスのエクスポートをサポートしています。最適なパフォーマンスを得るために、推奨される最大ファイルサイズは 20 GB までです。
