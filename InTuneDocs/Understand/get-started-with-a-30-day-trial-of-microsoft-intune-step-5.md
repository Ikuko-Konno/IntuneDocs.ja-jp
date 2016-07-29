---
title: "評価モバイル デバイスの登録 | Microsoft Intune"
description: "Intune の 30 日間無料評価版にサインアップするときに、モバイル デバイスを登録しアプリをインストールする方法"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 2424d52f800ae61dbadc0a3ae73c2b3f24d936c3


---

# 評価版モバイル デバイスを登録してアプリをインストールする
Intune を使用してモバイル デバイス管理をセットアップするには、まずモバイル デバイス管理機関を設定し、デバイス プラットフォームの管理を有効にして、ポータル サイト アプリでデバイスを登録する必要があります。 その後、発行した Microsoft Skype アプリケーションを展開できます。

## デバイス管理のサービスを準備する

1.  **Intune をモバイル デバイス管理機関に設定する**

    [Intune 管理コンソール](https://manage.microsoft.com/)で、**[管理]** &gt; **[モバイル デバイス管理]** の順に選択します。 **[タスク]**  >  **[MDM 機関の設定]** を選択してから、**[MDM 機関]** ダイアログ ボックスで **[はい]** を選択します。

2.  **デバイス プラットフォームの MDM を有効にする**

    管理対象のデバイス プラットフォームに対してモバイル デバイス管理を有効にします。 要件はプラットフォームによって異なります。

    -   **iOS と Mac OS X**: 「[Microsoft Intune を使用して iOS および Mac の管理をセットアップする](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune)」を参照してください。

    -   **Android**:Android モバイル デバイスは、ユーザーが、Google Play から入手できるポータル サイト アプリを使用して登録できます。 Intune での追加構成は不要です。

    -   **Windows Phone**: 「[Microsoft Intune を使用して Windows Phone の管理をセットアップする](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune)」を参照してください。

## テスト デバイスの登録

### iOS および Mac OS X
App Store の Microsoft Corporation から **Microsoft Intune ポータル サイト** アプリをインストールし、前の手順で追加した Intune ユーザー資格情報を使用してサインインします。 **[登録済みデバイス]** を表示して、デバイスを追加します。

### Android
[Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) の Microsoft Corporation から **Intune ポータル サイト** アプリをインストールし、前述の手順で追加した Intune ユーザー資格情報を使用してサインインします。

### Windows Phone 8。1
Windows Phone ストアの Microsoft Corporation から**ポータル サイト** アプリをインストールし、前述の手順で追加した Intune ユーザー資格情報を使用してサインインします。  **[登録済みデバイス]** を表示して、デバイスを追加します。

 ### Windows Phone 8。0
 **[システム設定]** &gt; **[業務用アプリ]** をクリックし、前述の手順で追加した Intune ユーザー資格情報を使用してサインインします。 ポータル サイト アプリがお使いの電話に展開されます。

**サーバー アドレス**の入力を求めるメッセージが表示された場合は、「manage.microsoft.com」と入力します。


## 以前に展開したアプリのインストール
モバイル デバイスでポータル サイトを開き、**[アプリ]** を選択して、**Microsoft Skype** をインストールします。

Intune を使用したモバイル デバイス管理の詳細については、「[Microsoft Intune にデバイスを登録する準備](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)」を参照してください。

### 次の手順
これで終了です。 *Microsoft Intune の評価*チュートリアルの手順 5 を修了しました。

>[!div class="step-by-step"]

>[&larr; **ポリシーの作成**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**オプションとその他の機能** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Jul16_HO3-->


