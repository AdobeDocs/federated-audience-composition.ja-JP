---
audience: end-user
title: クエリモデラーを使用した最初のクエリの作成
description: クエリモデラーで最初のクエリを作成する方法について説明します。
badge: label="限定提供" type="Informative"
exl-id: abff07ef-2bc0-4e00-8957-4d59fc3bc938
source-git-commit: 0efe4046cf30b4c447551c1cebbea0b4c2085a9f
workflow-type: tm+mt
source-wordcount: '2068'
ht-degree: 100%

---

# 式の編集 {#expression}

式を編集する場合は、条件を手動で入力してルールを作成します。このモードでは、日付、文字列、数値の各フィールドの操作や並べ替えなど、具体的なクエリの実行に使用する値を操作する高度な関数を使用できます。

## 式エディターの操作 {#edit}

式エディターは、クエリモデラーの「**[!UICONTROL 式を編集]**」ボタンから実行できます。このボタンは、カスタム条件を設定する際に「**[!UICONTROL 属性]**」フィールドと「**[!UICONTROL 値]**」フィールドで使用できます。

| 「**[!UICONTROL 属性]**」フィールドからのアクセス | 「**[!UICONTROL 値]**」フィールドからのアクセス |
|  ---  |  ---  |
| ![](assets/expression-editor-attribute.png){zoomable="yes"}{width="200" align="center" zoomable="yes"} | ![](assets/edit-expression.png){zoomable="yes"}{width="200" align="center" zoomable="yes"} |

式エディターには、次の内容があります。

* 式を定義するための&#x200B;**入力フィールド（1）**。
* 式で使用でき、クエリのスキーマ（ターゲティングディメンションとも呼ばれる）に対応する使用可能な&#x200B;**フィールド（2）**&#x200B;のリスト。
* カテゴリ別に並べ替えられる&#x200B;**ヘルパー関数（3）**。

式を編集するには、入力フィールドに式を直接入力します。フィールドまたはヘルパー関数を追加するには、式内の追加する場所にカーソルを置き、「+」ボタンをクリックします。

![](assets/expression-editor.png){zoomable="yes"}

式の準備が整ったら、「**[!UICONTROL 確認]**」ボタンをクリックします。式は、選択したフィールドに表示されます。編集するには、式エディターを開き、目的の変更を行います。

次の例は、「**[!UICONTROL 値]**」フィールドに設定された式を示しています。編集するには、「**[!UICONTROL 式を編集]**」ボタンを使用して式エディターを開く必要があります。

![](assets/edit-expression-value.png){zoomable="yes"}

## ヘルパー関数

クエリ編集ツールを使用すると、高度な関数を使用して、目的の結果や操作対象のデータのタイプに応じて複雑なフィルタリングを実行できます。次の関数を使用できます。

### 集計

集計関数は、一連の値に対して計算を実行する場合に使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong><br /> </td> 
   <td> 数値タイプの列の平均を返します<br /> </td> 
   <td> Avg(&lt;値&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong><br /> </td> 
   <td> 列の null でない値をカウントします<br /> </td> 
   <td> Count(&lt;値&gt;)<br /></td>  
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong><br /> </td> 
   <td> 返される値をカウントします（すべてのフィールド）<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong><br /> </td> 
   <td> 列の null でないユニーク値をカウントします<br /> </td> 
   <td> Countdistinct(&lt;値&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong><br /> </td> 
   <td> 数値、文字列または日付タイプの列の最大値を返します<br /> </td> 
   <td> Max(&lt;値&gt;)<br /></td>  
  </tr> 
  <tr> 
   <td> <strong>Min</strong><br /> </td> 
   <td> 数値、文字列または日付タイプの列の最小値を返します<br /> </td> 
   <td> Min(&lt;値&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>StdDev</strong><br /> </td> 
   <td> 数値、文字列または日付タイプの列の標準偏差を返します<br /> </td> 
   <td> StdDev(&lt;値&gt;)<br /></td> 
  </tr>
  <tr> 
   <td> <strong>StringAgg</strong><br /> </td> 
   <td> 文字列タイプの列の値を 2 番目の引数の文字で区切って連結したものを返します<br /> </td> 
   <td> StringAgg(&lt;値&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong><br /> </td> 
   <td> 数値、文字列または日付タイプの列の値の合計を返します<br /> </td> 
   <td> Sum(&lt;値&gt;)<br /></td> 
  </tr> 
 </tbody> 
</table>

### 日付

日付関数は、日付や時刻の値を操作する場合に使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> 日付に日数を追加します<br /> </td> 
   <td> AddDays(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> 日付に時間数を追加します<br /> </td> 
   <td> AddHours(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> 日付に分数を追加します<br /> </td> 
   <td> AddMinutes(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> 日付に月数を追加します<br /> </td> 
   <td> AddMonths(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> 日付に秒数を追加します<br /> </td> 
   <td> AddSeconds(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> 日付に年数を追加します<br /> </td> 
   <td> AddYears(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr>
  <tr> 
   <td> <strong>ConvertNTZ</strong><br /> </td> 
   <td> 定義されたセッション TZ を適用して、タイムスタンプ NTZ（タイムゾーンなしのタイムスタンプ）を TZ（タイムゾーンありのタイムスタンプ）に変換します<br/> </td> 
   <td> ConvertNTZ (&lt;date+time&gt;)<br /> </td>  
  </tr>
  <tr> 
   <!--<td> <strong>ConvertTimezone</strong><br /> </td> 
   <td> <br/> </td> 
   <td> ConvertNTZ (&lt;date+time&gt;)<br /> </td>  
  </tr>-->
  <tr> 
   <td> <strong>DateCmp</strong><br /> </td> 
   <td> 2 つの日付の比較<br/> </td> 
   <td> DateCmp(&lt;日付&gt;,&lt;日付&gt;)<br /> </td>  
  </tr>
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> 日付のみを返します（時刻は 0:00）*<br /> </td> 
   <td> DateOnly(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> 日付の日を表す数を返します<br /> </td> 
   <td> Day(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> 日付の年の日数を返します<br /> </td> 
   <td> DayOfYear(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> 現在の日付 - n 日に対応する日付を返します<br /> </td> 
   <td> DaysAgo(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> 現在の日付 - n 日に対応する日付（整数 yyyymmdd）を返します<br /> </td> 
   <td> DaysAgoInt(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> 2 つの日付の間の日数を返します<br /> </td> 
   <td> DaysDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> 年齢（日数）を返します<br /> </td> 
   <td> DaysOld(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> サーバーの現在のシステム日付を返します<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> 日付の時間を返します<br /> </td> 
   <td> Hour(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> 2 つの日付の間の時間数を返します<br /> </td> 
   <td> HoursDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> 日付の分を返します<br /> </td> 
   <td> Minute(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> 2 つの日付の間の分数を返します<br /> </td> 
   <td> MinutesDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> 日付の月を表す数を返します<br /> </td> 
   <td> Month(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> 現在の日付 - n ヶ月に対応する日付を返します<br /> </td> 
   <td> MonthsAgo(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の月数を返します<br /> </td> 
   <td> MonthsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> 年齢（月数）を返します<br /> </td> 
   <td> MonthsOld(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> 範囲内の最も古い日付を返します<br /> </td> 
   <td> Oldest (&lt;日付, 日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> 日付の秒を返します<br /> </td> 
   <td> Second(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の秒数を返します<br /> </td> 
   <td> SecondsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> 日付から日数を引きます<br /> </td> 
   <td> SubDays(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> 日付から時間数を引きます<br /> </td> 
   <td> SubHours(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> 日付から分数を引きます<br /> </td> 
   <td> SubMinutes(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> 日付から月数を引きます<br /> </td> 
   <td> SubMonths(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> 日付から秒数を引きます<br /> </td> 
   <td> SubSeconds(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> 日付から年数を引きます<br /> </td> 
   <td> SubYears(&lt;日付&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> 日付 + 時間を日付に変換します<br /> </td> 
   <td> ToDate(&lt;日付 + 時刻&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> 文字列を日付 + 時刻に変換します<br /> </td> 
   <td> ToDateTime(&lt;文字列&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToTimestamp</strong><br /> </td> 
   <td> 文字列をタイムスタンプに変換<br /> </td> 
   <td> ToTimestamp(&lt;文字列&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToTimeZone</strong><br /> </td> 
   <td> 日付と時刻をタイムゾーンに変換<br /> </td> 
   <td> ToTimeZone(&lt;日付&gt;,&lt;タイムゾーン&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> 日付 + 時刻を最も近い秒に丸めます<br /> </td> 
   <td> TruncDate(@lastModified, &lt;秒数&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> 日付と時刻を指定された精度（秒）に丸めます<br /> </td> 
   <td> TruncDateTZ(&lt;日付&gt;, &lt;秒数&gt;, &lt;タイムゾーン&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> 日付を四半期に丸めます<br /> </td> 
   <td> TruncQuarter(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> 時刻部分を最も近い秒に丸めます<br /> </td> 
   <td> TruncTime(&lt;日付&gt;, &lt;秒数&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> 日付を週に丸めます<br /> </td> 
   <td> TruncWeek(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> 日付 + 時刻をその年の 1 月 1 日に丸めます<br /> </td> 
   <td> TruncYear(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> 日付の曜日を表す数値を返します（0=月曜日、6=日曜日）<br /> </td> 
   <td> WeekDay(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> 日付の年を表す数を返します<br /> </td> 
   <td> Year(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> 日付の年と月を表す数を返します<br /> </td> 
   <td> YearAndMonth(&lt;日付&gt;)<br /> </td>  
  </tr>
  <tr> 
   <td> <strong>YearsAgo</strong><br /> </td> 
   <td> 指定された日付と現在の日付の間の年数を返します<br /> </td> 
   <td> YearsAgo(&lt;日付&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> 2 つの日付の間の年数を返します<br /> </td> 
   <td> YearsDiff(&lt;終了日&gt;, &lt;開始日&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> 満年齢を返します<br /> </td> 
   <td> YearsOld(&lt;日付&gt;)<br /> </td>  
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>**Dateonly** 関数はオペレーターのタイムゾーンではなく、サーバーのタイムゾーンを考慮することに注意してください。

### ジオマーケティング

ジオマーケティング関数は、地理に関する値を操作する場合に使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distance</strong><br /> </td> 
   <td> 経度と緯度で定義された 2 つのポイントの距離を返します。<br /> </td> 
   <td> Distance(&lt;経度 A&gt;, &lt;緯度 A&gt;, &lt;経度 B&gt;, &lt;緯度 B&gt;)<br /> </td>  
  </tr> 
 </tbody> 
</table>

### 数値

数値関数は、テキストを数値に変換する場合に使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> 数値の絶対値を返します<br /> </td> 
   <td> Abs(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> ある特定の数値以上の最小の整数を返します<br /> </td> 
   <td> Ceil(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> ある特定の数値以上の最大の整数を返します<br /> </td> 
   <td> Floor(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> 2 つの数のうち大きい方を返します<br /> </td> 
   <td> Greatest(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> 2 つの数のうち小さい方を返します<br /> </td> 
   <td> Least(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> 整数の割り算 n1 ÷ n2 の余りを返します<br /> </td> 
   <td> Mod(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Percent</strong><br /> </td> 
   <td> 割合で表される 2 つの数の比率を返します<br /> </td> 
   <td> Percent(&lt;数値 1&gt;, &lt;数値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Random</strong><br /> </td> 
   <td> ランダムな値を返します<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> 数値を n 桁に丸めます<br /> </td> 
   <td> Round(&lt;数値&gt;, &lt;小数点以下の桁数&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> 数値の符号を返します<br /> </td> 
   <td> Sign(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> 整数を浮動小数に変換します<br /> </td> 
   <td> ToDouble(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> 浮動小数を 64 ビットの整数に変換します<br /> </td> 
   <td> ToInt64(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 浮動小数を整数に変換します<br /> </td> 
   <td> ToInteger(&lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> n1 を n2 の桁数に切り捨てます<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td>  
  </tr> 
 </tbody> 
</table>

### その他

以下の表には、上記以外の使用可能な関数が記載されています。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AESEncrypt</strong><br /> </td> 
   <td> 引数で指定された文字列を暗号化<br /> </td> 
   <td> AESEncrypt(&lt;値&gt;)<br /> </td> 
  </tr>
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> 条件が true の場合は値 1 を返します。そうでない場合は値 2 を返します<br /> </td> 
   <td> (When(&lt;条件&gt;, &lt;値 1&gt;), Else(&lt;値 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> 値のフラグを削除します<br /> </td> 
   <td> ClearBit(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> 値 1 がゼロまたは null の場合は値 2 を返し、それ以外の場合は値 1 を返します<br /> </td> 
   <td> Coalesce(&lt;値 1&gt;, &lt;値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> 値 1 = 値 2 の場合は値 3 を返します。そうでない場合は値 4 を返します<br /> </td> 
   <td> Decode(&lt;値 1&gt;, &lt;値 2&gt;, &lt;値 3&gt;, &lt;値 4&gt;)<br /> </td>  
  </tr> 
  <!--<tr> 
   <td> <strong>DefaultFolder</strong><br /> </td> 
   <td> Returns value 3 if value 1 = value 2. If not returns value 4.<br /> </td> 
   <td> Decode(&lt;value 1&gt;, &lt;value 2&gt;, &lt;value 3&gt;, &lt;value 4&gt;)<br /> </td>  
  </tr> -->
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> 値 1 を返します（case 関数のパラメーターとしてのみ使用できます）<br /> </td> 
   <td> Else(&lt;値 1&gt;, &lt;値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> メールアドレスからドメインを抽出します<br /> </td> 
   <td> GetEmailDomain(&lt;値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> ミラーページサーバーの URL を取得します<br /> </td> 
   <td> GetMirrorURL(&lt;値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> 式が true の場合は値 1 を返します。そうでない場合は値 2 を返します<br /> </td> 
   <td> Iif(&lt;条件&gt;, &lt;値 1&gt;, &lt;値 2&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> 値にフラグが含まれているかどうかを示します<br /> </td> 
   <td> IsBitSet(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> 文字列 1 が空の場合は値 2 を返し、それ以外の場合は値 3 を返します<br /> </td> 
   <td> IsEmptyString(&lt;値 1&gt;, &lt;値 2&gt;, &lt;値 3&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>NewUUID</strong><br /> </td> 
   <td> 一意の ID を返します<br /> </td> 
   <td> NewUUID()<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> 引数が NULL の場合は、空の文字列を返します<br /> </td> 
   <td> NoNull(&lt;値&gt;)<br /> </td>   
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> ライン番号を返します<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> 値に強制的にフラグを指定します<br /> </td> 
   <td> SetBit(&lt;識別子&gt;, &lt;フラグ&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> 数値をブール値に変換します<br /> </td> 
   <td> ToBoolean(&lt;数値&gt;)<br /> </td>   
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> 式が true の場合は値 1 を返します。そうでない場合は値 2 を返します（case 関数のパラメーターとしてのみ使用できます）<br /> </td> 
   <td> When(&lt;条件&gt;, &lt;値 1&gt;)<br /> </td>  
  </tr> 
 </tbody> 
</table>

### 文字列

文字列関数は、一連の文字列を操作する場合に使用します。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> すべてのパラメーターが null でなく空でもないかどうかを示します<br /> </td> 
   <td> AllNonNull2(&lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> すべてのパラメーターが null でなく空でもないかどうかを示します<br /> </td> 
   <td> AllNonNull3(&lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Ascii</strong><br /> </td> 
   <td> 文字列の最初の文字の ASCII 値を返します<br /> </td> 
   <td> Ascii(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> ASCII コード「n」に対応する文字を返します<br /> </td> 
   <td> Char(&lt;数値&gt;)<br /></td>  
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> 文字列 1 における文字列 2 の位置を返します<br /> </td> 
   <td> Charindex(&lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>dataLength</strong><br /> </td> 
   <td> 文字列のサイズをバイト単位で返します<br /> </td> 
   <td> dataLength(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> 文字列の n 番目（1 から n）のラインを返します<br /> </td> 
   <td> GetLine(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> 最初の 2 つのパラメーターが等しい場合に、3 番目のパラメーターを返します。等しくない場合は、最後のパラメーターを返します<br /> </td> 
   <td> IfEquals(&lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> パラメーターとして渡されたメモが null かどうかを示します<br /> </td> 
   <td> IsMemoNull(&lt;メモ&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> パラメーターとして渡された文字列を連結します。必要に応じて、文字列間にスペースを追加します.<br /> </td> 
   <td> JuxtWords(&lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> パラメーターとして渡された文字列を連結します。必要に応じて、文字列間にスペースを追加します<br /> </td> 
   <td> JuxtWords3(&lt;文字列&gt;, &lt;文字列&gt;, &lt;文字列&gt;)<br /></td>  
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> 文字列の最初の n 文字を返します<br /> </td> 
   <td> Left(&lt;文字列&gt;, &lt;数値&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> 文字列の長さを返します<br /> </td> 
   <td> Length(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>行</strong><br /> </td> 
   <td> 文字列から n 行目を抽出<br /> </td> 
   <td> Line(&lt;文字列&gt;,&lt;数値&gt;)<br /></td> 
  </tr>
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> 文字列を小文字で返します<br /> </td> 
   <td> Lower(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> 左側の完成した文字列を返します<br /> </td> 
   <td> LPad (&lt;文字列&gt;, &lt;数値&gt;, &lt;文字数&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> 文字列の左側の空白を削除します<br /> </td> 
   <td> Ltrim(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 文字列の MD5 キーの 16 進数表現を返します<br /> </td> 
   <td> Md5Digest(&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> パラメーターとして渡す文字列をメモに含めるかどうかを指定します<br /> </td> 
   <td> MemoContains(&lt;メモ&gt;、&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>NodeValue</strong><br /> </td> 
   <td> XPath とフィールドデータから XML フィールドの値を抽出します<br /> </td> 
   <td> NodeValue (&lt;文字列&gt;, &lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>置換</strong><br /> </td> 
   <td> 指定された文字列値のすべての発生を別の文字列値に置き換えます。<br /> </td> 
   <td> Replace(&lt;文字列&gt;,&lt;文字列&gt;,&lt;文字列&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> 文字列の最後の n 文字を返します<br /> </td> 
   <td> Right(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> 右側の完成した文字列を返します<br /> </td> 
   <td> RPad(&lt;文字列&gt;, &lt;数値&gt;, &lt;文字&gt;)<br /></td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> 文字列の右側の空白を削除します<br /> </td> 
   <td> Rtrim(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 文字列の SHA256 キーの 16 進数表現。<br /> </td> 
   <td> Sha256Digest (&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 文字列の SHA512 キーの 16 進数表現。<br /> </td> 
   <td> Sha512Digest (&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> 各単語の最初の文字を大文字にして文字列を返します<br /> </td> 
   <td> Smart(&lt;文字列&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> 文字列の n1 文字目から始まる長さ n2 文字の部分文字列を抽出します<br /> </td> 
   <td> Substring(&lt;文字列&gt;, &lt;オフセット&gt;, &lt;長さ&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> 数値を文字列に変換します<br /> </td> 
   <td> ToString(&lt;数値&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> 文字列を大文字で返します<br /> </td> 
   <td> Upper(&lt;文字列&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 他の 2 つのパラメーターが等しい場合に、パラメーターとして渡されたリンクの外部キーを返します<br /> </td> 
   <td> VirtualLink(&lt;数値&gt;, &lt;数値&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> 他の 2 つのパラメーターが等しい場合に、パラメーターとして渡されたリンクの外部（テキスト）キーを返します<br /> </td> 
   <td> VirtualLinkStr(&lt;文字列&gt;, &lt;数値&gt;, &lt;数値&gt;)<br /> </td>  
  </tr> 
 </tbody> 
</table>

### ウィンドウ

<table> 
 <tbody> 
  <tr> 
   <td> <strong>名前</strong><br /> </td> 
   <td> <strong>説明</strong><br /> </td> 
   <td> <strong>構文</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>_Over__</strong><br /> </td> 
   <td> 第 1 パラメーターとして入力された SQL 関数呼び出しを、第 2 パラメーターとして入力された「パーティション」または「並べ替え順」フィールドより優先して実行します<br /> </td> 
   <td> _Over_(&lt;値&gt;, &lt;値&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 降順ソートを適用します<br /> </td> 
   <td> Desc(&lt;値 1&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> パーティション内の結果を並べ替えます<br /> </td> 
   <td> OrderBy(&lt;値 1&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> テーブルのクエリの結果を区分します<br /> </td> 
   <td> PartitionBy(&lt;値 1&gt;)<br /> </td>  
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> テーブルのパーティションと並べ替えシーケンスに基づいてライン番号を生成します<br /> </td> 
   <td> RowNum(PartitionBy(&lt;値 1&gt;), OrderBy(&lt;値 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>
