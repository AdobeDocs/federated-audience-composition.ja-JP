---
audience: end-user
title: オーディエンスの操作
description: オーディエンスの操作方法を学ぶ
badge: label="限定提供" type="Informative"
exl-id: c6507624-1dc9-43f9-a3ad-c3dc9689f8c7
source-git-commit: 4b7645e45b68a7316d9ddc09af1a8253b4e4dd62
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 5%

---

# オーディエンスの操作 {#gs-audiences}

Experience Platformの Federated Audience コンポジションを使用すると、様々なアクティビティをビジュアルキャンバスに活用してオーディエンスを作成し、Adobe Experience Platform Audience Portal に保存できる [ コンポジションを作成 ](../compositions/gs-compositions.md) できます。

その後、Adobe Experience Platformでサポートされている任意の宛先に対して、これらのオーディエンスをアクティブ化できます。

## コンポジションを使用したオーディエンスの作成 {#creation}

Federated Audience コンポジションを使用してオーディエンスを作成するには、**[!UICONTROL オーディエンスを保存]** アクティビティを含むコンポジションを作成する必要があります。 このアクティビティを使用すると、オーディエンスをオーディエンスポータルに保存したり、外部データベースからフィールドを選択してオーディエンスに含めたりできます。 [「オーディエンスを保存」アクティビティの設定方法の詳細情報](../compositions/activities/save-audience.md)

Adobeの Federated Data Composition を使用して作成されたオーディエンスには、**[!UICONTROL オーディエンスを保存]** アクティビティで選択されたすべてのフィールドが含まれ、すべてのAdobe Experience Platform オーディエンスと共に Audience Portal に保存されます。

コンポジションを実行すると、結果のオーディエンスが外部オーディエンスとしてAdobe Experience Platformに保存され、Adobeの Real-time Customer Data Platform やAdobe Journey Optimizerで使用できるようになります。

これらのオーディエンスは、Adobe Experience Platformでサポートされている任意の宛先に対してアクティブ化できます。 [ 宛先の操作方法については、こちらを参照してください ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home)

>[!NOTE]
>
>Adobe Federated Audience Composition を使用して作成されたオーディエンスは編集できません。 これらのオーディエンスの 1 つを変更するには、コンポジションを使用して新しいオーディエンスを作成する必要があります。

## Adobe Experience Platformでのオーディエンスへのアクセス {#access-audience}

Federated Audience コンポジションを使用して作成されたオーディエンスは、Audience Portal でアクセス可能になります。このポータルには、**オーディエンス** メニューからアクセスできます。

**[!UICONTROL 参照]** タブには、Adobe Experience Platformに保存されている既存のオーディエンスがすべて表示されます。 **[!UICONTROL 接触チャネル]** 列または左側のパネルで使用可能なフィルターを使用して、リスト内の Federated Audience Composition オーディエンスを識別できます。

![](assets/audiences-list.png)

Adobe Experience Platformでのオーディエンスの操作方法について詳しくは、[Audience Portal ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/audience-portal) を参照してください。

<!-- add link to this donc once published: https://jira.corp.adobe.com/browse/PLAT-198674-->