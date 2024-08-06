---
audience: end-user
title: オーディエンスの操作
description: オーディエンスの操作方法について説明します
badge: label="限定提供" type="Informative"
exl-id: c6507624-1dc9-43f9-a3ad-c3dc9689f8c7
source-git-commit: f549f1611bfe6deb6dc684e3a0d9c968ba7c184a
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# オーディエンスの操作 {#gs-audiences}

Experience Platform 連合オーディエンス構成を使用すると、[構成を作成](../compositions/gs-compositions.md)し、様々なアクティビティを視覚的なキャンバスに活用してオーディエンスを作成し、Adobe Experience Platform オーディエンスポータルに保存できます。

その後、Journey Optimizer でこれらのオーディエンスをターゲットにするか、Adobe Experience Platform でサポートされる任意の宛先に対してアクティブ化できます。

## 構成を使用したオーディエンスの作成{#creation}

連合オーディエンス構成を使用してオーディエンスを作成するには、**[!UICONTROL オーディエンスを保存]**&#x200B;アクティビティを含む構成を作成する必要があります。このアクティビティを使用すると、オーディエンスをオーディエンスポータルに保存し、オーディエンスに含める外部データベースからフィールドを選択できます。[オーディエンスの保存アクティビティの設定方法を学ぶ](../compositions/activities/save-audience.md)

アドビの連合オーディエンス構成を使用して作成されたオーディエンスには、**[!UICONTROL オーディエンスを保存]**&#x200B;アクティビティで選択したすべてのフィールドが含まれ、すべての Adobe Experience Platform オーディエンスと共にオーディエンスポータルに保存されます。

構成を実行すると、結果のオーディエンスが外部オーディエンスとして Adobe Experience Platform に保存され、Adobe Real-time Customer Data Platform や Adobe Journey Optimizer で使用できるようになります。

これらのオーディエンスは、Adobe Experience Platform でサポートされている任意の宛先に対してアクティブ化できます。宛先の操作について詳しくは、[Adobe Experience Platform](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/home){target="_blank"} を参照してください。

>[!NOTE]
>
>アドビの連合オーディエンス構成を使用して作成されたオーディエンスは編集できません。これらのオーディエンスのいずれかを変更するには、構成を使用して新しいオーディエンスを作成する必要があります。

## Adobe Experience Platform でのオーディエンスへのアクセス {#access-audience}

連合オーディエンス構成を使用して作成されたオーディエンスへは、**オーディエンス**&#x200B;メニューのオーディエンスポータルからアクセスできます。

「**[!UICONTROL 参照]**」タブには、Adobe Experience Platform に保存されている既存のオーディエンスがすべて表示されます。**[!UICONTROL 接触チャネル]**&#x200B;列または左パネルで使用可能なフィルターを使用して、リスト内の連合オーディエンス構成オーディエンスを特定できます。

![](assets/audiences-list.png)

Adobe Experience Platform でのオーディエンスの操作方法について詳しくは、[オーディエンスポータルのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/audience-portal){target="_blank"}を参照してください

<!-- add link to this donc once published: https://jira.corp.adobe.com/browse/PLAT-198674-->