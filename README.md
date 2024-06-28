---
source-git-commit: e1b447971ee2792cf3a1a4c759edd462e3a76967
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 37%

---
# 記事のコントリビューション

アドビのコミュニティはもとより、ドキュメントチーム外部のアドビ従業員からのコントリビューションもお待ちしています。

## アドビのオープンソースの行動規範

このプロジェクトでは、[アドビのオープンソースの行動規範](code-of-conduct.md)または [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct)（英語）を採用しています。詳しくは、[コントリビューション](contributing.md)の記事を参照してください。

## Adobeコンテンツへの投稿方法

**Adobe従業員でない場合** 外部コミュニティの投稿を送信できます。 コミュニティの投稿は社内システムにインポートされ、編集されてパブリックリポジトリにマージされます。 その後、公開リポジトリが最新の変更と同期され、非公開リポジトリに結合されます。

**Adobe社員の場合**&#x200B;の場合、プライベートに直接投稿できます [Adobe GitHub リポジトリ](https://git.corp.adobe.com/AdobeDocs/). 詳しくは、Adobeの従業員を対象としたAdobe Experience League オーサリングガイドを参照してください。

## 外部寄稿者

### 軽微な変更

マイナーアップデートに参加している場合：

1. 編集するトピックに移動します。
1. 「このコンテンツは役に立ちましたか？」 ブラウザーウィンドウの下部に表示されるバナーで、 **詳細なフィードバックオプション**.
1. クリック **編集の提案** そして、GitHub UI で変更内容を含んだプルリクエスト（PR）を送信します。

   詳しくは、全般的な事項について説明した[アドビドキュメントのコントリビューターガイド](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=ja)を参照してください。

このリポジトリー内のドキュメントやコード例に対して提案される軽微な変更や補足説明には、アドビの利用規約が適用されます。

### コミュニティからの大きな変更または新しいトピック

Adobeコミュニティのメンバーが新しいトピックを作成したり、大きな変更を送信したりする場合は、 **問題** 問題を送信してドキュメントチームとの会話を開始するには、該当する Git リポジトリーの「」タブをクリックします。 計画が合意されたら、Adobeライターと協力してリビジョンを公開します。

**注意：** ドキュメントとコード例を大幅に変更したプルリクエストを送信すると、プルリクエストにオンライン貢献使用許諾契約（CLA）を送信するように求めるメッセージが表示されます。 プルリクエストを確認する前に、オンラインフォームに記入する必要があります。

### ツール

コミュニティのコントリビューターは、基本的な編集をするときには GitHub の UI を使用し、大きな変更を加えるときにはリポジトリーをフォークします。

詳しくは、[アドビドキュメントのコントリビューターガイド](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=ja)を参照してください。

## 内部寄稿者

Adobe Experience Cloud ソリューションの製品チームのテクニカルライター、プログラムマネージャーまたはデベロッパーで、業務として技術記事の執筆やコントリビューションをする場合は、 [プライベートリポジトリ](https://git.corp.adobe.com/AdobeDocs).

## トピックの書式設定

このリポジトリ内の記事はすべて、GitHub 固有の Markdown を使用しています。 Markdown について詳しくは、以下を参照してください。

* [Markdown の基本](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/)（英語）
* [印刷可能な Markdown のクイックリファレンス](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)（英語）

## ラベル

公開リポジトリーでは、プルリクエストに以下のような自動ラベルが割り当てられ、プルリクエストワークフローの管理とプルリクエストの処理状況の把握に役立ちます。

* **Change sent to author**：保留中のプルリクエストの通知が作成者に送信されました。
* **ready- to- merge**：プルリクエストレビューチームによるレビューの準備ができました。
