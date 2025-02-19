---
title: Microsoft Intune での Android デバイス管理者の登録
titleSuffix: ''
description: デバイス管理者の登録を使用して、Android デバイスを Intune に登録します。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 678eb92bb6f5f23756092cd5d9cc1a645e1e8db3
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74562369"
---
# <a name="android-device-administrator-enrollment"></a>Android デバイス管理者の登録

Android デバイス管理者 ("従来の" Android 管理とも呼ばれ、Android 2.2 でリリースされました) は、Android デバイスを管理する方法の 1 つです。 しかし、[Android Enterprise](https://www.android.com/enterprise/management/) (Android 5.0 でリリース) では、強化された管理機能を使用できるようになりました。 Google では、より豊富で安全な最新のデバイス管理に移行するための努力の一環として、新しい Android リリースでのデバイス管理者のサポートを縮小させています。

そのため、このような縮小された機能を回避するために、新しいデバイスは、以下で説明するデバイス管理者のプロセスを使って登録しないようにすることをお勧めします。

また、同じ理由から、デバイスを Android 10 に更新する場合は、そのデバイスをデバイス管理者の管理以外に移行することもお勧めします。 

Android デバイス管理者のサポートに関する Intune サポートについて詳しくは、[「通知」セクション](../fundamentals/whats-new.md#decreasing-support-for-android-device-administrator)をご覧ください。

それでもユーザーがデバイス管理者の管理を使って各自の Android デバイスを登録するようにしたい場合は、次のセクションに進みます。  


> [!Note]  
> ハイブリッド モバイル デバイス管理 (ハイブリッド MDM。Intune による管理と System Center Configuration Manager コンソールの併用) では、Android 10 以降はサポートされません。ハイブリッド MDM は 2019 年 9 月 1 日にサービスを終了するためです。 まだハイブリッド MDM を使用している場合は、できるだけ早く Intune スタンドアロンに移行する必要があります。 移行に関するヘルプが必要な場合は、サポートにお問い合わせください。 詳細については、「[Move from Hybrid Mobile Device Management to Intune on Azure](https://aka.ms/hybrid_notification)」 (ハイブリッド MDM から Azure での Intune に移行する) を参照してください。

Google の Android Enterprise 機能について詳しくは、次の記事をご覧ください。
- [デバイス管理者から Android Enterprise への移行に関する Google のガイダンス](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [デバイス管理者 API の廃止計画に関する Google のドキュメント](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>デバイス管理者の登録を設定する

1. モバイル デバイスの管理を準備するには、MDM (モバイル デバイス管理) 機関を **Microsoft Intune** に設定する必要があります。 手順については、[MDM 機関の設定](../fundamentals/mdm-authority-set.md)に関するページを参照してください。 この項目は、モバイル デバイス管理について初めて Intune を設定するときに一度だけ設定します。
2. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインし、 **[デバイス]**  >  **[Android]**  >  **[Android の登録]**  >  **[デバイス管理者特権を持つ個人所有のデバイスと会社所有のデバイス]**  >  **[デバイス管理者によってデバイスを管理します]** に移動します。
3. [デバイスを登録する方法をユーザーに知らせます](/intune-user-help/enroll-your-device-in-intune-android)。  

ユーザーが登録した後に、[コンプライアンス ポリシーの割り当て](../protect/compliance-policy-create-android.md)、[アプリの管理](../apps/app-management.md)など、Intune でのデバイスの管理を開始することができます。

その他のユーザー タスクについては、次の記事を参照してください。
- [Microsoft Intune を使用したエンドユーザー エクスペリエンスに関するリソース](../fundamentals/end-user-educate.md)
- [Android デバイスを Intune で使用する](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>デバイス管理者の登録をブロックする
Android デバイス管理者のデバイスをブロックする場合や、個人所有の Android デバイス管理者のデバイスの登録のみをブロックする場合は、[デバイスの種類の制限の設定](enrollment-restrictions-set.md)に関するページをご覧ください。



## <a name="next-steps"></a>次の手順
- [コンプライアンス ポリシーの割り当て](../protect/compliance-policy-create-android.md)
- [アプリの管理](../apps/app-management.md)
