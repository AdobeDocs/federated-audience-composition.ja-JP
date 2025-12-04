---
title: 外部データベースへのアクセスの権限
description: 各データベースエンジンにアクセスしてタスクを実行するために必要な権限について説明します
exl-id: 287fb4a4-5767-4337-96be-dceca55f756d
source-git-commit: e0bf1f76f7f781fb6fcc3b44898ba805d87a25c9
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# Federated Data Access（FDA）権限マトリックス {#fda-rights}

次の表に、Federated Data Access（FDA）を通じて外部データベースで操作を実行できるようにする、各システムに必要なデータベース権限の概要を示します。

|   | Snowflake | Redshift | Google BigQuery | Databricks |
|:-:|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | `USAGE ON WAREHOUSE`、`USAGE ON DATABASE`、`USAGE ON SCHEMA` 権限 | AWS アカウントにリンクされたユーザーの作成 | サービスアカウントを作成し、プロジェクトへのプリンシパルアクセス権を付与します | カタログでの `USE CATALOG` 権限と SQL ウェアハウスでの `CAN_USE` 権限 |
| **テーブルの作成** | `CREATE TABLE ON SCHEMA` 権限 | `CREATE` 権限 | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create` および `bigquery.tables.create` 権限が含まれている必要があります | `USE SCHEMA` および `CREATE TABLE` 権限 |
| **インデックスの作成** | なし | `CREATE` 権限 | BigQuery は、検索インデックスのみをサポートします。サービスアカウントに割り当てられる役割には、`bigquery.jobs.create`、`bigquery.tables.getData`、`bigquery.tables.createIndex` 権限が含まれている必要があります | なし |
| **関数の作成** | `CREATE FUNCTION ON SCHEMA` 権限 | 外部の Python スクリプトを呼び出せる `USAGE ON LANGUAGE plpythonu` 権限 | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create` および `bigquery.routines.create` 権限が含まれている必要があります | `CREATE FUNCTION` 権限 |
| **プロシージャの作成** | なし | 外部の Python スクリプトを呼び出せる `USAGE ON LANGUAGE plpythonu` 権限 | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create` および `bigquery.routines.create` 権限が含まれている必要があります | なし |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | オブジェクトの所有者 | オブジェクトの所有者またはスーパーユーザー | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create`、`bigquery.routines.delete`、`bigquery.tables.delete`、`bigquery.tables.deleteIndex` 権限が含まれている必要があります | なし |
| **実行の監視** | 必要なオブジェクトに対する `MONITOR` 権限 | `EXPLAIN` コマンドの使用に権限は不要 | `monitoring.viewer` 役割 | `CAN_VIEW` 権限 |
| **データの書き込み** | `INSERT` または `UPDATE` 権限（書き込み操作による） | `INSERT` および `UPDATE` 権限 | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create` および `bigquery.tables.updateData` が含まれている必要があります | `MODIFY` 権限 |
| **テーブルへのデータの読み込み** | ターゲットテーブル権限での `CREATE STAGE ON SCHEMA`、`SELECT`、`INSERT` | `SELECT` および `INSERT` 権限 | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create`、`bigquery.tables.getData`、`bigquery.tables.updateData` が含まれている必要があります | `SELECT` および `MODIFY` 権限 |
| **クライアントデータへのアクセス** | `SELECT on (FUTURE) TABLE(S)` または `VIEW(S)` 権限 | `SELECT` 権限 | サービスアカウントに割り当てられる役割には、テーブル用の `bigquery.jobs.create` および `bigquery.tables.getData` や、`bigquery.dataViewer` 役割が含まれている必要があります | `SELECT` 権限 |
| **メタデータへのアクセス** | `SELECT on INFORMATION_SCHEMA SCHEMA` 権限 | `SELECT` 権限 | `bigquery.metadataViewer` 役割 | `SELECT on INFORMATION_SCHEMA SCHEMA` 権限 |


|   | Microsoft Fabric | Azure Synapse Analytics | Vertica |
|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | 読み取り（デフォルト）権限 | `CONNECT` 権限 | 権限は不要 |
| **テーブルの作成** | `CREATE TABLE ON DATABASE`（ウェアハウス）および `ALTER ON SCHEMA` | `CREATE TABLE` 権限 | `CREATE ON SCHEMA` 権限 |
| **インデックスの作成** | なし | `ALTER` 権限 | なし |
| **関数の作成** | なし | `CREATE FUNCTION` 権限 | `CREATE ON SCHEMA` 権限 |
| **プロシージャの作成** | `CREATE PROCEDURE ON DATABASE`（ウェアハウス）および `ALTER ON SCHEMA` | `CREATE PROCEDURE` 権限 | `CREATE ON SCHEMA` 権限 |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | `ALTER ON SCHEMA` | `ALTER` 権限 | オブジェクトの所有者またはオブジェクトの `DROP` 権限 |
| **実行の監視** | ワークスペースコントリビューターまたは上記の権限（`queryinsights.exec_requests_history`） | `CONTROL` 権限 | `EXPLAIN` 文の使用に権限は不要 |
| **データの書き込み** | `INSERT` または `UPDATE ON OBJECT` | `INSERT` および `UPDATE` 権限 | `INSERT` および `UPDATE` 権限 |
| **テーブルへのデータの読み込み** | `SELECT ON OBJECT` および `INSERT ON OBJECT` | `CREATE TABLE`、`EXECUTE`、`SELECT`、`INSERT`、`UPDATE`、`ALTER` 権限 | テーブルでの `INSERT` 権限、スキーマでの `USAGE` 権限 |
| **クライアントデータへのアクセス** | `SELECT ON OBJECT` | `SELECT` 権限 | `SELECT` 権限 |
| **メタデータへのアクセス** | `SELECT ON INFORMATION_SCHEMA` | describe テーブルに権限は不要 | `USAGE ON SCHEMA`、`SELECT on TABLE` およびテーブル `v_catalog.columns` と `v_catalog.view_columns` での権限 |
