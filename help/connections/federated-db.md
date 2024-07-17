---
audience: end-user
title: 連合データベースの基本を学ぶ
description: 連合データベースを作成および管理する方法を学ぶ
source-git-commit: 847da9a5eeb28199010f8491f7eebba4a60a83f1
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 33%

---

# 連合データベースの基本を学ぶ {#federated-db}


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_menu"
>title="連合データベース"
>abstract="この画面には、連合データベースへの既存の接続がリストされます。 新しい接続を作成するには、「**連合データベースを追加**」ボタンをクリックします。"


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_properties"
>title="連合データベースのプロパティ"
>abstract="新しい連合データベースの名前を入力し、このタイプを選択します。"


>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_details"
>title="連合データベースの詳細"
>abstract="新しい連合データベースに接続するための設定を入力します。 「**接続をテスト**」ボタンを使用して、設定を検証します。"

外部データベースへの接続を作成、設定、テスト、保存します。

サポートされる外部データベース：

* Snowflake
* Google BigQuery
* Azure synapse
* Vertica Analytics
* Amazon Redshift

## Snowflake {#snowflake}

* **[!UICONTROL サーバー]**:

* **[!UICONTROL ユーザー]**：ユーザーの名前です。

* **[!UICONTROL パスワード]**：ユーザーアカウントのパスワード。

* **[!UICONTROL データベース]**:

* **[!UICONTROL 作業用スキーマ]**:

* **[!UICONTROL 秘密鍵]**:
.pem ファイルのみ使用できます

* **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

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

* **[!UICONTROL サービスアカウント]**：お使いの **[!UICONTROL サービスアカウント]** のメール。 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/iam/docs/creating-managing-service-accounts) を参照してください。

* **[!UICONTROL プロジェクト]**: **[!UICONTROL プロジェクト]** の名前 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/resource-manager/docs/creating-managing-projects) を参照してください。

* **[!UICONTROL データセット]**: **[!UICONTROL データセット]** の名前 詳しくは、[Google Cloud ドキュメント ](https://cloud.google.com/bigquery/docs/datasets-intro) を参照してください。

* **[!UICONTROL キーファイルパス]**：キーファイルをサーバーにアップロードします。 .json ファイルのみ使用できます。

* **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

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

* **[!UICONTROL サーバー]**：Azure Synapse サーバーの URL

* **[!UICONTROL アカウント]**：ユーザーの名前

* **[!UICONTROL パスワード]**：ユーザーアカウントのパスワード

* **[!UICONTROL データベース]**：データベースの名前

* **[!UICONTROL オプション]**

## Vertica Analytics {#vertica-analytics}

* **[!UICONTROL サーバー]**：[!DNL Vertica Analytics] サーバーの URL

* **[!UICONTROL アカウント]**：ユーザーの名前

* **[!UICONTROL パスワード]**：ユーザーアカウントのパスワード

* **[!UICONTROL データベース]**：データベースの名前

* **[!UICONTROL 作業スキーマ]**：作業スキーマの名前。

* **[!UICONTROL オプション]**：コネクタは、以下の表で説明するオプションをサポートします。

コネクタは、次のオプションをサポートしています。

| オプション | 説明 |
|---|---|
| TimeZoneName | デフォルトでは空で、Campaign Classic アプリケーションサーバーのシステムのタイムゾーンが使用されます。オプションを使用すると、TIMEZONE セッションパラメーターを強制できます。 |


## Amazon Redshift {#amazon-redshift}

* **[!UICONTROL サーバー]**：DNS の名前

* **[!UICONTROL アカウント]**：ユーザーの名前

* **[!UICONTROL パスワード]**：ユーザーアカウントのパスワード

* **[!UICONTROL データベース]**：DSN で指定されていない場合のデータベースの名前。DSN で指定した場合は、空のままにできます

* **[!UICONTROL 作業スキーマ]**：作業スキーマの名前。 [詳細情報](https://docs.aws.amazon.com/redshift/latest/dg/r_Schemas_and_tables.html)

