---
title: プライベート接続を使用した連合オーディエンス構成への接続
description: プライベート接続を使用して連合オーディエンス構成を設定し、接続する方法について説明します。これには、PrivateLink やサイト間 VPN が含まれます。
source-git-commit: c4096e842caf383dee2e43bc80e18e1ac2036faf
workflow-type: ht
source-wordcount: '1634'
ht-degree: 100%

---


# 連合オーディエンス構成へのプライベート接続

連合オーディエンス構成では、複数のデータベースとのプライベート接続をサポートします。プライベート接続を使用すると、パブリックインターネットを経由することなく、顧客がホストするデータウェアハウスに接続できます。

## サポートされているデータベース {#supported-databases}

次のデータベースでは、連合オーディエンス構成へのプライベート接続をサポートします。

| データベース | クラウド | プライベート接続タイプ |
| -------- | ----- | ----------------------- |
| [!DNL Snowflake] | [!DNL Amazon Web Services]（AWS） | AWS PrivateLink（VPC インターフェイスエンドポイント） |
| [!DNL Snowflake] | [!DNL Microsoft Azure] | Azure PrivateLink（プライベートエンドポイント） |
| [!DNL Amazon Redshift] | [!DNL Amazon Web Services]（AWS） | AWS PrivateLink（管理 VPC エンドポイント） |
| [!DNL Databricks] | [!DNL Amazon Web Services]（AWS） | AWS PrivateLink（VPC インターフェイスエンドポイント） |
| [!DNL Databricks] | [!DNL Microsoft Azure] | サイト間 VPN |
| [!DNL Databricks] | [!DNL Google Cloud Platform]（GCP） | サイト間 VPN |
| [!DNL Azure Synapse Analytics] | [!DNL Microsoft Azure] | サイト間 VPN |
| [!DNL Google BigQuery] | [!DNL Google Cloud Platform]（GCP） | サイト間 VPN |

## Snowflake {#snowflake}

>[!AVAILABILITY]
>
>[!DNL Snowflake] とのプライベート接続を使用するには、[!DNL Snowflake] の Business Critical 層以上を使用している&#x200B;**必要**&#x200B;があります。[!DNL Snowflake] とのプライベート接続について詳しくは、[Snowflake ドキュメントのプライベート接続ガイド](https://docs.snowflake.com/ja/user-guide/private-connectivity-inbound)を参照してください。

[!DNL Snowflake] とのプライベート接続の使用は、[!DNL Snowflake] インスタンスがどのクラウドプロバイダー上にあるかによって異なります。

### Amazon Web Services（AWS） {#snowflake-aws}

>[!IMPORTANT]
>
>続行する前に、アドビカスタマーケアから AWS アカウント ID を取得していることを確認してください。AWS アカウント ID を取得したら、[!DNL Snowflake] サポートに連絡し、[!DNL Snowflake] がお客様の AWS アカウントを認証して PrivateLink を使用できるようにしてください。

AWS アカウントが [!DNL Snowflake] での使用を認証されたら、VPC インターフェイスエンドポイントを取得できるように、`privatelink-vpce-id`、`privatelink-account-url`、`privatelink_ocsp-url` などの値を取得する必要があります。

[!DNL Snowflake] アカウントで ACCOUNTADMIN として次のコマンドを実行することで、これらの値を取得できます。

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

これらのコマンドを実行したら、完全な SQL 出力をアドビカスタマーケアに送信してください。これにより、アドビで VPC インターフェイスエンドポイントを作成できます。

AWS との PrivateLink 接続の作成について詳しくは、[AWS PrivateLink ガイド](https://docs.snowflake.com/ja/user-guide/admin-security-privatelink)を参照してください。

内部ステージング環境で PrivateLink を使用するために認証するには、アドビカスタマーケアに連絡して環境を有効にしてください。

内部ステージング環境用に AWS との PrivateLink 接続を作成する方法について詳しくは、[内部ステージ用の AWS VPC インターフェイスエンドポイントガイド](https://docs.snowflake.com/ja/user-guide/private-internal-stages-aws)を参照してください。

### Microsoft Azure {#snowflake-azure}

Microsoft Azure の場合、Azure プライベートエンドポイントを作成するには、`privatelink-pls-id`、`privatelink-account-url`、`privatelink_ocsp-url` などの値を取得する必要があります。

Snowflake アカウントで次のコマンドを実行して、これらの値を取得できます。

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

これらのコマンドを実行したら、完全な SQL 出力をアドビカスタマーケアに送信してください。これにより、アドビで Azure プライベートエンドポイントを作成できます。

アドビが Azure プライベートエンドポイントを作成したら、プライベートエンドポイントのリソース ID を取得できます。プライベートエンドポイントのリソース ID を取得したら、そのリソース ID を指定しながら、[!DNL Snowflake] サポートに連絡し、お客様の [!DNL Snowflake] アカウントの認証を依頼してください。

Azure との PrivateLink 接続の作成について詳しくは、[Azure PrivateLink ガイド](https://docs.snowflake.com/ja/user-guide/privatelink-azure)を参照してください。

内部ステージング環境で PrivateLink を使用するために認証するには、アドビカスタマーケアが提供する内部ステージリソース ID を指定しながら、[!DNL Snowflake] で次のコマンドを実行します。

`SELECT SYSTEM$AUTHORIZE_STAGE_PRIVATELINK_ACCESS('<internal-stage-private-endpoint-resource-id>');`

内部ステージング環境用に Azure との PrivateLink 接続を作成する方法について詳しくは、[内部ステージ用の Azure プライベートエンドポイントガイド](https://docs.snowflake.com/ja/user-guide/private-internal-stages-azure)を参照してください。

## Amazon Redshift {#amazon-redshift}

プロビジョニングされたクラスターと Redshift Serverless の両方では、連合オーディエンス構成を使用したプライベート接続をサポートします。

>[!IMPORTANT]
>
>開始する前に、アドビカスタマーケアに連絡し、Amazon Web Services（AWS）アカウント ID と Virtual Private Cloud（VPC）ID を受け取ってください。クロスアカウントエンドポイントへのアクセス権を取得するには、これらの値の&#x200B;**両方**&#x200B;が必要です。VPC へのアクセス権の付与について詳しくは、[VPC へのアクセス権の付与ガイド](https://docs.aws.amazon.com/ja_jp/redshift/latest/mgmt/managing-cluster-cross-vpc-console-grantor.html)を参照してください。

AWS と VPC ID の両方を取得したら、AWS Management Console に移動して、管理 VPC エンドポイントに対するクロスアカウントアクセス権を付与します。

プロビジョニングされたクラスターの場合は、**Redshift クラスター識別子**&#x200B;と&#x200B;**クラスター所有者の AWS アカウント ID** の両方の値に注意してください。Redshift Serverless の場合は、**ワークグループ名**&#x200B;と&#x200B;**所有者の AWS アカウント ID** の両方の値に注意してください。

これらの値を取得したら、その詳細をアドビカスタマーケアと共有して、アドビで管理 VPC エンドポイントを作成できるようにします。次に、アドビでは、**Redshift エンドポイント URL**、**Redshift JDBC URL**、**Redshift ODBC URL** の接続の詳細を共有します。

## Databricks {#databricks}

>[!AVAILABILITY]
>
>Databricks とのプライベート接続を使用するには、Databricks のエンタープライズプランを使用している&#x200B;**必要**&#x200B;があります。Databricks とのプライベート接続について詳しくは、[プライベートリンクの概念ガイド](https://docs.databricks.com/aws/ja/security/network/concepts/privatelink-concepts)を参照してください。

Databricks とのプライベート接続の使用は、Databricks インスタンスがどのクラウドプロバイダー上にあるかによって異なります。

### Amazon Web Services {#databricks-aws}

Amazon Web Services で設定する前に、アドビカスタマーケアに連絡し、Databricks をポイントするフロントエンド（インバウンド）の VPC インターフェイスエンドポイントを作成できるようにしてください。このエンドポイントは、連合オーディエンス構成から Databricks ワークスペースへの ODBC 接続を対象としています。

アドビカスタマーケアから VPC エンドポイント ID と AWS リージョンを取得したら、アドビから提供された情報を使用して VPC エンドポイントを登録する必要があります。

VPC エンドポイントを登録したら、Private Access Settings（PAS）オブジェクトを作成する必要があります。エンドポイントを作成する際、**プライベートアクセスレベル**&#x200B;を&#x200B;**エンドポイント**&#x200B;レベルに設定し、以前に作成した VPC エンドポイントを選択します。プライベートアクセス設定の作成について詳しくは、[インバウンド PrivateLink の設定ガイド](https://docs.databricks.com/aws/ja/security/network/front-end/front-end-private-connect#step-3-create-private-access-settings)を参照してください。

プライベートアクセス設定を指定したら、VPC エンドポイントをワークスペースに添付できます。PrivateLink を使用したワークスペースの作成について詳しくは、[インバウンド PrivateLink の設定ガイド](https://docs.databricks.com/aws/ja/security/network/front-end/front-end-private-connect#step-4-create-your-workspace-with-private-link-objects)を参照してください。

すべての設定が完了したので、Databricks ワークスペースの URL をアドビカスタマーケアと共有できます。Databricks ワークスペースの URL を共有したら、アドビではワークスペースのエンドポイントにリクエストをルーティングするために必要な DNS 設定を指定できます。

### Microsoft Azure {#databricks-azure}

サイト間 VPN は、アドビから Azure の Databricks ワークスペースに安全に接続するために使用されます。アドビにデータを安全に転送するための VPN トンネルを確立するには、Azure VPN Gateway を設定する必要があります。

Azure VPN Gateway と Databricks プライベート エンドポイントを設定したら、**Azure Virtual Network Gateway**、**Databricks プライベートエンドポイント IP**、**Databricks ワークスペース URL**、**AS 番号（ASN）**&#x200B;の詳細をアドビカスタマーケア担当者と共有してください。

これらの詳細を用いることで、アドビは接続に必要な VPN トンネルを確立できます。VPN トンネルを確立したら、アドビは **VPN トンネルのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、**AS 番号**&#x200B;を提供します。

これで、Azure VNet Gateway で VPN トンネルを設定できるようになりました。詳しくは、[VPN Gateway を使用した AWS と Azure の接続ガイド](https://learn.microsoft.com/ja-jp/azure/vpn-gateway/vpn-gateway-howto-aws-bgp)を参照してください。

### Google Cloud Platform {#databricks-gcp}

サイト間 VPN は、アドビから Google Cloud Platform の Databricks ワークスペースに安全に接続するために使用されます。アドビにデータを安全に転送するための VPN トンネルを確立するには、Google Cloud Platform High Availability VPN Gateway と Cloud Router を設定する必要があります。

GCP HA VPN Gateway と Cloud Router を設定したら、**GCP HA VPN Gateway**、**Databricks ワークスペース URL**、**Private Service Connect（PSC）IP**、**AS 番号（ASN）**&#x200B;の詳細をアドビカスタマーケア担当者と共有してください。

これらの詳細を用いることで、アドビは接続に必要な VPN トンネルを確立できます。VPN トンネルを確立したら、アドビは **VPN トンネルのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、**AS 番号**&#x200B;を提供します。

これで、Google Cloud Platform アカウントで VPN トンネルを設定できるようになりました。詳しくは、[HA VPN 接続の作成ガイド](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws?hl=ja)を参照してください。

## Azure Synapse Analytics {#azure-synapse}

Azure Synapse Analytics に接続するには、まず Azure Virtual Network Gateway と Synapse プライベートエンドポイントを作成する必要があります。Azure Virtual Network Gateway を使用すると、Azure Virtual Network と Synapse 間で暗号化されたトラフィックを送信できます。一方、Synapse プライベートエンドポイントを使用すると、プライベート接続を使用して安全にデータを転送できます。

Azure Virtual Network Gateway と Synapse プライベートエンドポイントを設定したら、**Azure Virtual Network Gateway**、**Synapse プライベートエンドポイント IP**、**Synapse ワークスペース URL**、**AS 番号（ASN）**&#x200B;の詳細をアドビカスタマーケア担当者と共有してください。

これらの詳細を用いることで、アドビは接続に必要な VPN トンネルを確立できます。VPN トンネルを確立したら、アドビでは **VPN トンネルのペアリング**、**事前共有キー**、**AS 番号**&#x200B;を提供します。

これで、Azure VNet Gateway で VPN トンネルを設定できるようになりました。詳しくは、[VPN Gateway を使用した AWS と Azure の接続ガイド](https://learn.microsoft.com/ja-jp/azure/vpn-gateway/vpn-gateway-howto-aws-bgp)を参照してください。

## Google BigQuery {#gbq}

Google Big Query に接続するには、まず Google Cloud Platform High Availability VPN Gateway と Cloud Router を作成する必要があります。

GCP HA VPN Gateway と Cloud Router を設定したら、**GCP HA VPN Gateway**、**Private Service Connect（PSC）IP**、**AS 番号（ASN）**&#x200B;の詳細をアドビカスタマーケア担当者と共有してください。

これらの詳細を用いることで、アドビは接続に必要な VPN トンネルを確立できます。VPN トンネルを確立したら、アドビは **VPN トンネルのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、**AS 番号**&#x200B;を提供します。

これで、Google Cloud Platform アカウントで VPN トンネルを設定できるようになりました。詳しくは、[HA VPN 接続の作成ガイド](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws?hl=ja)を参照してください。
