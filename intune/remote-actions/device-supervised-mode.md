---
title: Microsoft Intune で iOS の監視モードを有効にする
titleSuffix: ''
description: Intune で iOS の監視モードを有効にする方法を説明します。
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e995dbc89321bf844151accd654a2d17d35afd9
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "73713429"
---
# <a name="turn-on-ios-supervised-mode"></a>iOS の監視モードを有効にする


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Apple iOS の監視モードでは、デバイスを管理するときに、大規模に展開されている企業が所有するデバイスを有効活用する、多くのオプションが管理者に提供されます。 たとえば、AirDrop を制限したり、ユーザーがデバイスの名前を変更できないようにすることができます。 監視モードを必要とする設定の一覧については、「[Microsoft Intune での iOS デバイスの制限設定](../configuration/device-restrictions-ios.md)」を参照してください。

Intune は Apple [Device Enrollment Program (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) の一部として監視モードをサポートしています。

監視を必要とする Apple コントロールのリストは、Apple の「[ペイロード設定のリファレンス](http://help.apple.com/configurator/mac/2.4/#/cad5370d089)」を参照してください。

## <a name="turn-on-supervised-mode-during-enrollment"></a>登録時に監視モードで有効にする

[Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)では、[DEP で Apple 登録プロファイルを作成](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile)するときに、デバイスの監視モードを有効にすることができます。 **[デバイス管理の設定]** で、 **[監督下]** チェック ボックスをオンにします。

## <a name="turn-on-supervised-mode-after-enrollment"></a>登録後に監視モードで有効にする

登録後に監視モードを有効にする唯一の方法は、iOS デバイスを Mac に接続し、(デバイスをリセットする) [Apple Configurator を使用する](../enrollment/apple-configurator-enroll-ios.md)ことです。 登録後に、Intune でデバイスを監視モードに構成することはできません。

## <a name="identify-a-supervised-device"></a>監視対象デバイスを識別する

デバイスが監視対象かどうかを判断するには、ロック画面または **[バージョン情報]** ページを確認します。
- デバイスのロック画面には、"**この iPhone は "会社名" によって管理されています**" と表示されます。
- デバイスの **[バージョン情報]** ページには、"**この iPhone は監視されています。"会社名" はインターネット トラフィックを監視し、このデバイスの位置を特定できます。** " と表示されます。

## <a name="next-steps"></a>次の手順

その他のデバイス管理オプションについては、「[Microsoft Intune デバイスの管理とは](device-management.md)」を参照してください。
