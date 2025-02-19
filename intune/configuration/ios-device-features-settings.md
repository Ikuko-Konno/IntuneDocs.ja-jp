---
title: Microsoft Intune の iOS デバイスの機能設定 - Azure | Microsoft Docs
description: AirPrint、ホーム画面のレイアウト、アプリの通知、共有デバイス、シングル サインイン、Web コンテンツ フィルター設定に関するすべての設定について、Microsoft Intune での iOS デバイスの構成設定をすべて説明します。 デバイス構成プロファイルでこれらの設定を使い、組織内でこのような Apple 機能を使うよう iOS デバイスを構成します。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e73612080e52c8eb49a0c090b68e917e24fef3ab
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992948"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>Intune で一般的な iOS 機能を使用するための iOS および iPadOS のデバイス設定

Intune には、iOS ユーザーが自分のデバイスでさまざまな Apple 機能を使用できるようになる組み込みの設定がいくつかあります。 たとえば、管理者は、iOS ユーザーが AirPrint プリンターを使用する方法の制御、ホーム画面のドックおよびページへのアプリとフォルダーの追加、アプリ通知の表示、ロック画面への資産タグの詳細の表示、シングル サインオン認証の使用、および証明書を使用したユーザーの認証を行うことができます。

これらの機能を使用して、iOS デバイスをご利用のモバイル デバイス管理 (MDM) ソリューションの一部として制御します。

この記事では、このような設定を一覧で示し、各設定の機能について説明します。 これらの機能の詳細について[は、iOS または macOS デバイスの機能設定の追加](../device-features-configure.md)に関するページを参照してください。

## <a name="before-you-begin"></a>始める前に

[iOS デバイス構成プロファイルを作成します](../device-features-configure.md)。

> [!NOTE]
> これらの設定は、さまざまな登録の種類に適用され、一部の設定はすべての登録オプションに適用されます。 さまざまな登録の種類の詳細については、「 [iOS の登録](../ios-enroll.md)」を参照してください。

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>設定の適用先: すべての登録の種類

> [!NOTE]
> すべてのプリンターを同じプロファイルに追加してください。 Apple では、複数の印刷プロファイルで同じデバイスを対象にすることを禁止しています。

- **[IP アドレス]** : プリンターの IPv4 アドレスまたは IPv6 アドレスを入力します。 ホスト名を使用してプリンターを識別している場合は、ターミナルでプリンターに ping を実行することで IP アドレスを取得できます。 詳細については、「IP アドレスとパスを取得する」 (この記事内) を参照してください。
- **[パス]** : 通常、このパスはネットワーク上のプリンターの `ipp/print` です。 詳細については、「IP アドレスとパスを取得する」 (この記事内) を参照してください。
- **[ポート]** : AirPrint の接続先のリスニング ポートを入力します。 このプロパティを空白のままにすると、AirPrint には既定のポートが使用されます。 iOS 11.0 以降で使用できます。
- **[TLS]** : トランスポート層セキュリティ (TLS) で AirPrint の接続を保護するには、 **[有効]** を選択します。 iOS 11.0 以降で使用できます。

放映されるプリントサーバーを追加するには、次のようにします。

- **[追加]** で AirPrint サーバーが一覧に追加されます。 多くの印刷プリントサーバーを追加できます。
- この情報を含むコンマ区切りファイル (.csv) を**インポート**します。 または、 **[エクスポート]** を使用して、追加した放映プリントサーバーの一覧を作成します。

### <a name="get-server-ip-address-resource-path-and-port"></a>サーバーの IP アドレス、リソース パス、ポートを取得する

AirPrinter サーバーを追加するには、プリンターの IP アドレス、リソース パス、およびポートが必要です。 この情報を取得する手順は次のとおりです。

1. AirPrint プリンターと同じローカル ネットワーク (サブネット) に接続している Mac 上で、( **/アプリケーション/ユーティリティ**から) **ターミナル**を開きます。
2. ターミナルで「`ippfind`」と入力し、Enter キーを押します。

    プリンター情報をメモします。 たとえば、`ipp://myprinter.local.:631/ipp/port1` のような内容が返されます。 最初の部分はプリンターの名前です。 最後の部分 (`ipp/port1`) はリソース パスです。

3. ターミナルで「`ping myprinter.local`」と入力し、Enter キーを押します。

   IP アドレスをメモします。 たとえば、`PING myprinter.local (10.50.25.21)` のような内容が返されます。

4. この IP アドレスとリソース パスの値を使用します。 この例では、IP アドレスは `10.50.25.21`、リソース パスは `/ipp/port1` です。

## <a name="home-screen-layout"></a>ホーム画面のレイアウト

この機能は、以下に適用されます。

- iOS 9.3 以降

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>設定の適用対象: 自動デバイス登録 (監視)

### <a name="dock"></a>ドッキング

**[ドッキング]** 設定で、iOS 画面の Dock に最大 6 つのアイテムまたはフォルダーを追加できます。 多くのデバイスではより少ないアイテムがサポートされています。 たとえば iPhone では最大で 4 つのアイテムがサポートされます。 この場合、追加した最初の 4 つのアイテムのみがデバイスに表示されます。

デバイスの Dock には最大 **6** つのアイテム (アプリとフォルダーの合計) を追加できます。

- **[追加]** : デバイスのドックにアプリまたはフォルダーを追加します。
- **[種類]** : **[アプリ]** または **[フォルダー]** を追加します。

  - **[アプリ]** : 画面のドックにアプリを追加するには、このオプションを選択します。 次を入力します。

    - **[アプリ名]** : アプリケーションの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
    - **[アプリ バンドル ID]** : アプリのバンドル ID を入力します。 例については、[組み込み iOS アプリのバンドル ID](bundle-ids-built-in-ios-apps.md) に関する記事を参照してください。

  - **[フォルダー]** : 画面のドックにフォルダーを追加するには、このオプションを選択します。

    フォルダー内のページに追加したアプリは、一覧と同じ順序で左から右に配置されます。 1 つのページに収まるよりも多くのアプリを追加すると、残りのアプリは別のページに移動します。

    - **[フォルダー名]** : 新しいフォルダーの名前を入力します。 この名前は、ユーザーに対してデバイス上に表示されます。
    - **[ページ一覧]** : ページを**追加**し、次のプロパティを入力します。

      - **[ページ名]** : ページの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
      - **[アプリ名]** : アプリケーションの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
      - **[アプリ バンドル ID]** : アプリのバンドル ID を入力します。 例については、[組み込み iOS アプリのバンドル ID](bundle-ids-built-in-ios-apps.md) に関する記事を参照してください。

      デバイスの Dock には最大 **20** ページまで追加できます。

> [!NOTE]
> [ドッキング] 設定を使用してアイコンを追加すると、ホーム画面と各ページ上のアイコンがロックされ、移動することができません。 これは iOS と Apple の MDM ポリシーのデザインに起因する可能性があります。

#### <a name="example"></a>例

次の例では、Dock 画面に "Safari"、"メール"、および "株価" アプリのみが表示されています。 "メール" アプリを選択すると、そのプロパティが表示されます。

![iOS Dock 設定のサンプル](./media/ios-device-features-settings/FfFiUcP.png)

iPhone にポリシーを割り当てると、ドックは次の画像のようになります。

![iPhone の iOS Dock のレイアウト サンプル](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>ページ

ホーム画面に表示するページと、各ページに表示するアプリを追加します。 ページに追加したアプリは、一覧と同じ順序で左から右に配置されます。 1 つのページに収まるよりも多くのアプリを追加すると、残りのアプリは別のページに移動します。

> [!TIP]
> ドラッグ アンド ドロップで、ホーム画面とページの一覧のアイテムの順序を変更できます。

デバイスには最大 **40** ページまで追加できます。

- **[ページ一覧]** : ページを**追加**し、次のプロパティを入力します。

  - **[ページ名]** : ページの名前を入力します。 この名前は Azure portal で参照用に使われ、iOS デバイスには "*表示されません*"。

  デバイスには最大 **60** アイテム (アプリとフォルダーの合計) まで追加できます。

  - **[追加]** : デバイスのページにアプリまたはフォルダーを追加します。

    - **[種類]** : **[アプリ]** または **[フォルダー]** を追加します。

      - **[アプリ]** : 画面のページにアプリを追加するには、このオプションを選択します。 次の項目も入力します。

        - **[アプリ名]** : アプリケーションの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
        - **[アプリ バンドル ID]** : アプリのバンドル ID を入力します。 例については、[組み込み iOS アプリのバンドル ID](bundle-ids-built-in-ios-apps.md) に関する記事を参照してください。

      - **[フォルダー]** : 画面のドックにフォルダーを追加するには、このオプションを選択します。

        フォルダー内のページに追加したアプリは、一覧と同じ順序で左から右に配置されます。 1 つのページに収まるよりも多くのアプリを追加すると、残りのアプリは別のページに移動します。

        - **[フォルダー名]** : フォルダーの名前を入力します。 この名前は、ユーザーに対してデバイス上に表示されます。
        - **[追加]** : フォルダーにページを追加します。 また、次のプロパティも入力します。

          - **[ページ名]** : ページの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
          - **[アプリ名]** : アプリケーションの名前を入力します。 この名前は Azure portal での参照用に使用されます。 iOS デバイスには "*表示されません*"。
          - **[アプリ バンドル ID]** : アプリのバンドル ID を入力します。 例については、[組み込み iOS アプリのバンドル ID](bundle-ids-built-in-ios-apps.md) に関する記事を参照してください。

#### <a name="example"></a>例

次の例では、**Contoso** という新しいページが追加されます。 ページには、"友達を探す" と "設定" アプリが表示されています。 "設定" アプリを選択すると、そのプロパティが表示されます。

![iOS ホーム画面の設定例](./media/ios-device-features-settings/Jc2OxyX.png)

iPhone にポリシーを割り当てると、ページは次の画像のようになります。

![ホーム画面が変更された iOS デバイス](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>アプリの通知

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>設定の適用対象: 自動デバイス登録 (監視)

- **[追加]** : アプリの通知を追加します。

    ![Intune の iOS プロファイルでアプリの通知を追加する](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **[アプリ バンドル ID]** : 追加するアプリの**アプリ バンドル ID** を入力します。 例については、[組み込み iOS アプリのバンドル ID](bundle-ids-built-in-ios-apps.md) に関する記事を参照してください。
  - **[アプリ名]** : 追加するアプリの名前を入力します。 この名前は Azure portal での参照用に使用されます。 デバイスには "*表示されません*"。
  - **[発行元]** : 追加するアプリの発行元を入力します。 この名前は Azure portal での参照用に使用されます。 デバイスには "*表示されません*"。
  - **[通知]** : アプリがデバイスに通知を送信するのを**有効**または**無効**にします。
    - **[通知センターに表示する]** : **有効**にすると、アプリがデバイスの通知センターに通知を表示することを許可します。 **[無効]** にすると、アプリが通知センターに通知を表示することを禁止します。
    - **[ロック画面に表示する]** : **[有効]** を選択すると、アプリからの通知がデバイスのロック画面に表示されます。 **[無効]** にすると、アプリがロック画面に通知を表示することを禁止します。
    - **[アラートの種類]** : デバイスのロックが解除されているときの通知の表示方法を選択します。 次のようなオプションがあります。
      - **[なし]** : 通知は表示されません。
      - **[バナー]** : 通知を示すバナーが短時間表示されます。
      - **[モデル]** : 通知が表示され、ユーザーはデバイスの使用を続ける前に、手動でこの通知を消す必要があります。
    - **[アプリ アイコンのバッジ]** : アプリ アイコンにバッジを追加するには、 **[有効]** を選択します。 バッジは、通知を送信したアプリを意味します。
    - **[サウンド]** : **[有効]** を選択すると、通知の配信時にサウンドを再生します。

## <a name="lock-screen-message"></a>ロック画面のメッセージ

この機能は、以下に適用されます。

- iOS 9.3 以降

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>設定の適用対象: 自動デバイス登録 (監視)

- **[資産タグ情報]** : デバイスの資産タグに関する情報を入力します。 たとえば、「`Owned by Contoso Corp`」や「`Serial Number: {{serialnumber}}`」と入力します。

  入力したテキストは、デバイスのサインイン ウィンドウとロック画面に表示されます。

- **[ロック画面の脚注]** : デバイスの紛失または盗難時に、返却に役立つようなメモを入力します。 必要な任意のテキストを入力できます。 たとえば、`If found, call Contoso at ...` のようなものを入力します。

  デバイス トークンを使用して、このようなフィールドにデバイス固有の情報を追加することもできます。 たとえば、シリアル番号を表示するには、`Serial Number: {{serialnumber}}` と入力します。 ロック画面には、`Serial Number 123456789ABC` のようにテキストが表示されます。 変数を入力するときは、必ず中かっこ `{{ }}` を使用してください。 [アプリの構成トークン](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list)に関する記事には、使用できる変数の一覧が掲載されています。 `deviceName` または他のデバイス固有の値を使用することもできます。

  > [!NOTE]
  > 変数は UI で検証されず、大文字と小文字が区別されます。 その結果、不適切な入力で保存されたプロファイルが表示される場合があります。 たとえば、`{{deviceid}}` の代わりに `{{DeviceID}}` を入力した場合、リテラル文字列がデバイスの一意の ID の代わりに表示されます。 正しい情報を入力してください。

## <a name="single-sign-on"></a>シングル サインオン

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>設定の適用先: デバイスの登録、デバイスの自動登録 (監視)

- **AAD からのユーザー名の属性**: Intune によって、Azure AD で各ユーザーに対してこの属性が検索されます。 次に Intune によって個々のフィールド (UPN など) にデータが入力され、その後で、デバイスにインストールされる XML が生成されます。 次のようなオプションがあります。

  - **[ユーザー プリンシパル名]** : UPN は次のように解析されます。

    ![ユーザー名属性](./media/ios-device-features-settings/User-name-attribute.png)

    **[領域]** テキスト ボックスに入力したテキストを使用して領域を上書きすることもできます。

    たとえば、Contoso にはヨーロッパ、アジア、北米などいくつかの領域があります。 Contoso は、アジアのユーザーが SSO を使用できるようにしたいと考えており、このアプリには `username@asia.contoso.com` 形式の UPN が必要です。 **[ユーザー プリンシパル名]** を選択すると、各ユーザーの領域は Azure AD から取得されます。これが `contoso.com` です。 そのため、アジアのユーザーの場合は、 **[ユーザー プリンシパル名]** を選択し、「`asia.contoso.com`」と入力します。 エンド ユーザーの UPN は `username@contoso.com` ではなく、`username@asia.contoso.com` になります。

  - **[Intune デバイス ID]** : Intune によって Intune デバイス ID が自動的に選択されます。

    既定では、アプリで使う必要があるのはデバイス ID だけです。 ただし、アプリがデバイス ID と共に領域を使う場合は、[領域] テキスト ボックスに領域を入力できます。

    > [!NOTE]
    > 既定では、デバイス ID を使う場合は領域を空のままにします。

  - **[Azure AD デバイス ID]**

- **[領域]** : URL のドメイン部分を入力します。 たとえば、「`contoso.com`」と入力します。
- **シングル サインオンを使用する URL プレフィックス**: 組織内の URL の中でユーザーのシングル サインオン認証を必要とするものがあれば、それを**追加**します。

  たとえば、ユーザーがそのようなサイトに接続すると、iOS デバイスによってシングル サインオンの資格情報が使用されます。 ユーザーはいかなる追加の資格情報も入力する必要がありません。 多要素認証が有効な場合、ユーザーは第 2 の認証情報を入力する必要があります。

  > [!NOTE]
  > これらの URL は、適切な形式の FQDN である必要があります。 Apple で要求されている形式は `http://<yourURL.domain>` です。

  URL の一致パターンは、`http://` または `https://` で始まっている必要があります。 単純な文字列一致が実行されるので、URL プレフィックス `http://www.contoso.com/` は `http://www.contoso.com:80/` とは一致しません。 iOS 10.0 以降では、単一のワイルドカード \* を使用して、一致するすべての値を入力できます。 たとえば、`http://*.contoso.com/` は `http://store.contoso.com/` と `http://www.contoso.com` の両方と一致します。

  パターン `http://.com` はすべての HTTP URL と一致し、`https://.com` はすべての HTTPS URL と一致します。

- **シングル サインオンを使用するアプリ**: シングル サインオンを使用できるエンド ユーザーのデバイスにアプリを**追加**します。

  `AppIdentifierMatches` 配列には、アプリ バンドル ID と一致する文字列が含まれる必要があります。 これらの文字列では、完全に一致する値 (`com.contoso.myapp` など) を指定するか、\* ワイルドカード文字を使用してバンドル ID のプレフィックス一致を入力できます。 ワイルドカード文字は、ピリオド文字 (.) の後に指定する必要があり、文字列の最後で 1 回だけ使えます (`com.contoso.*` など)。 ワイルドカードが含まれる場合は、バンドル ID がプレフィックスで始まるすべてのアプリが、アカウントへのアクセスを許可されます。

  **[アプリ名]** を使用し、バンドル ID の識別に役立つわかりやすい名前を入力します。

- **[資格情報更新証明書]** : 認証に (パスワードではなく) 証明書を使用する場合は、認証証明書として既存の SCEP または PFX 証明書を選択します。 通常、この証明書は、VPN、Wi-Fi、メールなどの他のプロファイル用にユーザーに展開されるものと同じ証明書です。

## <a name="web-content-filter"></a>Web コンテンツ フィルター

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>設定の適用対象: 自動デバイス登録 (監視)

- **[フィルターの種類]** : 特定の Web サイトを許可する場合に選択します。 次のようなオプションがあります。

  - **[URL の構成]** : Apple の組み込み Web フィルターを使用します。不適切または性的に露骨な言葉など、成人向け用語を探すものです。 この機能によって、各 Web ページが読み込み時に評価され、不適切なコンテンツが特定され、ブロックされます。 また、フィルターで確認したくない URL を追加することもできます。 または、Apple のフィルター設定に関係なく、特定の URL をブロックします。

    - **[許可する URL]** : 許可する URL を**追加**します。 これらの URL では、Apple の Web フィルターがバイパスされます。

        > [!NOTE]
        > 入力する URL は、Apple Web フィルターで評価されたくない URL です。 これらの URL は、許可される Web サイトの一覧ではありません。 許可される Web サイトの一覧を作成するには、 **[フィルターの種類]** を **[特定の Web サイトのみ]** に設定します。

    - **[ブロックする URL]** : Apple Web フィルター設定にかかわらず、開かないようにする URL を**追加**します。

  - **[特定の Web サイトのみ]** (Safari Web ブラウザーのみ): これらの URL は Safari ブラウザーのブックマークに追加されます。 ユーザーはこれらのサイトに**のみ**アクセスが許可され、他のサイトを開くことはできません。 このオプションは、ユーザーがアクセスできる URL の正確な一覧がわかっている場合にのみ使います。

    - **[URL]** : 許可する Web サイトの URL を入力します。 たとえば、「`https://www.contoso.com`」と入力します。
    - **ブックマークパス**: Apple はこの設定を変更しました。 すべてのブックマークは、 **[承認済みサイト]** フォルダーにあります。 ブックマークは、入力したブックマークパスには入りません。
    - **[タイトル]** : ブックマークのわかりやすいタイトルを入力します。

    URL を入力しないと、エンド ユーザーは `microsoft.com`、`microsoft.net`、および `apple.com` 以外の Web サイトにアクセスできません。 これらの URL は Intune によって自動的に許可されます。

## <a name="single-sign-on-app-extension"></a>シングル サインオン アプリの拡張機能

この機能は、以下に適用されます。

- iOS 13.0 以降
- iPadOS 13.0 以降

### <a name="settings-apply-to-all-enrollment-types"></a>設定の適用先: すべての登録の種類

- **Sso アプリ拡張機能の種類**: sso アプリ拡張機能の種類を選択します。 次のようなオプションがあります。

  - **未構成**: アプリの拡張機能は使用されません。 アプリの拡張機能を無効にするには、SSO アプリの拡張機能の種類を **[未構成]** に切り替えます。
  - **リダイレクト**: 汎用のカスタマイズ可能なリダイレクトアプリ拡張機能を使用して、最新の認証フローで SSO を実行します。 組織のアプリ拡張機能の拡張機能 ID がわかっていることを確認してください。
  - **資格情報**: 汎用のカスタマイズ可能な資格情報アプリ拡張機能を使用して、チャレンジと応答の認証フローで SSO を実行します。 組織のアプリ拡張機能の拡張機能 ID がわかっていることを確認してください。
  - **Kerberos**: iOS 13.0 (およびそれ以降) および iPadOS 13.0 (およびそれ以降) に含まれる Apple の組み込みの Kerberos 拡張機能を使用します。 このオプションは、Kerberos 固有の**資格情報**アプリ拡張機能です。

  > [!TIP]
  > **リダイレクト**と**資格情報**の種類を使用して、独自の構成値を追加して拡張機能を通過します。 **資格情報**を使用している場合は、Apple によって提供される、 **Kerberos**の種類に組み込まれている構成設定を使用することを検討してください。

- **拡張機能 ID** (リダイレクトと資格情報): SSO アプリ拡張機能を識別するバンドル識別子 (`com.apple.extensiblesso`など) を入力します。

- **チーム ID** (リダイレクトと資格情報): SSO アプリ拡張機能のチーム識別子を入力します。 チーム識別子は、`ABCDE12345`のように、Apple によって生成される10文字の英数字 (数字と文字) 文字列です。 チーム ID は必要ありません。

  [チーム ID を検索](https://help.apple.com/developer-account/#/dev55c3c710c)します (Apple の web サイトを開きます)。詳細については、こちらを参照してください。

- [**領域**(資格情報と Kerberos)]: 認証領域の名前を入力します。 領域名は、`CONTOSO.COM`のように大文字で指定する必要があります。 通常、領域名は DNS ドメイン名と同じですが、すべて大文字で指定します。

- [**ドメイン**(資格情報と Kerberos)]: SSO 経由で認証できるサイトのドメイン名またはホスト名を入力します。 たとえば、web サイトが `mysite.contoso.com`場合、`mysite` はホスト名、`contoso.com` がドメイン名になります。 ユーザーがこれらのサイトのいずれかに接続すると、アプリ拡張機能によって認証チャレンジが処理されます。 この認証により、ユーザーは顔 ID、タッチ ID、または Apple pincode/パスコードを使用してサインインできます。

  - シングルサインオンアプリ拡張機能の Intune プロファイル内のすべてのドメインは一意である必要があります。 さまざまな種類の SSO アプリ拡張機能を使用している場合でも、どのサインオンアプリ拡張機能プロファイルでもドメインを繰り返すことはできません。
  - これらのドメインでは大文字と小文字が区別されません。

- **Url** (リダイレクトのみ): リダイレクトアプリ拡張機能が SSO を実行するための id プロバイダーの URL プレフィックスを入力します。 ユーザーがこれらの Url にリダイレクトされると、SSO アプリ拡張機能が介入し、SSO を要求します。

  - Intune シングルサインオンアプリ拡張機能プロファイル内のすべての Url は一意である必要があります。 さまざまな種類の SSO アプリ拡張機能を使用している場合でも、任意の SSO アプリ拡張機能プロファイルでドメインを繰り返すことはできません。
  - Url は、 http://または https://で始まる必要があります。

- **追加の構成**(リダイレクトと資格情報): SSO アプリ拡張機能に渡す追加の拡張機能固有のデータを入力します。
  - **キー**: `user name`など、追加する項目の名前を入力します。
  - **種類**: データの種類を入力します。 次のようなオプションがあります。

    - 文字列型
    - ブール: **構成値** に、`True` または `False`を入力します。
    - 整数: **構成値** に数値を入力します。
    
  - **値**: データを入力します。

  - **[追加]** : 選択した構成キーを追加します。

- **キーチェーンの使用法**(Kerberos のみ): パスワードが保存されてキーチェーンに格納されないようにするには、 **[ブロック]** を選択します。 **[未構成]** (既定値) を指定すると、パスワードを保存してキーチェーンに格納できます。
- **顔 id、タッチ id、またはパスコード**(Kerberos のみ **): ユーザー**は、ユーザーが顔 id、タッチ Id、または Apple パスコードを入力して、追加したドメインにサインインすることを強制します。 **[未構成]** (既定) では、ユーザーはサインインに生体認証やパスコードを使用する必要がありません。
- **既定の領域**(Kerberos のみ): 既定の領域として入力した**領域**の値を設定するには、[**有効**にする] を選択します。 **未構成**(既定) では、既定の領域は設定されません。

  > [!TIP]
  > - 組織で複数の Kerberos SSO アプリ拡張機能を構成している場合は、この設定**を有効に**します。
  > - 複数のレルムを使用している場合は、この設定**を有効に**します。 これにより、入力した**領域**の値が既定の領域として設定されます。
  > - 領域が1つしかない場合は、**構成しません**(既定)。

- [**プリンシパル名**(kerberos のみ)]: kerberos プリンシパルのユーザー名を入力します。 領域名を含める必要はありません。 たとえば、`user@contoso.com`では、`user` がプリンシパル名、`contoso.com` が領域名です。

  > [!TIP]
  > - また、`{{ }}`中かっこを入力することによって、プリンシパル名に変数を使用することもできます。 たとえば、ユーザー名を表示するには、「`Username: {{username}}`」と入力します。 
  > - ただし、変数の代入に注意してください。変数は UI で検証されず、大文字と小文字が区別されるためです。 正しい情報を入力してください。

- **Active Directory サイトコード**(kerberos のみ): kerberos 拡張機能で使用する Active Directory サイトの名前を入力します。 Kerberos 拡張機能によって Active Directory サイトコードが自動的に検出される可能性があるため、この値を変更する必要はありません。
- [**キャッシュ名**(kerberos のみ)]: kerberos キャッシュの汎用セキュリティサービス (GSS) 名を入力します。 多くの場合、この値を設定する必要はありません。
- **アプリバンドル id** (Kerberos のみ): デバイスでシングルサインオンを使用する必要があるアプリバンドル識別子を**追加**します。 これらのアプリには、Kerberos チケット保証チケットと認証チケットへのアクセス権が付与され、アクセスが許可されているサービスに対してユーザーを認証します。
- [**ドメイン領域マッピング**(Kerberos のみ)]: 領域にマップするドメイン DNS サフィックスを**追加**します。 ホストの DNS 名が領域名と一致しない場合に、この設定を使用します。 このカスタムドメインから領域へのマッピングを作成する必要はほとんどありません。
- [ **Pkinit 証明書**(kerberos のみ)]: Kerberos 認証に使用できる、初期認証 (pkinit) 証明書の公開キー暗号化を**選択し**ます。 Intune で追加した[PKCS](../protect/certficates-pfx-configure.md)または[SCEP](../protect/certificates-scep-configure.md)証明書から選択できます。 証明書の詳細については、「 [Microsoft Intune での認証に証明書を使用する](../protect/certificates-configure.md)」を参照してください。

## <a name="wallpaper"></a>壁紙

イメージのないプロファイルが既存のイメージを含むデバイスに割り当てられるときに、予期しない動作が発生する場合があります。 たとえば、イメージのないプロファイルを作成します。 このプロファイルは、既にイメージがあるデバイスに割り当てられます。 このシナリオでは、イメージによってデバイスの既定値が変更される可能性があり、または元のイメージがデバイス上に保持される可能性があります。 この動作は、Apple の MDM プラットフォームによって制御および制限されます。

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>設定の適用対象: 自動デバイス登録 (監視)

- **[壁紙の表示場所]** : 画像を表示するデバイス上の場所を選択します。 次のようなオプションがあります。
  - **[未構成]** : カスタムの画像はデバイスに追加されません。 デバイスにはオペレーティング システムの既定値が使用されます。
  - **[ロック画面]** : ロック画面に画像を追加します。
  - **[ホーム画面]** : ホーム画面に画像を追加します。
  - **[ロック画面とホーム画面]** : ロック画面とホーム画面に同じ画像を使用します。
- **[壁紙の画像]** : 使用する既存の .png、.jpg、または .jpeg 画像をアップロードします。 ファイル サイズは 750 KB 未満にする必要があります。 追加した画像を**削除**することもできます。

> [!TIP]
> ロック画面とホーム画面に異なる画像を表示するには、ロック画面の画像を使ってプロファイルを作成します。 ホーム画面の画像を使って別のプロファイルを作成します。 両方のプロファイルを iOS ユーザーまたはデバイス グループに割り当てます。

## <a name="next-steps"></a>次の手順

[プロファイルを割り当て](../device-profile-assign.md)、[その状態を監視](../device-profile-monitor.md)します。

[macOS](macos-device-features-settings.md) デバイスのデバイス機能プロファイルを作成することもできます。
