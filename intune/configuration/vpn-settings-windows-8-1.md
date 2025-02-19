---
title: Windows 8.1 デバイス用の Microsoft Intune の VPN 設定
titleSuffix: ''
description: Windows 8.1 を実行するデバイスでの VPN 接続の構成に使用できる Intune 設定について説明します。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12267ce4e29fe2d53d01aa8115cafbf2196d50ed
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72490843"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>Windows 8.1 を実行するデバイス用に Microsoft Intune で VPN 設定を構成する

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

この記事では、Windows 8.1 を実行するデバイスでの VPN 接続の構成に使用できる Intune 設定を示します。

選択した設定によっては、次の一覧に記載されている値の一部を構成できない場合があります。

## <a name="base-vpn-settings"></a>基本 VPN 設定


- **[Apply all settings to Windows 8.1 only (すべての設定を Windows 8.1 のみに適用する)]** - これは、Intune クラシック ポータルで構成できる設定です。 Azure Portal では、この設定は変更できません。 これが **[構成済み]** に設定されている場合は、すべての設定が Windows 8.1 デバイスのみに適用されます。 **[未構成]** に設定されている場合、これらの設定は Windows 10 デバイスにも適用されます。
- **[接続名]** - この接続の名前を入力します。 ユーザーがデバイスで使用可能な VPN 接続の一覧を参照するときに、この名前が表示されます。
- **[サーバー]** - デバイスの接続先とする 1 台以上の VPN サーバーを追加します。
  - **[追加]** - **[行の追加]** ページが開き、以下の情報を指定できます。
    - **[説明]** - **Contoso VPN サーバー**のような、サーバーを表す名前を指定します。
    - **[IP アドレスまたは FQDN]** - デバイスが接続する VPN サーバーの IP アドレスまたは完全修飾ドメイン名を指定します。 例: **192.168.1.1**、**vpn.contoso.com**。
    - **[既定のサーバー]** - このサーバーを、デバイスで接続を確立するために使用する既定のサーバーとして有効にします。 既定のサーバーとして設定するサーバーの数は 1 台のみにしてください。
  - **[インポート]** - 説明、IP アドレスまたは FQDN、既定のサーバーという形式でまとめられた、コンマ区切りのサーバーのリストを含むファイルを参照します。 **[OK]** を選択すると、これらが **[サーバー]** リストにインポートされます。
  - **[エクスポート]** - サーバーのリストをコンマ区切り値 (csv) ファイルにエクスポートします。

- **[接続の種類]** - 以下のベンダーの一覧から VPN 接続の種類を選択します。
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **[ログイン グループまたはドメイン]** (SonicWall Mobile Connect のみ) - 接続先のログイン グループまたはドメインの名前を指定します。

- **[ロール]** (Pulse Secure のみ) - この接続に対するアクセス権を持つユーザー ロールの名前を指定します。 ユーザー ロールを使用して、個人の設定とオプションを定義し、特定のアクセス機能を有効または無効にします。

- **[領域]** (Pulse Secure のみ) - 使用する認証領域の名前を指定します。 認証領域とは、接続の種類が [Pulse Secure] の場合に使用される認証リソースのグループを表します。


- **[カスタム XML]** - VPN 接続を構成する任意のカスタム XML コマンドを指定します。

**Pulse Secure の例:**

```xml
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**CheckPoint Mobile VPN の例:**

```xml
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**SonicWall Mobile Connect の例:**

```xml
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**F5 Edge Client の例:**

```xml
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

詳細については、カスタムの XML コマンドの記述方法に関する各製造元の VPN のドキュメントを参照してください。


## <a name="proxy-settings"></a>プロキシの設定

- **[自動的にプロキシ設定を検出する]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合は、デバイスで接続の設定を自動的に検出するかどうかを指定します。 詳細については、Windows Server のマニュアルを参照してください。
- **[自動構成スクリプト]** - ファイルを使用してプロキシ サーバーを構成します。 構成ファイルを含む**プロキシ サーバー URL** を入力します。 たとえば、「`http://proxy.contoso.com`」と入力します。
- **[プロキシ サーバーを使用する]** - プロキシ サーバーの設定を手動で入力する場合は、このオプションを有効にします。
  - **[アドレス]** - プロキシ サーバーのアドレスを (IP アドレスとして) 入力します。
  - **[ポート番号]** - プロキシ サーバーに関連付けられているポート番号を入力します。
- **[ローカル アドレスにはプロキシ サーバーを使用しない]** - VPN サーバーが接続にプロキシ サーバーを必要とする場合、指定したローカル アドレスに対してプロキシ サーバーを使用しないようにするには、このオプションを選択します。 詳細については、Windows Server のマニュアルを参照してください。
