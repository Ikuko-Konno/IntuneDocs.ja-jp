---
title: Windows デバイスの登録を解除するとどうなるか | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6e3f61fc84458525ae2ff62887d64baea9542
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505949"
---
# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a>Intune から Windows デバイスの登録を解除するとどうなりますか。

お使いのデバイスの種類に関する情報については、このページの右側の**この記事内の項目**の下にあるリンクを使用してください。


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a>Windows 10、Windows 8.1、Windows 8、Windows 7、Windows Vista

- デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。

- Intune クライアント ソフトウェアをインストールしていた場合、コンピューターから削除されます。

- Intune Endpoint Protection ソフトウェアはコンピューターから削除されます。 コンピューターに別のウイルス対策ソフトウェアがインストールされており、無効になっている場合は、Intune Endpoint Protection を削除した後で、そのアプリケーションを再び有効にできます。 ポータル サイトから削除した後は、コンピューターの確認を行ってください。

    > [!IMPORTANT]
    > 他のウイルス対策ソフトウェアを再び有効にしない場合、または他のウイルス対策ソフトウェアがインストールされていない場合、コンピューターはウイルスおよびマルウェアに対して脆弱になる可能性があります。

- 追加時にデバイスで変更した設定がある場合 (カメラを無効にするなど)、その設定は適用されなくなります。

- コンピューターは、Intune サービスから自動的なソフトウェア更新プログラムまたはウイルス対策ソフトウェア更新プログラムを受信しなくなります。 ただし、コンピューターがどのようにセットアップされているかによって異なりますが、Windows Server Update Services、Windows Update、または Microsoft Update から、引き続き更新プログラムを受信できる可能性があります。

さらに Windows 8.1 の場合、

- お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。

- Windows Mail など、一部のメール アプリケーションは、デバイスに保存されている会社の電子メールにアクセスできなくなります。

- Wi-Fi または仮想プライベート ネットワークを使用して、社内ネットワークに接続できなくなる可能性があります。

- お使いのデバイスで、ファイルの共有または内部 Web サイトなど、一部の会社リソースにアクセスできなくなる可能性があります。

## <a name="windows-10-mobile-and-windows-phone-81"></a>Windows 10 Mobile および Windows Phone 8.1

- ポータル サイト アプリがデバイスからアンインストールされます。 これにより、そのデバイスはポータル サイトに表示されなくなります。さらに、ポータル サイトまたはポータル Web サイトからアプリをインストールできなくなります。

- お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。

- 追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。

    > [!IMPORTANT]
    > 例外は暗号化のポリシーのみです。暗号化のポリシーは引き続き適用されます。 会社のポリシーで Windows Phone の暗号化が必須にされていた場合、電話の暗号化を解除するには、 **[設定]** メニューを使用してリセットするしかありません。

## <a name="windows-rt-running-windows-81"></a>Windows 8.1 を実行している Windows RT

- ポータル サイト アプリがデバイスからアンインストールされます。 これにより、デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。

- お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。

- 追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。

- Wi-Fi または仮想プライベート ネットワークを使用して、社内ネットワークに接続できなくなる可能性があります。

- お使いのデバイスで、ファイルの共有または内部 Web サイトなど、一部の会社リソースにアクセスできなくなる可能性があります。

- Windows Mail など、一部のメール アプリケーションは、デバイスに保存されている会社の電子メールにアクセスできなくなります。

Windows RT デバイスを削除すると、次のような結果になります。

- ポータル サイト アプリがデバイスからアンインストールされます。 これにより、デバイスはポータル サイトに表示されなくなります。また、ポータル サイトからアプリをインストールできなくなります。

- お使いのデバイスで、会社のアプリと会社のデータを使用できなくなります。

- 追加時にデバイスで変更した設定がある場合 (カメラを無効にする、特定のパスワードの長さを必須にするなど)、その設定は適用されなくなります。

ご不明な点がある場合は、会社のサポートに問い合わせてください。 連絡先情報については、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)をご確認ください。
