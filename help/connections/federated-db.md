---
audience: end-user
title: 連合データベースの基本を学ぶ
description: 連合データベースを作成および管理する方法を学ぶ
badge: label="限定提供" type="Informative"
source-git-commit: 2608a9864c605ea127183dd1658932cfc8a18cf8
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 17%

---

# 連合データベースの基本を学ぶ {#federated-db}

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_menu"
>title="連合データベース"
>abstract="この画面には、連合データベースへの既存の接続がリストされます。 新しい接続を作成するには、「**[!UICONTROL 連合データベースを追加]**」ボタンをクリックします。"

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_properties"
>title="連合データベースのプロパティ"
>abstract="新しい連合データベースの名前を入力し、このタイプを選択します。"

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_details"
>title="連合データベースの詳細"
>abstract="新しい連合データベースに接続するための設定を入力します。 「**[!UICONTROL 接続をテスト]**」ボタンを使用して、設定を検証します。"

外部データベースへの接続を作成、設定、テスト、保存します。



サポートされる外部データベース：

* Amazon Redshift
* Azure synapse
* Google BigQuery
* Snowflake
* Vertica Analytics

## Snowflake {#snowflake}

連合データベースを使用して、外部データベースに保存されている情報を処理します。 Snowflakeへのアクセスを設定するには、次の手順に従います。

1. **[!UICONTROL Federated data]** メニューで、「**[!UICONTROL Federated databases]**」を選択します。

1. **[!UICONTROL 連合データベースを追加]** をクリックします。

   ![](assets/federated_database_1.png)

1. Federate データベースに **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL 種類]** ドロップダウンから「Snowflake」を選択します。

   ![](assets/federated_database_2.png)

1. Snowflake認証の設定を行います。

   * **[!UICONTROL サーバー]**: サーバー名を入力します。

   * **[!UICONTROL ユーザー]**：ユーザー名を入力します。

   * **[!UICONTROL パスワード]**：アカウントのパスワードを入力します。

   * **[!UICONTROL データベース]** （オプション）:DSN で指定されていない場合は、データベースの名前を入力します。

   * **[!UICONTROL 作業スキーマ]** （オプション）：作業スキーマの名前を入力します。

   * **[!UICONTROL 秘密鍵]**:「**[!UICONTROL 秘密鍵]**」フィールドをクリックして、ロケールフォルダーから.pem ファイルを選択します。

   * **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

1. 「**[!UICONTROL 接続をテスト]**」オプションを選択して、設定を確認します。

1. 「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックして、関数を作成します。

1. 設定が完了したら、「**[!UICONTROL 追加]**」をクリックして、Federate データベースを作成します。

コネクタは、次のオプションをサポートしています。

| オプション | 説明 |
|---|---|
| workschema | ワークテーブルに使用するデータベーススキーマ  |
| warehouse | 使用するデフォルトのウェアハウスの名前。ユーザーのデフォルト値より優先されます。 |
| TimeZoneName | デフォルトでは空で、Campaign Classic アプリケーションサーバーのシステムのタイムゾーンが使用されます。このオプションは、TIMEZONE セッションパラメーターを強制的に指定するために使用できます。<br>詳しくは、[このページ](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone)を参照してください。 |
| WeekStart | WEEK_START セッションパラメーター。デフォルトでは 0 に設定されています。<br>詳しくは、[このページ](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start)を参照してください。 |
| UseCachedResult | USE_CACHED_RESULTS セッションパラメーター。デフォルトでは TRUE に設定されています。このオプションは、Snowflakeがキャッシュした結果を無効にするために使用できます。 <br>詳しくは、[このページ](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html)を参照してください。 |
| bulkThreads | Snowflakeバルクローダーに使用するスレッドの数。スレッドが多いほど、大きなバルク読み込みのパフォーマンスが向上します。 デフォルトでは 1 に設定されています。この数は、マシンスレッド数に応じて調整できます。 |
| chunkSize | バルクローダーチャンクのファイルサイズを決定します。 デフォルトでは 128MB に設定されています。 bulkThreads と共に使用する場合は、より最適なパフォーマンスが得られるように変更できます。 同時にアクティブなスレッドが多いほど、パフォーマンスが向上します。 <br> 詳しくは、[Snowflakeドキュメントを参照してください ](https://docs.snowflake.net/manuals/sql-reference/sql/put.html)。 |
| StageName | 事前プロビジョニングされた内部ステージの名前。 新しい一時ステージを作成する代わりに、一括読み込みで使用されます。 |

## Google BigQuery {#google-big-query}

連合データベースを使用して、外部データベースに保存されている情報を処理します。 Google Big Query へのアクセスを設定するには、次の手順に従います。

1. **[!UICONTROL Federated data]** メニューで、「**[!UICONTROL Federated databases]**」を選択します。

1. **[!UICONTROL 連合データベースを追加]** をクリックします。

   ![](assets/federated_database_1.png)

1. Federate データベースに **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL タイプ]** ドロップダウンから、「Google Big Query」を選択します。

   ![](assets/federated_database_3.png)

1. Google Big Query 認証を設定します。

   * **[!UICONTROL サービスアカウント]**: **[!UICONTROL サービスアカウント]** のメールアドレスを入力します。 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/iam/docs/creating-managing-service-accounts) を参照してください。

   * **[!UICONTROL プロジェクト]**: **[!UICONTROL プロジェクト]** の名前を入力します。 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/resource-manager/docs/creating-managing-projects) を参照してください。

   * **[!UICONTROL データセット]**: **[!UICONTROL データセット]** の名前を入力します。 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/bigquery/docs/datasets-intro) を参照してください。

   * **[!UICONTROL キーファイルパス]**：キーファイルをサーバーにアップロードします。 .json ファイルのみ使用できます。

   * **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

1. 「**[!UICONTROL 接続をテスト]**」オプションを選択して、設定を確認します。

1. 「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックして、関数を作成します。

1. 設定が完了したら、「**[!UICONTROL 追加]**」をクリックして、Federate データベースを作成します。

| オプション | 説明 |
|:-:|:-:|
| ProxyType | ODBC および SDK コネクタ経由で BigQuery に接続するために使用されるプロキシの種類です。 現在、</br>HTTP （デフォルト）、http_no_tunnel、socks4、socks5 がサポートされています。 |
| ProxyHost | プロキシにアクセスできるホスト名または IP アドレス。 |
| ProxyPort | プロキシが実行されているポート番号（例：8080） |
| ProxyUid | 認証済みプロキシに使用するユーザー名 |
| ProxyPwd | ProxyUid パスワード |
| bqpath | なお、これは一括読み込みツール（Cloud SDK）にのみ適用されます。 </br> PATH 変数の使用を避ける場合や、google-cloud-sdk ディレクトリを別の場所に移動する必要がある場合は、このオプションを使用して、サーバー上の cloud sdk bin ディレクトリへの正確なパスを指定できます。 |
| GCloudConfigName | これは、リリース 7.3.4 リリース以降に適用され、一括読み込みツール（Cloud SDK）にのみ適用されることに注意してください。</br> Google Cloud SDK は、設定を使用してデータを BigQuery テーブルに読み込みます。 `accfda` という名前の設定は、データを読み込むためのパラメーターを格納します。 ただし、このオプションを使用すると、ユーザーは設定に別の名前を指定できます。 |
| GCloudDefaultConfigName | これは、リリース 7.3.4 リリース以降に適用され、一括読み込みツール（Cloud SDK）にのみ適用されることに注意してください。</br> アクティブなGoogle Cloud SDK 設定は、最初にアクティブなタグを新しい設定に転送しないと、削除できません。 データを読み込むためのメイン設定を再作成するには、この一時的な設定が必要です。 一時設定のデフォルト名は `default` です。これは必要に応じて変更できます。 |
| GCloudRecreateConfig | これは、リリース 7.3.4 リリース以降に適用され、一括読み込みツール（Cloud SDK）にのみ適用されることに注意してください。</br>`false` に設定すると、一括読み込みメカニズムは、Google Cloud SDK 設定を再作成、削除、変更しようとしません。 代わりに、マシン上の既存の設定を使用してデータの読み込みを続行します。 この機能は、他の操作がGoogle Cloud SDK 設定に依存している場合に役立ちます。 </br> 適切な設定を行わないでこのエンジンオプションを有効にすると、一括読み込みメカニズムは警告メッセージを表示します：`No active configuration found. Please either create it manually or remove the GCloudRecreateConfig option`。 それ以上のエラーを防ぐために、デフォルトの ODBC 配列の挿入バルクロードメカニズムを使用して、に戻ります。 |

## Azure synapse Redshift {#azure-synapse-redshift}

連合データベースを使用して、外部データベースに保存されている情報を処理します。 azure synapseRedshift へのアクセスを設定するには、次の手順に従います。

1. **[!UICONTROL Federated data]** メニューで、「**[!UICONTROL Federated databases]**」を選択します。

1. **[!UICONTROL 連合データベースを追加]** をクリックします。

   ![](assets/federated_database_1.png)

1. Federate データベースに **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL 種類]** ドロップダウンから、「Azure synapseRedshift」を選択します。

   ![](assets/federated_database_4.png)

1. azure synapseRedshift 認証を設定します。

   * **[!UICONTROL サーバー]**:Azure synapseサーバーの URL を入力します。

   * **[!UICONTROL アカウント]**：ユーザー名を入力します。

   * **[!UICONTROL パスワード]**：アカウントのパスワードを入力します。

   * **[!UICONTROL データベース]** （オプション）:DSN で指定されていない場合は、データベースの名前を入力します。

   * **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

1. 「**[!UICONTROL 接続をテスト]**」オプションを選択して、設定を確認します。

1. 「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックして、関数を作成します。

1. 設定が完了したら、「**[!UICONTROL 追加]**」をクリックして、Federate データベースを作成します。

| オプション | 説明 |
|:-:|:-:|
| 認証 | コネクターでサポートされている認証のタイプ。 現在サポートされている値：ActiveDirectoryMSI。 詳しくは、[SQL ドキュメント ](https://learn.microsoft.com/en-us/sql/connect/odbc/using-azure-active-directory?view=sql-server-ver15#example-connection-strings) （接続文字列 n°8 の例）を参照してください |

## Vertica Analytics {#vertica-analytics}

連合データベースを使用して、外部データベースに保存されている情報を処理します。 vertica analyticsへのアクセスを設定するには、次の手順に従います。

1. **[!UICONTROL Federated data]** メニューで、「**[!UICONTROL Federated databases]**」を選択します。

1. **[!UICONTROL 連合データベースを追加]** をクリックします。

   ![](assets/federated_database_1.png)

1. Federate データベースに **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL タイプ]** ドロップダウンから「Vertica analytics」を選択します。

   ![](assets/federated_database_5.png)

1. Vertica Analytics認証を次のように設定します。

   * **[!UICONTROL サーバー]**:[!DNL Vertica Analytics] サーバーの URL を追加します。

   * **[!UICONTROL アカウント]**：ユーザー名を追加します。

   * **[!UICONTROL パスワード]**：アカウントのパスワードを追加します。

   * **[!UICONTROL データベース]** （オプション）:DSN で指定されていない場合は、データベースの名前を入力します。

   * **[!UICONTROL 作業スキーマ]** （オプション）：作業スキーマの名前を入力します。

   * **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

1. 「**[!UICONTROL 接続をテスト]**」オプションを選択して、設定を確認します。

1. 「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックして、関数を作成します。

1. 設定が完了したら、「**[!UICONTROL 追加]**」をクリックして、Federate データベースを作成します。

コネクタは、次のオプションをサポートしています。

| オプション | 説明 |
|---|---|
| TimeZoneName | デフォルトでは空で、Campaign Classic アプリケーションサーバーのシステムのタイムゾーンが使用されます。オプションを使用すると、TIMEZONE セッションパラメーターを強制できます。 |

## Amazon Redshift {#amazon-redshift}

連合データベースを使用して、外部データベースに保存されている情報を処理します。 Amazon Redshift へのアクセスを設定するには、次の手順に従います。

1. **[!UICONTROL Federated data]** メニューで、「**[!UICONTROL Federated databases]**」を選択します。

1. **[!UICONTROL 連合データベースを追加]** をクリックします。

   ![](assets/federated_database_1.png)

1. Federate データベースに **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL Type]** ドロップダウンから、「Amazon Redshift」を選択します。

   ![](assets/federated_database_6.png)

1. Amazon Redshift の認証設定を行います。

   * **[!UICONTROL サーバー]**:DNS の名前を追加します。

   * **[!UICONTROL アカウント]**：ユーザー名を追加します。

   * **[!UICONTROL パスワード]**：アカウントのパスワードを追加します。

   * **[!UICONTROL データベース]**：DSN で指定されていない場合のデータベースの名前。DSN で指定した場合は、空のままにできます

   * **[!UICONTROL 作業スキーマ]**：作業スキーマの名前。 [詳細情報](https://docs.aws.amazon.com/redshift/latest/dg/r_Schemas_and_tables.html)

1. 「**[!UICONTROL 接続をテスト]**」オプションを選択して、設定を確認します。

1. 「**[!UICONTROL 関数をデプロイ]**」ボタンをクリックして、関数を作成します。

1. 設定が完了したら、「**[!UICONTROL 追加]**」をクリックして、Federate データベースを作成します。