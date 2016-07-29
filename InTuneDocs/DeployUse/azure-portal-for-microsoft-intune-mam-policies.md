---
title: "Azure ポータルの MAM ポリシー対応 | Microsoft Intune"
description: "Azure ポータルを使用してモバイル アプリ管理ポリシーを作成します。 ここで作成したポリシーは、Intune に登録されているデバイスにも未登録のデバイスにも適用できます。"
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 359f76daa35a14e4107a9e03c6a1b1f4d1215777
ms.openlocfilehash: c466a854474c1c5ba3270f848caa51edcd5b6856


---

# Azure ポータルの Microsoft Intune MAM ポリシー対応
## Azure ポータルへのアクセス
**Azure ポータル**では、モバイル アプリ管理ポリシーを作成して管理できます。

Azure ポータルでは、次の MAM ポリシーの作成をサポートしています。
- **Intune で登録および管理されている**デバイスで実行中のアプリ
- どの MDM ソリューションにも**登録していない**デバイスで実行中のアプリ
- **サード パーティの MDM ソリューションに登録済み**のデバイスで実行中のアプリ

>[!IMPORTANT]

> 現在 Intune 管理コンソールを使用してデバイスを管理している場合は、Intune に登録済みのデバイスのアプリをサポートする MAM ポリシーを [Intune 管理コンソール](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)を使用して作成できます。

> Intune 管理コンソールでは、MAM ポリシー設定の一部が表示されない可能性があります。 Azure ポータルは MAM ポリシーを作成するための新しい管理コンソールです。Intune 管理コンソールと Azure ポータルの両方で MAM ポリシーを作成した場合、Azure ポータルのポリシーがアプリに適用され、ユーザーに展開されます。

## Azure ポータルにログインし、スタート ページをカスタマイズする

1.  [Azure ポータル](https://portal.azure.com)に移動し、[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] 資格情報でサインインします。

    ![Azure ポータルのログイン ページのスクリーンショット](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  正常にサインインすると、**ダッシュボード**が開きます。 **ダッシュボード** ページには、既定のタイルのセットが用意されています。これらのタイルを削除したり新しいタイルを追加したりして、ページをカスタマイズできます。

    ![Azure ポータルのダッシュボードのスクリーンショット](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  **[参照]** メニューで、**[Intune]** を探します。![[Intune] が強調表示されている [参照] メニューのスクリーンショット](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  **[Intune]、[Intune モバイル アプリケーション管理]、[設定]** の順にクリックします。

    ![[Intune モバイル アプリケーション管理] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > ブレードを **[開始]** ページにピン留めするには、ブレードの **[ピン留め]** オプションを使用できます。   **[Intune モバイル アプリケーション管理ブレード]**のピン アイコンをクリックして、これを **[開始]** ページにピン留めします。

    ![ピン アイコンが強調表示されている [Intune モバイル アプリケーション管理] ブレードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Intune タイルが固定されているダッシュボードのスクリーンショット](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## 次のステップ
[Get ready to configure mobile app management policies (モバイル アプリ管理ポリシーの展開)](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


