---
title: 外部データベースにアクセスするための権限
description: 各データベースエンジンに固有の権限について説明します
source-git-commit: 8cd1b967e004d84fda3788e442e41d2010f5ec24
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 46%

---

# FDA 権限マトリックス {#fda-rights}

次の表に、各システムで必要なデータベース権限の概要を示します。これにより、ユーザーは FDA を使用して外部データベースに対する操作を実行できます。

|   | Snowflake | Redshift | Google BigQuery | Databricks |
|:-:|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | ウェアハウスでの使用、データベースでの使用、スキーマ特権での使用 | AWS アカウントにリンクされたユーザーの作成 | サービスアカウントを作成し、プロジェクトへのプリンシパルアクセス権を付与します | カタログの USE 権限および SQL Warehouse の CAN_USE 権限 |
| **テーブルの作成** | CREATE TABLE ON SCHEMA 権限 | CREATE 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create および bigquery.tables.create 権限が含まれている必要があります。 | USE SCHEMA 権限および CREATE TABLE 権限 |
| **インデックスの作成** | なし | CREATE 権限 | BigQuery は検索インデックスのみをサポートします。 サービスアカウントに割り当てられる役割には、bigquery.jobs.create、bigquery.tables.getData および bigquery.tables.createIndex 権限が含まれている必要があります。 | なし |
| **関数の作成** | CREATE FUNCTION ON SCHEMA 権限 | 外部の Python スクリプトを呼び出せる USAGE ON LANGUAGE plpythonu 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create および bigquery.routines.create 権限が含まれている必要があります。 | CREATE FUNCTION 権限 |
| **プロシージャの作成** | なし | 外部の Python スクリプトを呼び出せる USAGE ON LANGUAGE plpythonu 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create および bigquery.routines.create 権限が含まれている必要があります。 |  該当なし |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | オブジェクトの所有者 | オブジェクトの所有者またはスーパーユーザー | サービスアカウントに割り当てられる役割には、bigquery.jobs.create、bigquery.routines.delete、bigquery.tables.delete および bigquery.tables.deleteIndex 権限が含まれている必要があります。 |
| **実行の監視** | 必要なオブジェクトに対する MONITOR 権限 | EXPLAIN コマンドの使用に権限は不要 | monitoring.viewer ロール | CAN_VIEW 権限 |
| **データの書き込み** | INSERT / UPDATE 権限（書き込み操作に応じて異なる） | INSERT および UPDATE 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create と bigquery.tables.updateData が含まれている必要があります。 |  MODIFY 権限 |
| **テーブルへのデータの読み込み** | CREATE STAGE ON SCHEMA およびターゲットテーブルでの SELECT および INSERT 権限 | SELECT および INSERT 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create、bigquery.tables.getData および bigquery.tables.updateData が含まれている必要があります。 | 権限の選択と変更 |
| **クライアントデータへのアクセス** | SELECT on (FUTURE) TABLE または VIEW 権限 | SELECT 権限 | サービスアカウントに割り当てられる役割には、bigquery.jobs.create と bigquery.tables.getData （テーブル用）または bigquery.dataViewer ロールが含まれている必要があります。 |  SELECT 権限 |
| **メタデータへのアクセス** | SELECT on INFORMATION_SCHEMA SCHEMA 権限 | SELECT 権限 | bigquery.metadataViewer ロール |  INFORMATION_SCHEMA SCHEMA 権限の選択 |


|   | Microsoft Fabric | Azure Synapse Analytics | Vertica |
|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | 読み取り（デフォルト）権限 | CONNECT 権限 | 権限は不要 |
| **テーブルの作成** | データベース （ウェアハウス）上にテーブルを作成し、スキーマに変更 | CREATE TABLE 権限 | スキーマで作成権限 |
| **インデックスの作成** | なし | ALTER 権限 | なし |
| **関数の作成** | なし | CREATE FUNCTION 権限 | スキーマで作成権限 |
| **プロシージャの作成** | データベース（ウェアハウス）上のプロシージャの作成とスキーマ上の変更 | CREATE PROCEDURE 権限 | スキーマで作成権限 |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | ALTER ON スキーマ | ALTER 権限 | オブジェクトの所有またはオブジェクトの DROP 権限 |
| **実行の監視** | Workspace投稿者または上記の権限（queryinsights.exec_requests_history）  | 制御権限 | EXPLAIN 文の使用に権限は不要 |
| **データの書き込み** | オブジェクトに対して挿入または更新 | INSERT および UPDATE パーミッション | INSERT および UPDATE 権限 |
| **テーブルへのデータの読み込み** | オブジェクト上を選択してオブジェクト上に挿入 | テーブルの作成、実行、選択、挿入、更新、権限の変更 | テーブルの INSERT 権限、スキーマの USAGE 権限 |
| **クライアントデータへのアクセス** | オブジェクトを選択 | SELECT パーミッション | SELECT 権限 |
| **メタデータへのアクセス** | INFORMATION_SCHEMA のを選択 | テーブルの説明に必要な権限がありません | USAGE ON SCHEMA、SELECT on TABLE および table v_catalog.columns と v_catalog.view_columns に対する権限 |
