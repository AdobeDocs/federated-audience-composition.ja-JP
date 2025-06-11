---
title: 外部データベースへのアクセスの権限
description: 各データベースエンジンにアクセスしてタスクを実行するために必要な権限について説明します
exl-id: 287fb4a4-5767-4337-96be-dceca55f756d
source-git-commit: 530a8709a67fabec1a36e1661b922f3e9a9e6996
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 35%

---

# Federated Data Access （FDA）権限マトリックス {#fda-rights}

次の表に、各システムで必要なデータベース権限の概要を示します。これにより、Federated Data Access （FDA）を使用して外部データベースに対する操作を実行できます。

|   | Snowflake | Redshift | Google BigQuery | Databricks |
|:-:|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | `USAGE ON WAREHOUSE`、`USAGE ON DATABASE`、`USAGE ON SCHEMA` の権限 | AWS アカウントにリンクされたユーザーを作成 | サービスアカウントを作成し、プロジェクトへのプリンシパルアクセス権を付与します | カタログの `USE CATALOG` 権限と SQL Warehouse の `CAN_USE` 権限 |
| **テーブルの作成** | `CREATE TABLE ON SCHEMA` 権限 | `CREATE` 権限 | サービス アカウントに割り当てられた役割には、`bigquery.jobs.create` と `bigquery.tables.create` の権限が含まれている必要があります | `USE SCHEMA` および `CREATE TABLE` の権限 |
| **インデックスの作成** | なし | `CREATE` 権限 | BigQuery は検索インデックスのみをサポートします。 サービスアカウントに割り当てられた役割には、`bigquery.jobs.create`、`bigquery.tables.getData`、`bigquery.tables.createIndex` の権限が含まれている必要があります | なし |
| **関数の作成** | `CREATE FUNCTION ON SCHEMA` 権限 | 外部 `USAGE ON LANGUAGE plpythonu` スクリプトを呼び出せる権限がありません | サービス アカウントに割り当てられた役割には、`bigquery.jobs.create` と `bigquery.routines.create` の権限が含まれている必要があります。 | `CREATE FUNCTION` 権限 |
| **プロシージャの作成** | なし | 外部 `USAGE ON LANGUAGE plpythonu` スクリプトを呼び出せる権限がありません | サービスアカウントに割り当てられる役割には、`bigquery.jobs.create` および `bigquery.routines.create` の権限が含まれている必要があります。 | なし |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | オブジェクトの所有者 | オブジェクトの所有者またはスーパーユーザー | サービス アカウントに割り当てられた役割には、`bigquery.jobs.create`、`bigquery.routines.delete`、`bigquery.tables.delete`、`bigquery.tables.deleteIndex` のアクセス許可が含まれている必要があります | なし |
| **実行の監視** | 必要なオブジェクトに対する `MONITOR` 権限 | `EXPLAIN` コマンドを使用するために必要な権限はありません | `monitoring.viewer` 役割 | `CAN_VIEW` 権限 |
| **データの書き込み** | `INSERT` 権限または `UPDATE` 権限（書き込み操作による） | `INSERT` および `UPDATE` の権限 | サービス アカウントに割り当てられた役割には、`bigquery.jobs.create` と `bigquery.tables.updateData` が含まれている必要があります。 | `MODIFY` 権限 |
| **テーブルへのデータの読み込み** | ターゲット・テーブル権限に対する `CREATE STAGE ON SCHEMA`、`SELECT`、`INSERT` | `SELECT` および `INSERT` の権限 | サービス アカウントに割り当てられた役割には、`bigquery.jobs.create`、`bigquery.tables.getData`、および `bigquery.tables.updateData` が含まれている必要があります。 | `SELECT` および `MODIFY` の権限 |
| **クライアントデータへのアクセス** | `SELECT on (FUTURE) TABLE(S)` または `VIEW(S)` の権限 | `SELECT` 権限 | サービス アカウントに割り当てられた役割には、テーブルの `bigquery.jobs.create` と `bigquery.tables.getData`、または `bigquery.dataViewer` の役割が含まれている必要があります。 | `SELECT` 権限 |
| **メタデータへのアクセス** | `SELECT on INFORMATION_SCHEMA SCHEMA` 権限 | `SELECT` 権限 | `bigquery.metadataViewer` 役割 |  `SELECT on INFORMATION_SCHEMA SCHEMA` 権限 |


|   | Microsoft Fabric | Azure Synapse Analytics | Vertica |
|:-:|:-:|:-:|:-:|
| **リモートデータベースへの接続** | 読み取り（デフォルト）権限 | `CONNECT` 権限 | 権限は不要 |
| **テーブルの作成** | `CREATE TABLE ON DATABASE` （倉庫）および `ALTER ON SCHEMA` | `CREATE TABLE` 権限 | `CREATE ON SCHEMA` 権限 |
| **インデックスの作成** | なし | `ALTER` 権限 | なし |
| **関数の作成** | なし | `CREATE FUNCTION` 権限 | `CREATE ON SCHEMA` 権限 |
| **プロシージャの作成** | `CREATE PROCEDURE ON DATABASE` （倉庫）および `ALTER ON SCHEMA` | `CREATE PROCEDURE` 権限 | `CREATE ON SCHEMA` 権限 |
| **オブジェクト（テーブル、インデックス、関数、プロシージャ）の削除** | `ALTER ON SCHEMA` | `ALTER` 権限 | オブジェクトの所有またはオブジェクトに対する `DROP` 権限 |
| **実行の監視** | Workspace投稿者以上の権限（`queryinsights.exec_requests_history`） | `CONTROL` 権限 | `EXPLAIN` ステートメントを使用するために必要な特権はありません |
| **データの書き込み** | `INSERT` または `UPDATE ON OBJECT` | `INSERT` および `UPDATE` の権限 | `INSERT` および `UPDATE` 権限 |
| **テーブルへのデータの読み込み** | `SELECT ON OBJECT` および `INSERT ON OBJECT` | `CREATE TABLE`、`EXECUTE`、`SELECT`、`INSERT`、`UPDATE` および `ALTER` の権限 | テーブルに対する `INSERT` 権限、スキーマに対する `USAGE` 権限 |
| **クライアントデータへのアクセス** | `SELECT ON OBJECT` | `SELECT` 権限 | `SELECT` 権限 |
| **メタデータへのアクセス** | `SELECT ON INFORMATION_SCHEMA` | describe テーブルに権限は不要 | `USAGE ON SCHEMA`、`SELECT on TABLE` およびテーブル `v_catalog.columns` と `v_catalog.view_columns` に対する権限 |
