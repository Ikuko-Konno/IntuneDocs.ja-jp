---
title: デバイスに証明書がない | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: NOINDEX, NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 753fce1e37014e0ad4dac44f1eeb9284482e8f83
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72500175"
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>電話に通常インストールされている証明書が Android デバイスにない

デバイスが Intune に登録されておらず、電話に通常インストールされる証明書がない場合は、ポータル サイト アプリにサインインすることはできません。 サインインしようとすると、次のメッセージが表示されます。

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

この問題は、必要な証明書を [Digicert の証明書ページ](https://www.digicert.com/digicert-root-certificates.htm)から取得することで解決できます。

1. __Baltimore CyberTrust Root__ 証明書を見つけてダウンロードします。 直接[こちら](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt)からダウンロードすることもできます。

2. 画面の上から下へドラッグして最近の通知の一覧を表示し、 **[BaltimoreCyberTrustRoot.crt]** をタップします。

3. デバイスに**証明書の命名**を求めるメッセージが表示されます。 表示された既定の証明書名を変更しないでください。

4. **[認証情報の使用]** が **[VPN とアプリ]** に設定されていることを確認し、 **[OK]** をタップします。

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. ブラウザーとポータル サイト アプリを閉じます。

6. 会社のポータル アプリをもう一度開きます。 これで、会社のポータル アプリにサインインできるようになりました。 ポータル サイト アプリを使用できるようにならない場合は、[ポータル Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)に記載の情報を参考に、詳細な手順について会社のサポートに問い合わせてください。

>[!NOTE]
> この証明書をインストールしても問題が解決せず、別の "証明書が見つかりません" というメッセージが表示される場合は、[不足している証明書をインストールする](your-device-is-missing-an-IT-required-certificate-android.md)別の手順を実行する必要があります。

サポートが必要な場合は、 社内サポートに問い合わせてください。 連絡先情報については、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)をご確認ください。
