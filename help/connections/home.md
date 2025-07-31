---
audience: end-user
title: 連合データベースとの接続の作成および管理
description: 連合データベースとの接続の作成および管理方法について説明します
exl-id: ab65cd8a-dfa0-4f09-8e9b-5730564050a1
source-git-commit: 0fad4079df8efb2ed249a3b82703acf658ca2e72
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 13%

---

# 接続の作成 {#connections-fdb}

>[!AVAILABILITY]
>
>接続にアクセスするには、次のいずれかの権限が必要です。
>
>-**連合データベースの管理**
>>-**連合データベースの表示**
>
>必要な権限について詳しくは、[アクセス制御ガイド](/help/governance-privacy-security/access-control.md)を参照してください。

Experience Platform Federated Audience Composition を使用すると、サードパーティのデータウェアハウスからオーディエンスを作成および強化し、それらのオーディエンスをAdobe Experience Platformに読み込むことができます。

## サポートされているデータベース {#supported-databases}

連合データベースとAdobe Experience Platformを使用するには、まず 2 つのソース間の接続を確立する必要があります。 Federated Audience Composition を使用すると、次のデータベースに接続できます。

* Amazon Redshift
* Azure Synapse Analytics
* Databricks
* Google BigQuery
* Microsoft Fabric
* Oracle
* Snowflake
* Vertica Analytics

## 接続を作成 {#create}

接続を作成するには、「Federated data」セクション内で **[!UICONTROL Federated databases]** を選択します。

![ 左側のナビゲーション内で「Federated Databases」ボタンがハイライト表示されている様子。](assets/home/select-federated.png){zoomable="yes" width="70%" align="center"}

「連合データベース」セクションが表示されます。 「**[!UICONTROL 連合データベースを追加]**」を選択して、接続を作成します。

![ 連合データベースの表示ページ内で「連合データベースを追加」ボタンがハイライト表示されている様子。](assets/home/add-federated.png){zoomable="yes" width="70%" align="center"}

接続プロパティポップオーバーが表示されます。 接続に名前を付けたり、作成するデータベースのタイプを選択したりできます。

![ 連合データベースのタイプが表示されます。](assets/home/select-type.png){zoomable="yes" width="70%" align="center"}

タイプを選択すると、「**[!UICONTROL 詳細]**」セクションが表示されます。 このセクションは、以前に選択したデータベース・タイプに基づいて異なります。

>[!BEGINTABS]

>[!TAB Amazon Redshift]

>[!AVAILABILITY]
>
>サポートされているのは、Amazon Redshift AWS、Amazon Redshift Spectrum、Amazon Redshift Serverless のみです。

Amazon Redshift を選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | データソースの名前。 |
| アカウント | アカウントのユーザー名。 |
| パスワード | アカウントのパスワード。 |
| データベース | データベースの名前。 サーバー名で指定した場合は、このフィールドを空白にできます。 |
| 作業スキーマ | ワークテーブルに使用するデータベースのスキーマの名前。 この機能について詳しくは、[Amazon スキーマのドキュメント ](https://docs.aws.amazon.com/ja_jp/redshift/latest/dg/r_Schemas_and_tables.html){target="_blank"} を参照してください。<br/><br/>**注意：** このスキーマへの接続に必要な権限がある場合は、一時的なデータ処理に使用されるスキーマを含め、データベースの任意のスキーマを使用できます。 ただし、複数のサンドボックスを同じデータベースに接続する場合は、異なる作業スキーマを使用する **必須** です。 |

>[!TAB Azure Synapse Analytics]

Azure Synapse Analytics を選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | Azure Synapse サーバーの URL。 |
| アカウント | Azure Synapse アカウントのユーザー名。 |
| パスワード | Azure synapse アカウントのパスワード。 |
| データベース | データベースの名前。 サーバー名で指定した場合は、このフィールドを空白にできます。 |
| オプション | 接続の追加オプション。 Azure Synapse Analytics の場合は、コネクタでサポートされている認証の種類を指定できます。 現在、Federated Audience Composition は `ActiveDirectoryMSI` をサポートしています。 接続文字列について詳しくは、[Microsoftのドキュメントにある接続文字列の例 ](https://learn.microsoft.com/ja-jp/sql/connect/odbc/using-azure-active-directory?view=sql-server-ver15#example-connection-strings){target="_blank"} を参照してください。 |

>[!TAB Databricks]

>[!NOTE]
>
>プライベートリンクを介した外部 Databricks データウェアハウスへの安全なアクセスがサポートされています。これには、プライベートリンク経由で Amazon Web Services（AWS）でホストされている Databricks データベースへの安全な接続と、VPN 経由で Microsoft Azure でホストされている Databricks データベースへの安全な接続が含まれます。安全なアクセスの設定について詳しくは、アドビ担当者にお問い合わせください。

データブロックを選択すると、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | Databricks サーバーの名前。 |
| HTTP パス | クラスターまたはウェアハウスへのパス。 パスについて詳しくは、[ 接続の詳細に関する Databricks ドキュメント ](https://docs.databricks.com/aws/en/integrations/compute-details){target="_blank"} を参照してください。 |
| パスワード | Databricks サーバーのアクセストークンです。 この値について詳しくは、[ 個人用アクセストークンに関する Databricks ドキュメント ](https://docs.databricks.com/aws/en/dev-tools/auth/pat){target="_blank"} を参照してください。 |
| カタログ | Databricks カタログの名前。 Databricks のカタログについて詳しくは、[Databricks のカタログに関するドキュメント ](https://docs.databricks.com/aws/en/catalogs/){target="_blank"} を参照してください |
| 作業スキーマ | ワークテーブルに使用するデータベーススキーマの名前。 <br/><br/>**注意：** このスキーマへの接続に必要な権限がある場合は、一時的なデータ処理に使用されるスキーマを含む **任意** スキーマをデータベースから使用できます。 ただし、複数のサンドボックスを同じデータベースに接続する場合は、異なる作業スキーマを使用する **必須** です。 |
| オプション | 接続の追加オプション。 使用可能なオプションを次の表に示します。 |

データベースの場合、次の追加オプションを設定できます。

| オプション | 説明 |
| ------- | ----------- |
| TimeZoneName | 使用するタイムゾーンの名前。 この値は、`TIMEZONE` セッションパラメーターを表します。 タイムゾーンについて詳しくは、[ タイムゾーンに関する Databricks のドキュメント ](https://docs.databricks.com/aws/en/sql/language-manual/parameters/timezone#:~:text=The%20system%20default%20is%20UTC%20.){target="_blank"} を参照してください。 |

>[!TAB Google BigQuery]

Google BigQuery を選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サービスアカウント | サービスアカウントのメールアドレス。 詳しくは、[Google Cloud Service アカウントのドキュメント ](https://cloud.google.com/iam/docs/service-accounts-create){target="_blank"} を参照してください。 |
| プロジェクト | プロジェクトの ID。 詳しくは、[Google Cloud プロジェクトのドキュメント ](https://cloud.google.com/resource-manager/docs/creating-managing-projects){target="_blank"} を参照してください。 |
| データセット | データセットの名前。 詳しくは、[Google Cloud データセットのドキュメント ](https://cloud.google.com/bigquery/docs/datasets-intro){target="_blank"} を参照してください。 |
| キーファイルのパス | サーバーに対するキーファイル。 サポートされているファイルは `json` のみです。 |
| オプション | 接続の追加オプション。 使用可能なオプションを次の表に示します。 |

Google BigQuery の場合、次の追加オプションを設定できます。

| オプション | 説明 |
| ------- | ----------- |
| ProxyType | BigQuery への接続に使用するプロキシのタイプ。 サポートされる値は、`HTTP`、`http_no_tunnel`、`socks4`、`socks5` です。 |
| ProxyHost | プロキシに到達できるホスト名または IP アドレス。 |
| ProxyUid | プロキシが実行されているポート番号。 |
| ProxyPwd | プロキシのパスワード。 |
| bgpath | **メモ：** これは、**一括読み込みツール** （Cloud SDK）にのみ適用されます。 <br/><br/> サーバー上の Cloud SDK bin ディレクトリへのパス。 `google-cloud-sdk` ディレクトリを別の場所に移動した場合、または PATH 変数を使用したくない場合にのみ、これを設定する必要があります。 |
| GCloudConfigName | **メモ：** これは、バージョン 7.3.4 より上の **bulk-load tool** （Cloud SDK）にのみ適用されます。<br/><br/> データを読み込むためのパラメーターを保存する設定の名前。 デフォルトでは、この値は `accfda` です。 |
| GCloudDefaultConfigName | **注意：** これは、バージョン 7.3.4 より前の **bulk-load tool** （Cloud SDK）にのみ適用されます。<br/><br/> データを読み込むためのメイン設定を再作成する一時設定の名前。 デフォルトでは、この値は `default` です。 |
| GCloudRecreateConfig | **メモ：** これは、バージョン 7.3.4 より上の **bulk-load tool** （Cloud SDK）にのみ適用されます。<br/><br/> 一括読み込みメカニズムでGoogle Cloud SDK設定を自動的に再作成、削除、変更するかどうかを指定できるブール値です。 この値を `false` に設定した場合、一括読み込みメカニズムはマシン上の既存の設定を使用してデータを読み込みます。 この値が `true` に設定されている場合は、設定が正しく設定されていることを確認します。正しく設定されていない場合は、`No active configuration found. Please either create it manually or remove the GCloudRecreateConfig option` エラーが表示され、ロードメカニズムがデフォルトのロードメカニズムに戻ります。 |

>[!TAB Microsoft ファブリック ]

Microsoft Fabric を選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | Microsoft Fabric サーバーの URL。 |
| アプリケーション ID | Microsoft Fabric のアプリケーション ID。 アプリケーション ID について詳しくは、アプリケーション設定に関する [Microsoft Fabric ドキュメント ](https://learn.microsoft.com/en-us/fabric/workload-development-kit/create-entra-id-app){target="_blank"} を参照してください。 |
| クライアントシークレット | アプリケーションのクライアント秘密鍵。 クライアントシークレットの詳細については、[ アプリケーション設定に関するMicrosoft Fabric ドキュメント ](https://learn.microsoft.com/en-us/fabric/workload-development-kit/create-entra-id-app#step-8-generate-a-secret-for-your-application){target="_blank"} を参照してください。 |
| オプション | 接続の追加オプション。 使用可能なオプションを次の表に示します。 |

Microsoft Fabric の場合、次のオプションを追加で指定できます。

| オプション | 説明 |
| ------ | ----------- |
| 認証 | コネクタが使用する認証のタイプ。 サポートされる値：`ActiveDirectoryMSI`。 詳しくは、[ ウェアハウスの接続性に関するMicrosoft ドキュメント ](https://learn.microsoft.com/en-us/fabric/data-warehouse/connectivity){target="_blank"} を参照してください。 |

>[!TAB Oracle]

>[!IMPORTANT]
>
>Oracle データベースコネクタは、現在 **のみ** オーディエンスの作成およびオーディエンスのエンリッチメントのユースケースに使用できます。
>
>また、Oracle データベースを設定する前に、Adobe カスタマーケア担当者にお問い合わせください。

Oracleを選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | Oracle サーバーの URL。 |
| アカウント | アカウントのユーザー名。 |
| パスワード | アカウントのパスワード。 |

>[!TAB Snowflake]

>[!NOTE]
>
>プライベートリンクを介した外部 Snowflake データウェアハウスへの安全なアクセスがサポートされています。Snowflake アカウントは、Amazon Web Services（AWS）または Azure でホストされ、連合オーディエンス構成環境と同じ地域に配置されている必要があります。Snowflake アカウントへの安全なアクセスの設定について詳しくは、アドビ担当者にお問い合わせください。

Snowflakeを選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | サーバーの名前。 |
| ユーザー | アカウントのユーザー名。 |
| パスワード | アカウントのパスワード。 |
| データベース | データベースの名前。 サーバー名で指定した場合は、このフィールドを空白にできます。 |
| 作業スキーマ | ワークテーブルに使用するデータベーススキーマの名前。 <br/><br/>**注意：** このスキーマへの接続に必要な権限がある場合は、一時的なデータ処理に使用されるスキーマを含む **任意** スキーマをデータベースから使用できます。 ただし、複数のサンドボックスを同じデータベースに接続する場合は、異なる作業スキーマを使用する **必須** です。 |
| 秘密鍵 | データベース接続の秘密鍵。 ローカルシステムから `.pem` ファイルをアップロードできます。 |
| オプション | 接続の追加オプション。 使用可能なオプションを次の表に示します。 |

Snowflakeの場合、次の追加オプションを設定できます。

| オプション | 説明 |
| ------- | ----------- |
| workschema | ワークテーブルに使用するデータベーススキーマの名前。 |
| TimeZoneName | 使用するタイムゾーンの名前。 この値は、`TIMEZONE` セッションパラメーターを表します。 デフォルトでは、システムタイムゾーンが使用されます。 タイムゾーンについて詳しくは、[ タイムゾーンに関するSnowflake ドキュメント ](https://docs.snowflake.com/en/sql-reference/parameters#timezone){target="_blank"} を参照してください。 |
| WeekStart | 週の開始日。 この値は、`WEEK_START` セッションパラメーターを表します。 週開始について詳しくは、週開始パラメーターの [Snowflake ドキュメントを参照してください ](https://docs.snowflake.com/en/sql-reference/parameters#week-start){target="_blank"} |
| UseCachedResult | Snowflakeのキャッシュされた結果を使用するかどうかを指定するブール値。 この値は、`USE_CACHED_RESULTS` セッションパラメーターを表します。 デフォルトでは、この値は true に設定されています。 このパラメーターについて詳しくは、[ 結果の保持に関するSnowflakeのドキュメント ](https://docs.snowflake.com/en/user-guide/querying-persisted-results){target="_blank"} を参照してください。 |
| bulkThreads | Snowflakeのバルクローダーに使用するスレッドの数。 追加されるスレッドが多いほど、大きな一括読み込みのパフォーマンスが向上します。 デフォルトでは、この値は 1 に設定されています。 |
| chunkSize | 各バルクローダーのチャンクのファイルサイズ。 より多くのスレッドと同時に使用すると、一括読み込みのパフォーマンスを向上させることができます。 デフォルトでは、この値は 128 MB に設定されています。 チャンクサイズについて詳しくは、[ データファイルの準備に関するSnowflake ドキュメント ](https://docs.snowflake.com/en/user-guide/data-load-considerations-prepare){target="_blank"} を参照してください。 |
| StageName | 事前にプロビジョニングされた内部ステージング環境の名前。 これは、新しい一時ステージを作成する代わりに、一括読み込みで使用できます。 |

>[!TAB Vertica Analytics]

Vertica Analyticsを選択した後、次の詳細を追加できます。

| フィールド | 説明 |
| ----- | ----------- |
| サーバー | Vertica Analytics サーバーの URL。 |
| アカウント | アカウントのユーザー名。 |
| パスワード | アカウントのパスワード。 |
| データベース | データベースの名前。 サーバー名で指定した場合は、このフィールドを空白にできます。 |
| 作業スキーマ | ワークテーブルに使用するデータベーススキーマの名前。 <br/><br/>**注意：** このスキーマへの接続に必要な権限がある場合は、一時的なデータ処理に使用されるスキーマを含む **任意** スキーマをデータベースから使用できます。 ただし、複数のサンドボックスを同じデータベースに接続する場合は、異なる作業スキーマを使用する **必須** です。 |
| オプション | 接続の追加オプション。 使用可能なオプションを次の表に示します。 |

Vertica Analyticsの場合、次の追加オプションを設定できます。

| オプション | 説明 |
| ------- | ----------- |
| TimeZoneName | 使用するタイムゾーンの名前。 この値は、`TIMEZONE` セッションパラメーターを表します。 タイムゾーンについて詳しくは、タイムゾーンに関する [Vertica Analyticsのドキュメントを参照してください ](https://docs.vertica.com/24.1.x/en/admin/configuring-db/config-procedure/using-time-zones-with/){target="_blank"} |

>[!ENDTABS]

接続の詳細を追加した後、次の追加設定に注意してください。

>[!NOTE]
>
>特定のデータベースに対して Federated Audience Composition を使用するには、そのデータベースに関連付けられている IP アドレスの **すべて** を許可リストに設定する必要があります。

| 設定 | 詳細 |
| -------- | ------- |
| 接続を有効化 | 接続を自動的に有効にするかどうかを指定するブール型の切り替えスイッチです。 |
| サーバー IP | データベースへの接続に許可リストに加えるする必要がある IP アドレスを表示するポップオーバー。 |
| 接続をテスト | 設定の詳細を確認できます。 |

**[!UICONTROL 関数をデプロイ]** を選択し、続いて **[!UICONTROL 追加]** を選択して、フェデレーテッド データベースとExperience Platform間の接続を最終決定できるようになりました。

