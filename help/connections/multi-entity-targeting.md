---
audience: end-user
title: Adobe Journey Optimizerの連合オーディエンス構成オーディエンスを使用したマルチエンティティターゲティング
description: Adobe Journey Optimizer ジャーニーでFederated Audience Composition オーディエンスからプロファイルをターゲティングする方法について説明します。
source-git-commit: 297a1d5019737c35ee07967a6d7330d3ad0bac1d
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 3%

---


# Adobe Journey OptimizerのFederated Audience Composition オーディエンスによるマルチエンティティターゲティング

複数のエンティティを使用したターゲティングでは、Adobe Journey Optimizer ジャーニーでFederated Audience Composition オーディエンス属性を補足識別子として使用できます。 これらの属性により、アカウントレベルや購読レベルなどの複数のエンティティでオーディエンスをアクティブ化できます。

## Federated Audience Compositionでのオーディエンスの作成 {#create}

マルチエンティティターゲティングを開始するには、まず連合オーディエンス構成でオーディエンスを作成して保存する必要があります。

オーディエンス構成UI内で、「**オーディエンスを作成**」アクティビティを追加して、連合コンポジションキャンバス内にオーディエンスを作成し、「**オーディエンスを保存**」アクティビティを追加して、オーディエンスのマッピング、プライマリ ID、データの有効期限を設定します。

![連合オーディエンス構成UIが表示され、オーディエンスが表示されます。](/help/connections/assets/multi-entity-targeting/build-activity.png)

オーディエンスの設定が完了したら、「**開始**」を選択して、コンポジションの実行を開始します。 このオーディエンスとそれに対応するデータセットは、Experience Platformで使用できるようになります。

連合オーディエンスコンポジションでのコンポジションの作成について詳しくは、[&#x200B; コンポジションの作成ガイド &#x200B;](/help/compositions/create-composition.md)を参照してください。

## Adobe Journey Optimizerでオーディエンスをアクティベート {#activate}

コンポジションの実行が完了したら、Journey Optimizerでオーディエンスをアクティブ化できます。 Adobe Journey Optimizerの&#x200B;**ジャーニー管理** セクション内で、「**ジャーニー**」を選択し、続いて「**ジャーニーを作成**」を選択して、ジャーニーユーザーインターフェイスを開きます。

![Adobe Journey Optimizer内の「ジャーニーを作成」ボタンがハイライト表示されます。](/help/connections/assets/multi-entity-targeting/select-create-journey.png)

ジャーニーインターフェイス内で、**オーディエンスを読み取り** ノードを追加します。 このノードを設定するには、ラベルを指定し、以前に作成したオーディエンスを選択します。

![&#x200B; オーディエンスの読み取りノードがJourney Optimizer UIに表示されます。](/help/connections/assets/multi-entity-targeting/read-journey.png)

以前に作成したオーディエンスを選択したら、**追加識別子を使用**&#x200B;を有効にします。

![補足識別子を使用チェックボックスが強調表示されます。](/help/connections/assets/multi-entity-targeting/enable-use-supplemental-identifier.png)

補足識別子を選択できるようになりました。 セレクター画面で、**詳細モード**&#x200B;を選択し、**Experience Platform**&#x200B;に移動します。 このページ内で、以前に作成したオーディエンスの名前を選択し、オーディエンスに使用する補足識別子を選択します。

![式エディターが表示されます。](/help/connections/assets/multi-entity-targeting/add-expression.png)

## ジャーニー条件の設定 {#configure-journey}

オーディエンス設定をアクティブ化して設定したら、ジャーニーの残りの条件を引き続き設定できます。 このユースケースでは、**オーディエンスの読み取り** ノードの後に&#x200B;**Optimizer** ノードを追加し、その後に&#x200B;**アクション** ノードを追加します。

残りのノードを設定したら、**公開**&#x200B;を選択してジャーニーの作成を完了します。

![公開ボタンがハイライト表示されます。](/help/connections/assets/multi-entity-targeting/select-publish.png)

これで、ジャーニーは、プライマリ識別子ではなく&#x200B;**補足識別子**&#x200B;に基づいてオーディエンスプロファイルをターゲットにします。 この機能を使用すると、サブスクリプション ID、アカウント ID、注文IDなどの複数のエンティティをターゲットにして、目的のチャネルにアクティベートできるようになりました。

## 次の手順 {#next-steps}

このガイドでは、Journey Optimizer ジャーニーでFederated Audience Composition オーディエンスから補足的なIDを使用する方法について説明します。 追加のジャーニーの使用について詳しくは、ジャーニーのガイド [&#128279;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/supplemental-identifier)で補足識別子を使用するを参照してください。
