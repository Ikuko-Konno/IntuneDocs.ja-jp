---
title: "ホスト型 Exchange 用の Exchange Connector | Microsoft Intune"
description: "Exchange ActiveSync モバイル デバイス管理 (MDM) をサポートするために、Intune を Office 365 Exchange サービスに接続する。"
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 63697222f024169d9450b9f4fea8c666353e72cc


---

# Exchange Online 用の Intune Service to Service Connector の構成

Office 365 でホストされている Microsoft Intune および Exchange Online サービスに接続するには、この情報を使用します。

## Service to Service Connector の要件
**Service to Service Connector** は、ホスト型 Exchange のみをサポートします。また、社内インフラストラクチャの要件はありません。

|要件|詳細情報|
|---------------|--------------------|
|ホスト型 Exchange が構成済みで実行中である|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|モバイル デバイス管理機関| [モバイル デバイスの管理機関を Microsoft Intune に設定します](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Microsoft Exchange のバージョン|Exchange Server 2013 以降のテナントがある Office 365 サブスクリプションが必要です。 テナントが Exchange Server 2013 以降であれば、コネクタは、その同じ環境内の Exchange Server 2010 をサポートします。|
|Active Directory の同期|Intune Connector を使用できるようにするには、[Active Directory の同期をセットアップ](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3)して、ローカル ユーザーとセキュリティ グループが Azure Active Directory のインスタンスと同期されるようにする必要があります。|

### Exchange コマンドレットの要件

Intune Exchange Connector が使用する Exchange Online ユーザー アカウントも作成する必要があります。 このアカウントは、Intune 管理コンソールを使用し、次の必要な Windows PowerShell Exchange コマンドレットを実行するアクセス許可を持っている必要があります。

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy、Set-MobileDeviceMailboxPolicy、New-MobileDeviceMailboxPolicy、Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule、Set-ActiveSyncDeviceAccessRule、New-ActiveSyncDeviceAccessRule、Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Service to Service Connector のセットアップ

1. Exchange 管理者権限と[上記](#exchange-cmdlet-requirements)のコマンドレットのアクセス許可を持つユーザー アカウントで、[Microsoft Intune 管理コンソール](http://manage.microsoft.com)を開きます。 Microsoft Intune は、現在ログインしているユーザーの電子メール アドレスを使用して、接続をセットアップします。

2.  ワークスペースのショートカット ウィンドウで**[管理]** を選択し、**[モバイル デバイス管理]** > **[Microsoft Exchange]**  > **[Exchange 接続のセットアップ]** に進みます。
![[Service To Service Connector のセットアップ] ページ](../media/intunesa5cservicetoserviceconnector.png)

3.  **[Exchange 接続のセットアップ]** ページで **[Service To Service Connector のセットアップ]**を選びます。


Service to Service Connector は自動的に構成され、ホスト型 Exchange 環境と同期されます。

## Exchange 接続の確認

Exchange Connector の構成が正常に完了したら、[Microsoft Intune 管理コンソール](http://manage.microsoft.com)で、**[管理]** を選択し、**[モバイル デバイス管理]** > **[Microsoft Exchange]** に進んで、**[Exchange の接続情報]** に表示される設定内容の詳細を確認します。

また、前回いつ同期が完了したかも確認することができます。



<!--HONumber=Jul16_HO3-->


