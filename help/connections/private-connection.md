---
title: プライベート接続を使用して連合オーディエンス構成に接続する
description: プライベート接続を使用してFederated Audience Compositionを設定し、接続する方法について説明します。 これには、PrivateLinkやサイト間VPNが含まれます。
source-git-commit: c4096e842caf383dee2e43bc80e18e1ac2036faf
workflow-type: tm+mt
source-wordcount: '1634'
ht-degree: 0%

---


# Federated Audience Compositionへのプライベート接続

Federated Audience Compositionは、複数のデータベースとのプライベート接続をサポートします。 プライベート接続により、パブリックインターネットを経由することなく、顧客がホストするデータウェアハウスに接続できます。

## サポートされているデータベース {#supported-databases}

次のデータベースは、Federated Audience Compositionへのプライベート接続をサポートしています。

| データベース | クラウド | プライベート接続タイプ |
| -------- | ----- | ----------------------- |
| [!DNL Snowflake] | [!DNL Amazon Web Services] （AWS） | AWS PrivateLink （VPC インターフェイスエンドポイント） |
| [!DNL Snowflake] | [!DNL Microsoft Azure] | Azure PrivateLink （プライベートエンドポイント） |
| [!DNL Amazon Redshift] | [!DNL Amazon Web Services] （AWS） | AWS PrivateLink （Managed VPC エンドポイント） |
| [!DNL Databricks] | [!DNL Amazon Web Services] （AWS） | AWS PrivateLink （VPC インターフェイスエンドポイント） |
| [!DNL Databricks] | [!DNL Microsoft Azure] | サイト間VPN |
| [!DNL Databricks] | [!DNL Google Cloud Platform] （GCP） | サイト間VPN |
| [!DNL Azure Synapse Analytics] | [!DNL Microsoft Azure] | サイト間VPN |
| [!DNL Google BigQuery] | [!DNL Google Cloud Platform] （GCP） | サイト間VPN |

## Snowflake {#snowflake}

>[!AVAILABILITY]
>
>[!DNL Snowflake]とのプライベート接続を使用するには、**少なくとも**&#x200B;が[!DNL Snowflake]のBusiness Critical層以上である必要があります。 [!DNL Snowflake]とのプライベート接続について詳しくは、[Snowflake ドキュメント ](https://docs.snowflake.com/en/user-guide/private-connectivity-inbound)のプライベート接続ガイドを参照してください。

[!DNL Snowflake]とのプライベート接続を使用するには、[!DNL Snowflake] インスタンスがどのクラウドプロバイダーに属しているかによって異なります。

### Amazon Web Services（AWS） {#snowflake-aws}

>[!IMPORTANT]
>
>続行する前に、Adobe カスタマーケアからAWS アカウント IDを取得していることを確認してください。 AWS アカウント IDを取得したら、[!DNL Snowflake] サポートにお問い合わせいただき、[!DNL Snowflake]がPrivateLinkの使用をAWS アカウントに許可できるようにしてください。

AWS アカウントが[!DNL Snowflake]での使用を許可されたら、`privatelink-vpce-id`、`privatelink-account-url`、`privatelink_ocsp-url`などの値を取得して、VPC インターフェイス エンドポイントを取得できるようにする必要があります。

これらの値を取得するには、[!DNL Snowflake] アカウントでACCOUNTADMINとして次のコマンドを実行します。

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

これらのコマンドを実行したら、SQL出力をAdobe カスタマーケアに送信して、AdobeでVPC インターフェイス エンドポイントを作成できるようにします。

AWSとのPrivateLink接続を作成する方法について詳しくは、[AWS PrivateLink ガイド ](https://docs.snowflake.com/en/user-guide/admin-security-privatelink)を参照してください。

内部ステージング環境でのPrivateLinkの使用を許可する場合は、Adobe カスタマーケアに連絡して環境を有効にしてください。

内部ステージング環境用にAWSとのPrivateLink接続を作成する方法について詳しくは、[内部ステージング用のAWS VPC インターフェイス エンドポイント ガイド ](https://docs.snowflake.com/en/user-guide/private-internal-stages-aws)を参照してください。

### Microsoft Azure {#snowflake-azure}

Microsoft Azureの場合、Azure プライベートエンドポイントを作成するには、`privatelink-pls-id`、`privatelink-account-url`、`privatelink_ocsp-url`などの値を取得する必要があります。

これらの値を取得するには、Snowflake アカウントで次のコマンドを実行します。

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

これらのコマンドを実行したら、SQL出力をAdobe カスタマーケアに送信して、AdobeでAzure プライベートエンドポイントを作成できるようにします。

AdobeがAzure プライベートエンドポイントを作成したら、プライベートエンドポイントリソース IDを取得できます。 プライベートエンドポイントリソース IDが取得できたので、[!DNL Snowflake] サポートに連絡して、リソース IDを提供しながら[!DNL Snowflake] アカウントを認証してください。

AzureとのPrivateLink接続を作成する方法について詳しくは、[Azure PrivateLink ガイド ](https://docs.snowflake.com/en/user-guide/privatelink-azure)を参照してください。

内部ステージング環境で使用するPrivateLinkを認証する場合は、Adobe カスタマーケアが提供する内部ステージリソース IDを指定しながら、[!DNL Snowflake]で次のコマンドを実行します。

`SELECT SYSTEM$AUTHORIZE_STAGE_PRIVATELINK_ACCESS('<internal-stage-private-endpoint-resource-id>');`

内部ステージング環境用にAzureとのPrivateLink接続を作成する方法について詳しくは、[内部ステージング用のAzure プライベートエンドポイント ガイド ](https://docs.snowflake.com/en/user-guide/private-internal-stages-azure)を参照してください。

## Amazon Redshift {#amazon-redshift}

プロビジョニングクラスターとRedshift Serverlessの両方で、Federated Audience Compositionによるプライベート接続がサポートされます。

>[!IMPORTANT]
>
>開始する前に、Adobe カスタマーケアに問い合わせて、Amazon Web Services（AWS）アカウント IDとVirtual Private Cloud （VPC） IDを受け取ってください。 クロスアカウントエンドポイントへのアクセスを取得するには、これらの値の&#x200B;**両方**&#x200B;が必要です。 VPCへのアクセス権の付与について詳しくは、[VPCへのアクセス権の付与ガイド ](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-cluster-cross-vpc-console-grantor.html)を参照してください。

AWSとVPC IDの両方を取得したら、AWS Management Consoleに移動して、管理対象のVPC エンドポイントに対するクロスアカウントアクセス権を付与します。

プロビジョニングされたクラスターの場合は、**Redshift クラスター識別子**&#x200B;と&#x200B;**クラスターオーナーのAWS アカウント ID**&#x200B;の両方の値に注意してください。 Redshift サーバーレスの場合は、**workgroup name**&#x200B;と&#x200B;**owner AWS アカウント ID**&#x200B;の両方の値に注意してください。

これらの値を取得したら、その詳細をAdobe カスタマーケアと共有して、Adobeで管理されたVPC エンドポイントを作成できるようにします。 次に、Adobeは次の接続の詳細を共有します。**Redshift エンドポイント URL**、**Redshift JDBC URL**、および&#x200B;**Redshift ODBC URL**。

## Databricks {#databricks}

>[!AVAILABILITY]
>
>Databricksとのプライベート接続を使用するには、Databricksのエンタープライズ プランに&#x200B;**アクセスしている必要があります。** Databricksとのプライベート接続について詳しくは、[ プライベートリンクの概念ガイド ](https://docs.databricks.com/aws/en/security/network/concepts/privatelink-concepts)を参照してください。

Databricksとのプライベート接続の使用は、Databricks インスタンスがどのクラウドプロバイダーを使用しているかによって異なります。

### Amazon Web Services {#databricks-aws}

Amazon Web Servicesを使用して設定する前に、Adobe カスタマーケアに連絡して、Databricksをポイントするフロントエンド（インバウンド）のVPC インターフェイス エンドポイントを作成できるようにしてください。 このエンドポイントでは、Databricks ワークスペースに対するFederated Audience CompositionのODBC接続について説明します。

Adobe カスタマーケアからVPC エンドポイント IDとAWS リージョンを取得したら、Adobeから提供される情報にVPC エンドポイントを登録する必要があります。

VPC エンドポイントを登録したら、Private Access Settings （PAS）オブジェクトを作成する必要があります。 エンドポイントを作成する場合、**プライベートアクセスレベル**&#x200B;を&#x200B;**エンドポイント** レベルに設定し、以前に作成したVPC エンドポイントを選択します。 プライベートアクセス設定の作成について詳しくは、[ インバウンド PrivateLinkの設定ガイド ](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-3-create-private-access-settings)を参照してください。

プライベートアクセス設定を設定したら、VPC エンドポイントをワークスペースにアタッチできます。 PrivateLinkを使用したワークスペースの作成について詳しくは、[ インバウンド PrivateLinkの設定ガイド ](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-4-create-your-workspace-with-private-link-objects)を参照してください。

すべての設定が完了したので、Databricks WorkspaceのURLをAdobe カスタマーケアと共有できます。 Databricks Workspace URLを共有すると、Adobeは、リクエストをWorkspace エンドポイントにルーティングするために必要なDNS設定を設定できます。

### Microsoft Azure {#databricks-azure}

サイト間VPNは、AdobeからAzureのDatabricks ワークスペースに安全に接続するために使用されます。 データをAdobeに安全に転送するために、Azure VPN ゲートウェイを設定してVPN トンネルを確立する必要があります。

Azure VPN GatewayとDatabricks プライベート エンドポイントを設定したら、次の詳細をAdobe カスタマーケア担当者にお知らせします。**Azure Virtual Network Gateway**、**Databricks Private Endpoint IP**、**Databricks Workspace URL**、および&#x200B;**Autonomous System Number （ASN）**。

これらの詳細により、Adobeは、接続に必要なVPN トンネルを確立できます。 VPN トンネルを確立すると、Adobeは&#x200B;**VPN-Tunnelのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、および&#x200B;**自律システム番号**&#x200B;を提供します。

Azure VNet GatewayでVPN トンネルを設定できるようになりました。 詳しくは、[VPN ゲートウェイ ガイドを使用してAWSとAzureを接続する](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-aws-bgp)を参照してください。

### Google Cloud Platform {#databricks-gcp}

サイト間VPNは、AdobeからGoogle Cloud Platform上のDatabricks ワークスペースに安全に接続するために使用されます。 Google Cloud Platform High Availability VPN ゲートウェイとCloud Routerを設定して、データをAdobeに安全に転送するためのVPN トンネルを確立する必要があります。

GCP HA VPN ゲートウェイとクラウドルーターを設定したら、次の詳細をAdobe カスタマーケア担当者にお知らせください。**GCP HA VPN ゲートウェイ**、**Databricks Workspace URL**、**Private Service Connect （PSC） IP**、および&#x200B;**Autonomous System Number （ASN）**。

これらの詳細により、Adobeは、接続に必要なVPN トンネルを確立できます。 VPN トンネルを確立すると、Adobeは&#x200B;**VPN-Tunnelのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、および&#x200B;**自律システム番号**&#x200B;を提供します。

Google Cloud Platform アカウントでVPN トンネルを設定できるようになりました。 詳しくは、[HA VPN接続の作成ガイド ](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws)を参照してください。

## Azure Synapse Analytics {#azure-synapse}

Azure Synapse Analyticsに接続するには、まずAzure Virtual Network GatewayとSynapse プライベート エンドポイントを作成する必要があります。 Azure Virtual Network Gatewayを使用すると、暗号化されたトラフィックをAzure仮想ネットワーク間でSynapseに送信できます。また、Synapse プライベートエンドポイントを使用すると、データを安全に送信するためのプライベート接続を使用できます。

Azure Virtual Network GatewayとSynapse プライベート エンドポイントを設定したら、次の詳細をAdobe カスタマーケア担当者にお知らせします。**Azure Virtual Network Gateway**、**Synapse Private Endpoint IP**、**Synapse Workspace URL**、および&#x200B;**自動サービス番号（ASN）**。

これらの詳細により、Adobeは、接続に必要なVPN トンネルを確立できます。 VPN トンネルを確立すると、Adobeは&#x200B;**VPN-Tunnel ペアリング**、**事前共有キー**&#x200B;および&#x200B;**自律システム番号**&#x200B;を提供します。

Azure VNet GatewayでVPN トンネルを設定できるようになりました。 詳しくは、[VPN ゲートウェイ ガイドを使用してAWSとAzureを接続する](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-aws-bgp)を参照してください。

## Google BigQuery {#gbq}

Google Big Queryに接続するには、まずGoogle Cloud Platform High Availability VPN ゲートウェイとクラウドルーターを作成する必要があります。

GCP HA VPN ゲートウェイとクラウドルーターを設定したら、次の詳細をAdobe カスタマーケア担当者にお知らせください。**GCP HA VPN ゲートウェイ**、**Private Service Connect （PSC） IP**、および&#x200B;**Autonomous System Number （ASN）**。

これらの詳細により、Adobeは、接続に必要なVPN トンネルを確立できます。 VPN トンネルを確立すると、Adobeは&#x200B;**VPN-Tunnelのパブリック IP アドレスとプライベート IP アドレス**、**事前共有キー**、および&#x200B;**自律システム番号**&#x200B;を提供します。

Google Cloud Platform アカウントでVPN トンネルを設定できるようになりました。 詳しくは、[HA VPN接続の作成ガイド ](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws)を参照してください。
