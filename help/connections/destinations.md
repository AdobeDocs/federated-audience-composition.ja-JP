---
audience: end-user
title: Adobeへのオーディエンスの送信 Federated Audience Composition
description: Adobe Experience Platform オーディエンスを Federated Audience コンポジションに送信する方法を説明します
badge: label="限定提供" type="Informative"
source-git-commit: 1e400d98040cdbcc6f13f84faa00e8efa6cfbd4a
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 8%

---

# Adobeの Federated Audience Composition にAdobe Experience Platformを送信 {#connect-aep-fac}

>[!CONTEXTUALHELP]
>id="dc_new_destination"
>title="宛先の作成"
>abstract="新しい連合データベースに接続するための設定を入力します。 「**[!UICONTROL 宛先に接続]**」ボタンを使用して、設定を検証します。"

Adobe Experience Platformでは、オーディエンスポータルからAdobeの Federated Audience Composition にオーディエンスを送信できます。 これにより、既存のオーディエンスをコンポジションに活用し、外部データベースのデータと組み合わせて、新しいオーディエンスを作成したり、既存のオーディエンスを更新したりできます。

これを行うには、Adobe Experience Platformで、AdobeFederated Audience Composition 宛先への新しい接続を設定する必要があります。 スケジューラーを使用して、特定のオーディエンスを通常の頻度で送信し、データを紐付ける ID など、オーディエンスと共に送信するフィールドを選択できます。 ガバナンスポリシーとプライバシーポリシーをオーディエンスに適用した場合、オーディエンスが更新された後も保持され、オーディエンスポータルに送り返されます。

Adobe Experience Platform オーディエンスをAdobeの Federated Audience コンポジションに送信する主な手順は次のとおりです。

1. Adobe Experience Platformの宛先カタログにアクセスし、Federated Audience Composition の宛先を選択します。

   右側のペインで「**[!UICONTROL 新しい宛先を設定]**」を選択します。

   ![](assets/destination-new.png)

1. 新しい接続の名前を指定し、使用する **[!UICONTROL 接続タイプ]** と接続する **[!UICONTROL 連合データベース]** を選択して、「**[!UICONTROL 次へ]**」をクリックします。

   ![](assets/destination-configure.png)

   「**[!UICONTROL アラート]**」セクションを使用すると、宛先へのデータフローのステータスに関する通知をアラートが受け取れるように設定できます。 アラートについて詳しくは、[UI を使用した宛先アラートの購読](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/alerts)についてのガイドを参照してください。

1. **[!UICONTROL ガバナンスポリシーと適用アクション]** ステップでは、データガバナンスポリシーを定義し、オーディエンスが送信されてアクティブな場合に使用されるデータが準拠していることを確認できます。

   宛先に対する目的のマーケティングアクションの選択が完了したら、「**[!UICONTROL 作成]**」をクリックします。

1. 宛先への新しい接続が作成されます。 オーディエンスをアクティブ化して、宛先に送信できるようになりました。 これを行うには、リストからテンプレートを選択し、「次へ **[!UICONTROL をクリックします]**

   ![](assets/destination-activate.png)

1. 送信するオーディエンスを選択し、「**[!UICONTROL 次へ]**」をクリックします。

1. 選択したオーディエンスのファイル名と書き出しスケジュールを設定します。

   ![](assets/destination-schedule.png)

   >[!NOTE]
   >
   >スケジュールとファイル名を設定する方法について詳しくは、Adobe Experience Platform ドキュメントを参照してください。
   >* [ オーディエンスの書き出しをスケジュール ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#scheduling)
   >* [ ファイル名の設定 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#configure-file-names)

1. **[!UICONTROL マッピング]** ステップでは、オーディエンスに書き出す属性フィールドと ID フィールドを選択します。 詳しくは、Adobe Experience Platform ドキュメントの [ マッピングステップ ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#mapping) を参照してください。

   ![](assets/destination-attributes.png)

1. 宛先設定とオーディエンス設定を確認し、「**[!UICONTROL 終了]**」をクリックします。

   ![](assets/destination-review.png)

これで、選択したオーディエンスが新しい接続用にアクティベートされました。 **[!UICONTROL オーディエンスをアクティブ化]** ページに戻ると、この接続で送信するオーディエンスを追加できます。 オーディエンスは、一度アクティブ化すると削除できません。
