---
audience: end-user
title: Adobe Journey Optimizer で連合オーディエンス構成オーディエンスを使用したマルチエンティティターゲティング
description: Adobe Journey Optimizer ジャーニーで連合オーディエンス構成オーディエンスからプロファイルをターゲットにする方法について説明します。
source-git-commit: 79f05c5a1b025b522a1b88615973d9fe383e3720
workflow-type: ht
source-wordcount: '496'
ht-degree: 100%

---


# Adobe Journey Optimizer で連合オーディエンス構成オーディエンスを使用したマルチエンティティターゲティング

マルチエンティティターゲティングを使用すると、連合オーディエンス構成オーディエンス属性を、Adobe Journey Optimizer ジャーニーの補助識別子として使用できます。これらの属性により、アカウントやサブスクリプションレベルなど、複数のエンティティでオーディエンスをアクティブ化できます。

## 連合オーディエンス構成でのオーディエンスの作成 {#create}

マルチエンティティターゲティングを開始するには、まず連合オーディエンス構成でオーディエンスを作成して保存する必要があります。

オーディエンス構成 UI 内で、**オーディエンスを作成**&#x200B;アクティビティを追加して、連合構成キャンバス内にオーディエンスを作成し、**オーディエンスを保存**&#x200B;アクティビティを追加して、オーディエンスのマッピング、プライマリ ID、データ有効期限を設定します。

![オーディエンスを示す、連合オーディエンス構成 UI が表示されています。](/help/connections/assets/multi-entity-targeting/build-activity.png)

オーディエンスの設定が完了したら、「**開始**」を選択して、構成の実行を開始します。このオーディエンスとそれに対応するデータセットは、Experience Platform で使用可能になります。

連合オーディエンス構成での構成の作成について詳しくは、[構成の作成ガイド](/help/compositions/create-composition.md)を参照してください。

## Adobe Journey Optimizer でのオーディエンスのアクティブ化 {#activate}

構成の実行が完了したら、Journey Optimizer でオーディエンスをアクティブ化できます。Adobe Journey Optimizer の「**ジャーニー管理**」セクション内で、「**ジャーニー**」、「**ジャーニーを作成**」の順に選択して、ジャーニーのユーザーインターフェイスを開きます。

![Adobe Journey Optimizer 内の「ジャーニーを作成」ボタンがハイライト表示されています。](/help/connections/assets/multi-entity-targeting/select-create-journey.png)

ジャーニーインターフェイス内で、**オーディエンスを読み取り**&#x200B;ノードを追加します。このノードは、ラベルを指定し、以前に作成したオーディエンスを選択して設定できます。

![オーディエンスを読み取りノードが Journey Optimizer UI で表示されています。](/help/connections/assets/multi-entity-targeting/read-journey.png)

以前に作成したオーディエンスを選択したら、**補助識別子を使用**&#x200B;を有効にします。

![「補助識別子を使用」チェックボックスがハイライト表示されています。](/help/connections/assets/multi-entity-targeting/enable-use-supplemental-identifier.png)

補助識別子を選択できるようになりました。セレクター画面で、「**詳細設定モード**」を選択し、**Experience Platform** に移動します。このページ内で、以前に作成したオーディエンスの名前を選択し、そのオーディエンスに使用する補助識別子を選択します。

![式エディターが表示されています。](/help/connections/assets/multi-entity-targeting/add-expression.png)

## ジャーニー条件の設定 {#configure-journey}

オーディエンス設定をアクティブ化して設定したら、ジャーニーの残りの条件を引き続き設定できます。このユースケースでは、**オーディエンスを読み取り**&#x200B;ノードの後に **Optimizer** ノード、**アクション**&#x200B;ノードの順に追加する必要があります。

残りのノードを設定したら、「**公開**」を選択し、ジャーニーの作成を完了します。

![公開ボタンがハイライト表示されています。](/help/connections/assets/multi-entity-targeting/select-publish.png)

ジャーニーは、プライマリ識別子の代わりに、**補助識別子**&#x200B;に基づいてオーディエンスプロファイルをターゲットにするようになります。この機能を使用すると、サブスクリプション ID、アカウント ID、注文 ID などの複数のエンティティをターゲットにして、目的のチャネルにアクティブ化できるようになりました。

## 次の手順 {#next-steps}

このガイドを参照すると、連合オーディエンス構成オーディエンスの補助識別子を Journey Optimizer ジャーニーで使用する方法が理解できます。補助ジャーニーの使用について詳しくは、[ジャーニーの補助識別子の使用](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/supplemental-identifier)ガイドを参照してください。

