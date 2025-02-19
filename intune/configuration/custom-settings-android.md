---
title: Microsoft Intune で Android デバイスにカスタム設定を追加する - Azure | Microsoft Docs
description: 事前共有キーを使った WiFi プロファイルの作成、アプリごとの VPN プロファイルの作成、Samsung Knox Standard デバイスのアプリの許可/拒否などを Microsoft Intune で行うには、Android デバイス用のカスタム プロファイルを追加または作成します
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17f0b30d0a8c706a7fdff1c7da722eeccdf097eb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72495790"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune で Android デバイス用のカスタム設定を使用する

Microsoft Intune では、"カスタム プロファイル" を使用して Android デバイス用のカスタム設定を追加または作成できます。 カスタム プロファイルは Intune の機能です。 Intune に組み込まれていないデバイスの設定と機能を追加するように設計されています。

Android のカスタム プロファイルでは、Open Mobile Alliance Uniform Resource Identifier (OMA-URI) 設定を使って、Android デバイスのさまざまな機能を構成します。 通常、これらの設定は、モバイル デバイスの製造元によってこれらの機能を制御するために使われます。

カスタム プロファイルを使うと、以下の Android 設定を構成して割り当てることができます。 次の設定は Intune に組み込まれていません。

- [事前共有キーを使用した Wi-Fi プロファイルの作成](/intune/wi-fi-profile-shared-key)
- [アプリごとの VPN プロファイルを作成する](/intune/android-pulse-secure-per-app-vpn)
- [Samsung Knox Standard デバイス用のアプリを許可またはブロックする](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> カスタム プロファイルでは、ここで挙げられている設定のみを構成できます。 Android デバイスでは、構成できる OMA-URI 設定の完全な一覧が表示されません。 他の設定が表示されるようにしたい場合は、[Intune Uservoice サイト](https://microsoftintune.uservoice.com/forums/291681-ideas)で他の設定に投票してください。

この記事では、Android デバイス用のカスタム プロファイルを作成する方法を示します。

## <a name="create-the-profile"></a>プロファイルの作成

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) にサインインします。
2. **[デバイス構成]**  >  **[プロファイル]**  >  **[プロファイルの作成]** の順に選択します。
3. 次の設定を入力します。

    - **名前**: `android custom profile` のようにプロファイルの名前を入力します。
    - **説明**: プロファイルの説明を入力します
    - **プラットフォーム**: **[Android]** を選びます。
    - **プロファイルの種類**: **[カスタム]** を選択します。

4. **[OMA-URI のカスタム設定]** で、 **[追加]** を選択します。 次の設定を入力します。

    - **名前**: 簡単に見つけられるように、OMA-URI 設定の一意の名前を入力します。
    - **説明**: 設定の概要および他の重要な詳細がわかる説明を入力します。
    - **OMA-URI**: 設定として使用する OMA-URI を入力します。
    - **データ型**: この OMA-URI の設定に使用するデータ型を選択します。 次のようなオプションがあります。

      - 文字列型
      - 文字列 (XML ファイル)
      - 日付と時刻
      - 整数型
      - 浮動小数点
      - ブール型
      - Base64 (ファイル)

    - **値**: 入力した OMA-URI に関連付けるデータ値を入力します。 値は、選択したデータ型に依存します。 たとえば、 **[日付と時刻]** を選択した場合は、日付の選択から値を選択します。

    設定を何か追加した後は、 **[エクスポート]** を選択できます。 **[エクスポート]** では、追加した値の一覧がコンマ区切り値 (.csv) ファイルで作成されます。

5. **[OK]** を選択して変更を保存します。 必要に応じて他の設定の追加を続けます。 
6. 終わったら、 **[OK]**  >  **[作成]** を選択して Intune プロファイルを作成します。 完了すると、プロファイルが **[デバイス構成 - プロファイル]** の一覧に表示されます。

## <a name="next-steps"></a>次の手順

プロファイルは作成されましたが、まだ何も行われていません。 次に、[プロファイルを割り当てます](device-profile-assign.md)。

[Android エンタープライズ デバイスでプロファイルを作成する](custom-settings-android-for-work.md)方法を確認してください。
