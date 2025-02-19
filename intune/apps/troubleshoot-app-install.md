---
title: アプリのインストールに関する問題のトラブルシューティング
titleSuffix: Microsoft Intune
description: Microsoft Intune のトラブルシューティング ウィンドウを使用して、アプリのインストールに関する問題をトラブルシューティングします。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4783d24e3fc25583a61f88c2e7375d4eed673186
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74563478"
---
# <a name="troubleshoot-app-installation-issues"></a>アプリのインストールに関する問題のトラブルシューティング

Microsoft Intune の MDM で管理されたデバイスでは、アプリのインストールが失敗することがあります。 アプリのインストールが失敗した場合、失敗の理由を理解したり、問題をトラブルシューティングするのが難しい場合があります。 Microsoft Intune ではアプリのインストール失敗に関する詳細が提供されます。ヘルプ デスクのオペレーターや Intune の管理者は、これを利用してアプリの情報を確認し、ユーザーからのヘルプ要請に対処することができます。 Intune 内のトラブルシューティング ウィンドウではエラーの詳細が提供され、これにはユーザーのデバイス上のマネージド アプリに関する詳細も含まれます。 アプリのエンド ツー エンドのライフサイクルの詳細は、 **[マネージド アプリ]** ウィンドウ内の個々のデバイスの下に表示されます。 アプリの作成日時、変更日時、対象とされた日時、デバイスに配信された日時など、インストールに関する問題を表示できます。 

## <a name="app-troubleshooting-details"></a>アプリのトラブルシューティングの詳細

Intune では、特定のユーザーのデバイスにインストールされているアプリに基づいて、アプリのトラブルシューティングの詳細が提供されます。

1. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。
3. **[トラブルシューティング + サポート]** を選択します。
4. **[ユーザーの選択]** をクリックして、トラブルシューティングするユーザーを選択します。 **[ユーザーの選択]** ウィンドウが表示されます。
5. 名前または電子メール アドレスを入力して、ユーザーを選択します。 ウィンドウの下部にある **[選択]** をクリックします。 ユーザーに対するトラブルシューティング情報が、 **[トラブルシューティング]** ウィンドウに表示されます。 
6. トラブルシューティングするデバイスを、 **[デバイス]** の一覧から選択します。
    ![Intune のトラブルシューティング ウィンドウ。](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. 選択したデバイスのウィンドウから **[マネージド アプリ]** を選択します。 マネージド アプリの一覧が表示されます。
    ![Intune によって管理される特定のデバイスの詳細。](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. 一覧から、 **[インストールのステータス]** が失敗を示しているアプリを選択します。
    ![インストールのエラーの詳細を示す選択したアプリ。](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > 同一のアプリを複数のグループに割り当てることは可能ですが、アプリに対して異なる意図したアクション (インテント) を使用する必要があります。 たとえば、アプリの割り当て中にアプリがユーザーのために除外される場合、アプリの解決されたインテントに **[除外されています]** と表示されます。 詳細については、「[アプリのインテントの競合を解決する方法](apps-deploy.md#how-conflicts-between-app-intents-are-resolved)」をご覧ください。<br><br>
    > 必要なアプリのインストールに失敗した場合、自分で、あるいはヘルプデスクに依頼してデバイスを同期し、アプリのインストールを再試行できます。

アプリのインストールのエラーに関する詳細では、問題点が示されます。 これらの詳細を使用して、問題解決のための最適なアクションを決定することができます。 アプリのインストールに関する問題のトラブルシューティングについて詳細については、[アプリのインストール エラー](troubleshoot-app-install.md#app-installation-errors)に関する記事を参照してください。

> [!Note]  
> **[トラブルシューティング]** ウィンドウには、ブラウザーで [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) に移動してアクセスすることもできます。

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>ユーザーグループの対象アプリのインストールがデバイスに接続していません
アプリのインストールで問題が発生した場合は、次の操作を考慮する必要があります。
- アプリがポータルサイトに表示されない場合は、アプリが**使用可能**なインテントで展開されていることと、ユーザーがアプリでサポートされているデバイスの種類を使用してポータルサイトにアクセスしていることを確認します。
- Windows BYOD デバイスの場合、ユーザーは仕事用アカウントをデバイスに追加する必要があります。
- ユーザーが AAD デバイスの制限を超えているかどうかを確認します。
  1. [ [Azure Active Directory デバイスの設定](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId)] に移動します。
  2. **ユーザーごとのデバイスの最大**数の設定値をメモしておきます。
  3. [ [Azure Active Directory のユーザー](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers)] に移動します。
  4. 影響を受けるユーザーを選択し、 **[デバイス]** をクリックします。
  5. ユーザーが設定された制限を超えている場合は、不要になった古いレコードを削除します。
- IOS DEP デバイスの場合、ユーザーが Intune の デバイスの概要 ウィンドウの **ユーザーによる登録** として表示されていることを確認します。 NA と表示されている場合は、Intune ポータルサイトの構成ポリシーを展開します。 詳細については、[ポータル サイト アプリの構成](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices)に関する記事をご覧ください。

## <a name="win32-app-installation-troubleshooting"></a>Win32 アプリのインストールのトラブルシューティング

Intune 管理拡張機能を使用して展開された Win32 アプリを選択します。 Win32 アプリのインストールに失敗した場合は、 **[ログの収集]** オプションを選択できます。 

> [!IMPORTANT]
> Win32 アプリがデバイスに正常にインストールされると、 **[ログの収集]** オプションは有効になりません。<p>Win32 アプリのログ情報を収集する前に、Intune 管理拡張機能を Windows クライアントにインストールする必要があります。 PowerShell スクリプトまたは Win32 アプリをユーザーまたはデバイスのセキュリティ グループに展開すると、Intune 管理拡張機能がインストールされます。 詳細については、[Intune 管理拡張機能の前提条件](intune-management-extension.md#prerequisites)に関する記事を参照してください。

### <a name="collect-log-file"></a>ログ ファイルを収集する

Win32 アプリのインストール ログを収集するには、まずセクション「[アプリのトラブルシューティングの詳細情報](troubleshoot-app-install.md#app-troubleshooting-details)」に記載されている手順を実行します。 次に、以下の手順に進みます。

1. **[インストールの詳細]** ウィンドウの **[ログの収集]** オプションをクリックします。

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. ファイル パスにログ ファイル名を指定してログ ファイル収集プロセスを開始し、 **[OK]** をクリックします。

    > [!NOTE]
    > ログ収集にかかる時間は 2 時間未満です。 サポートされるファイルの種類: *.log、.txt、.dmp、.cab、.zip、.xml、.evtx、.evtl*。 最大 25 個のファイル パスが許可されています。

3. ログ ファイルが収集されたら、**ログ** リンクを選択してログ ファイルをダウンロードできます。

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > アプリのログ収集の成功を示す通知が表示されます。

#### <a name="win32-log-collection-requirements"></a>Win32 ログ収集の要件

ログ ファイルを収集するには、従う必要がある特定の要件があります。

- 完全なログ ファイルのパスを指定する必要があります。 
- 以下のようなログ収集用の環境変数を指定できます。<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- 次のような正確なファイル拡張子のみが許可されています。<br>
  *.log, .txt, .dmp, .cab, .zip, .xml*
- アップロードできる最大ログ ファイルは、60 MB または 25 個ファイルのうち、どちらか早い方です。 
- Win32 アプリのインストール ログ収集は、必須、利用可能、およびアンインストールのアプリ割り当ての意図を満たすアプリに対して有効になります。
- 保存されたログは、ログに含まれる個人を特定できる情報を保護するために暗号化されます。
- Win32 アプリの失敗に関するサポート チケットを開くときは、上記の手順を使用して関連するエラー ログを添付してください。

## <a name="app-installation-errors"></a>アプリのインストール エラー

次のエラー メッセージと説明により、Android と iOS の両方のインストール エラーに関する詳細が表示されます。 

### <a name="android-errors"></a>Android のエラー

このセクションでは、デバイス管理者 (DA) と Samsung Knox 登録の両方について説明します。 詳細については、「 [android デバイス管理者の登録](../enrollment/android-enroll-device-administrator.md)」および「 [Samsung の Knox モバイル登録を使用して Android デバイスを自動的に登録する](../enrollment/android-samsung-knox-mobile-enroll.md)」を参照してください。 

| エラー メッセージ/コード | 説明 |
|---------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| アプリをインストールできませんでした。 (0xC7D14FB5) | このエラー メッセージは、Android アプリのインストール エラーの根本原因を Intune が判断できないときに表示されます。 エラー時、Android からは情報が提供されていません。 APK のダウンロードに成功したが、アプリのインストールに失敗したときに、このエラーが返されます。 このエラーは、デバイスにインストールできない不適切な APK ファイルが原因で発生する場合がよくあります。 考えられる原因としては、セキュリティ上の問題のために Google Play Protect によってそのアプリのインストールがブロックされている場合があります。 このエラーの別の原因としては、デバイスでそのアプリがサポートされていない場合が考えられます。 たとえば、アプリで必要とされる API バージョンが 21 以上で、デバイスの API バージョンが現在 19 だった場合です。 Intune では、DA デバイスと KNOX デバイスの両方に対してこのエラーが返されます。ユーザーが通知をクリックすると再試行できる場合もありますが、問題が APK にあれば、続けて失敗することはありません。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 |
| インストール (APK) ファイルがダウンロードされたものの、インストールする前に削除されたため、アプリのインストールは取り消されました。 (0xC7D14FBA) | APK のダウンロードに成功しましたが、ユーザーがアプリをインストールする前に、デバイスからファイルが削除されました。 これは、ダウンロードとインストールの間に大きな時間の隔たりがあった場合に発生する可能性があります。 たとえば、ユーザーが最初のインストールを取り消し、待機し、通知をクリックして再試行したときです。 このエラー メッセージは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、通知なしで実行できます。 ユーザーが取り消しではなく受諾できるように、再試行のための通知が提示されます。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 |
| アプリのインストールは、インストール中にプロセスが再開されたため、取り消されました。 (0xC7D14FBB) | APK インストール プロセス中にデバイスが再起動され、その結果としてインストールが取り消されました。 このエラー メッセージは、DA デバイスと KNOX デバイスの両方に対して返されます。 ユーザーは Intune に表示される通知をクリックし、再試行できます。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 |
| インストールが正常に完了したにもかかわらず、アプリケーションが検出されませんでした。 (0x87D1041C) | ユーザーは明示的にアプリをアンインストールしました。 このエラーはクライアントからは返されません。 このエラーは、ある時点でアプリがインストールされ、その後ユーザーによってアンインストールされた場合に発生します。 このエラーは必須のアプリケーションに対してのみ発生します。 ユーザーは必須ではないアプリをアンインストールできます。 このエラーは DA でのみ発生します。 KNOX の場合、マネージド アプリのアンインストールがブロックされます。 ユーザーがインストールするために、次の同期でデバイスに通知が再掲示されます。 ユーザーは通知を無視できます。 このエラーの報告は、ユーザーがアプリをインストールするまで続きます。 |
| 不明なエラーのため、ダウンロードできませんでした。 (0xC7D14FB2) | このエラーは、ダウンロードが失敗したときに発生します。 このエラーは通常、Wi-Fi の問題か、接続が遅いために発生します。 このエラーは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、ユーザーがインストールを求められることはありません。これは通知なしで実行できます。 ユーザーは Intune に表示される通知をクリックし、再試行できます。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 |
| 不明なエラーのため、ダウンロードできませんでした。 デバイスが次回同期されたとき、ポリシーが再試行されます。 (0xC7D15078) | このエラーは、ダウンロードが失敗したときに発生します。 このエラーは通常、Wi-Fi の問題か、接続が遅いために発生します。 このエラーは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、ユーザーがインストールを求められることはありません。これは通知なしで実行できます。 |
| エンド ユーザーがアプリのインストールを取り消しました。 (0xC7D14FB1) | ユーザーは明示的にアプリをアンインストールしました。 このエラーは、Android OS のインストール アクティビティをユーザーが取り消したときに返されます。 OS インストール プロンプトが提示されたときにユーザーが取り消しボタンを押したか、クリックしてプロンプトを終了しました。 このエラーは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、ユーザーがインストールを求められることはありません。これは通知なしで実行できます。 ユーザーは Intune に表示される通知をクリックし、再試行できます。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 インストールをキャンセルしないようにユーザーに依頼します。 |
| ファイルのダウンロード プロセスが予期せず停止しました。 (0xC7D15015) | ダウンロード プロセスが完了する前に OS により停止されました。 このエラーは、デバイスの電池残量が少なくなっているか、ダウンロードに時間がかかりすぎるときに発生します。 このエラーは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、ユーザーがインストールを求められることはありません。これは通知なしで実行できます。 ユーザーは Intune に表示される通知をクリックし、再試行できます。 アプリが利用可能なアプリであれば、通知は無視できます。 ただし、アプリが必須であれば、無視できません。 デバイスに信頼性の高いネットワーク接続があることを確認します。  |
| ファイルのダウンロード サービスが予期せず停止しました。 デバイスが次回同期されたとき、ポリシーが再試行されます。 (0xC7D1507C) | OS によって、完了する前にダウンロード プロセスが終了されました。 このエラーは、デバイスの電池残量が少なくなっているか、ダウンロードに時間がかかりすぎるときに発生します。 このエラーは、DA シナリオの場合にのみ返されます。 KNOX のシナリオでは、ユーザーがインストールを求められることはありません。これは通知なしで実行できます。 デバイスを手動で同期するか、24時間待機して、状態を確認してください。 |
| アプリをアンインストールできませんでした。 (0xc7d14fb8) | このエラーは、一般的なアンインストールエラーです。 OS は、アプリのアンインストールに失敗した理由を指定しませんでした。 一部の管理アプリは単にアンインストールできません。 アプリを手動でアンインストールできることを確認し、アンインストールが失敗した場合はポータルサイトログを収集します。 |
| アップグレードに使用されたアプリインストール APK ファイルが、デバイス上の現在のアプリの署名と一致しません。 (0xc7d14fb7) | Android OS では、アップグレードバージョンの署名証明書が、既存のバージョンの署名に使用される証明書とまったく同じである必要があるという制限があります。 開発者が同じ証明書を使用して新しいバージョンに署名できない場合は、既存のアプリをアップグレードするのではなく、既存のアプリをアンインストールし、新しいアプリを再デプロイする必要があります。 |
| エンド ユーザーがアプリのインストールを取り消しました。 (0xc7d14fb9) | Intune によって展開されたアプリに同意し、メッセージが表示されたらアプリをインストールするようにユーザーを教育します。 |
| アプリのアンインストールは、インストール中にプロセスが再開されたため、取り消されました。 (0xc7d14fbc) | アプリのインストールプロセスが OS によって終了されたか、デバイスが再起動されました。 このエラーが再び発生する場合は、インストールを再試行してポータルサイトログを収集します。 |
| アプリのインストール APK ファイルは署名されていないため、インストールできません。 (0xc7d14fb6) | 既定では、Android OS にはアプリに署名する必要があります。 デプロイする前にアプリが署名されていることを確認します。 |

### <a name="ios-errors"></a>iOS エラー

| エラー メッセージ/コード | 説明/トラブルシューティングのヒント |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM エージェントから、インストール コマンドが失敗したことが返されました。 |
| (0x87D1313C) | 更新されたダウンロード サービス URL をデバイスに送信している間にネットワーク接続が失われました。 具体的には、指定したホスト名を持つサーバーが見つかりませんでした。 |
| iOS デバイスは現在ビジーです。 (0x87D11388) | iOS デバイスがビジーだったため、エラーになりました。 デバイスはロックされています。 ユーザーは、アプリをインストールするためにデバイスのロックを解除する必要があります。 |
| アプリのインストールに失敗しました。 (0x87D13B64) | アプリのインストール エラーが発生しました。 このエラーをトラブルシューティングするには、iOS コンソール ログが必要です。 |
| アプリは管理されているものの、期限が切れたか、ユーザーによって削除されました。 (0x87D13B66) | ユーザーによってアプリが明示的にアンインストールされたか、アプリの有効期限が切れているがダウンロードに失敗したか、またはアプリの検出がデバイスからの応答と一致しません。 また、このエラーは iOS 9.2.2 プラットフォームのバグにより発生することがあります。 |
| アプリのインストールがスケジュールされているものの、トランザクションを完了するには引き換えコードが必要です。 (0x87D13B60) | このエラーは通常、有料アプリである iOS ストア アプリで発生します。 |
| インストールが正常に完了したにもかかわらず、アプリケーションが検出されませんでした。 (0x87D1041C) | アプリ検出プロセスの結果がデバイスからの応答に一致しませんでした。 |
| ユーザーがアプリのインストールの提案を拒否しました。 (0x87D13B62) | 最初のアプリ インストール中、ユーザーがキャンセルをクリックしました。 次にインストール要求を受け入れるようにユーザーに依頼します。 |
| ユーザーがアプリの更新の提案を拒否しました。 (0x87D13B63) | 更新プロセス中、エンド ユーザーがキャンセルをクリックしました。 必要に応じて展開するか、アップグレードのプロンプトを受け入れるようにユーザーを教育します。 |
| 不明なエラー (0x87D103E8) | 不明なアプリのインストール エラーが発生しました。 他のエラーが確認できなければ、結果的にこのエラーとなります。 |
| 共有 iPad にのみ VPP アプリをインストールできます (-2016330861)。 | 共有 iPad にインストールするには、Apple Volume Purchase Program を使用してアプリを入手する必要があります。 |
| App Store が無効な場合はアプリをインストールできません (-2016330860)。 | ユーザーがアプリをインストールするには、App Store を有効にする必要があります。 |
| アプリの VPP ライセンスが見つかりません (-2016330859)。 | アプリのライセンスを取り消して再割り当てを行ってみてください。 |
| MDM プロバイダーでシステム アプリをインストールできません (-2016330858)。 | iOS オペレーティング システムによって事前にインストールされているアプリのインストールは、サポートされるシナリオではありません。 |
| デバイスが紛失モードのときはアプリをインストールできません (-2016330857)。 | 紛失モードでは、デバイスの使用はすべてブロックされます。 アプリをインストールするには、紛失モードを無効にします。 |
| デバイスがキオスク モードのときはアプリをインストールできません (-2016330856)。 | アプリをインストールするには、このデバイスをキオスク モード構成ポリシーの除外グループに追加してみてください。 |
| このデバイスには 32 ビット アプリをインストールできません (-2016330852)。 | このデバイスは 32 ビット アプリのインストールをサポートしていません。 64 ビット バージョンのアプリを展開してみてください。 |
| ユーザーは App Store にサインインする必要があります (-2016330855)。 | アプリをインストールする前に、ユーザーは App Store にサインインする必要があります。 |
| 不明な問題です。 もう一度やり直してください (-2016330854)。 | 不明な理由でアプリのインストールに失敗しました。 後でもう一度やり直してください。 |
| アプリのインストールに失敗しました。 次にデバイスが同期されるときに Intune で再試行されます (-2016330853)。 | アプリのインストールでデバイス エラーが発生しました。 アプリをもう一度インストールするには、デバイスを同期します。 |
| Apple エラー ' VPP ライセンスが残っていません ' (0x87d13b7e) により、ライセンスの割り当てに失敗しました | この動作は仕様です。 これを解決するには、追加の VPP ライセンスを購入するか、対象外となったユーザーからライセンスを回収します。 |
| アプリのインストールエラー 12024: 原因不明。 (0x87d13b6e) | Apple は、インストールが失敗した理由を特定するための十分な情報を提供していません。 報告するものがありません。 |
| 必要なアプリ構成ポリシーが存在しません。ポリシーが同じグループを対象にしていることを確認してください。 (0x87d13b7f) | アプリにはアプリの構成が必要ですが、アプリの構成が対象になっていません。 管理者は、アプリが対象としているグループに、そのグループを対象とする必要なアプリ構成があることを確認する必要があります。 |
| デバイス VPP ライセンスは、iOS 9.0 以降のデバイスにのみ適用されます。 (0x87d13b69) | 影響を受けた iOS デバイスを iOS 9.0 以降にアップグレードします。 |
| アプリケーションはデバイスにインストールされていますが、管理されていません。 (0x87d13b8f) | このエラーは、LOB アプリにのみ発生します。 アプリが Intune の外部にインストールされました。 このエラーに対処するには、デバイスからアプリをアンインストールします。 デバイスの同期が次に行われるときに、デバイスは Intune からアプリをインストールする必要があります。 |
| ユーザーがアプリ管理を拒否しました (0x87d13b68) | アプリ管理を受け入れるようにユーザーに依頼します。 |
| 不明なエラー。 (0x87d1279 d) | このエラーは、iOS ストアアプリで発生しますが、エラーシナリオは不明です。 |
| 最新バージョンのアプリを以前のバージョンから更新できませんでした。 (0x87D13B9D) | このエラーメッセージは、アプリがインストールおよび管理されているものの、デバイスのバージョンが正しくない場合に表示されます。 この状況には、デバイスがアプリを更新するコマンドを受信したが、新しいバージョンがまだインストールされておらず、報告されていない場合などがあります。 このエラーは、アップグレードの展開後にデバイスが最初にチェックインしたときに報告され、新しいバージョンがインストールされたことがデバイスによって報告されるか、別のエラーが原因で失敗します。  |


### <a name="other-installation-errors"></a>その他のインストール エラー

|  エラー メッセージ/コード  |  説明  |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  0x80073CFF、0x80CF201C (クライアント エラー)  |  このアプリケーションをインストールするには、サイドローディング対応のシステムが必要です。 必ず、信頼できる署名を使用してアプリ パッケージに署名して、**AllowAllTrustedApps** ポリシーを有効にしたドメインに参加するデバイス、または **AllowAllTrustedApps** ポリシーを有効にした Windows サイドローディング ライセンスを持つデバイスにアプリ パッケージをインストールします。 詳細については、「[Troubleshooting packaging, deployment, and query of Windows Store apps (Windows ストア アプリのパッケージ化、展開、クエリのトラブルシューティング)](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting)」を参照してください。   |
|  0x80073CF0  |  パッケージを開くことができませんでした。 次の原因が考えられます。<ul><li> パッケージが署名されていません。</li><li> 発行元の名前が、署名している証明書の件名と一致しません。</li></ul> 詳細については、**AppxPackagingOM** イベント ログを確認してください。 詳細については、「[Troubleshooting packaging, deployment, and query of Windows Store apps (Windows ストア アプリのパッケージ化、展開、クエリのトラブルシューティング)](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting)」を参照してください。  |
|  0x80073CF3  |  パッケージは更新、依存関係、または競合の検証に失敗しました。 次の原因が考えられます。<ul><li> 受信パッケージがインストール済みのパッケージと競合しています。</li><li> 指定したパッケージの依存関係が見つかりません。</li><li> パッケージは正しいプロセッサ アーキテクチャをサポートしていません。</li></ul> 詳細については、**AppXDeployment-Server** イベント ログを確認してください。 詳細については、「[Troubleshooting packaging, deployment, and query of Windows Store apps (Windows ストア アプリのパッケージ化、展開、クエリのトラブルシューティング)](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting)」を参照してください。  |
|  0x80073CFB  |  指定したパッケージは既にインストールされており、パッケージの再インストールがブロックされています。 既にインストールされているパッケージと同じではないパッケージをインストールしようとすると、このエラーが発生する可能性があります。 デジタル署名がパッケージにも含まれることを確認します。 パッケージを再ビルドまたは再署名すると、パッケージは以前にインストールしたパッケージとビット単位で同じではなくなります。 このエラーを修正するには、次のように 2 つの選択肢が考えられます。<ul><li> アプリケーションのバージョン番号を増やして、パッケージの再ビルドと再署名を行います。</li><li> システムのすべてのユーザーの古いパッケージを削除してから、新しいパッケージをインストールします。</li></ul> 詳細については、「[Troubleshooting packaging, deployment, and query of Windows Store apps (Windows ストア アプリのパッケージ化、展開、クエリのトラブルシューティング)](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting)」を参照してください。  |
|  0x87D1041C  |  アプリケーションがインストールされましたが、検出されません。 アプリは Intune によって正常に展開され、その後、アンインストールされました。 アプリがアンインストールされる理由を次に示します。<ul><li> エンドユーザーが、アプリをアンインストールする。</li><li> パッケージ内の ID 情報が、不適切なアプリに対してデバイスが報告している内容と一致しない。</li><li>自己更新する MSI の場合、Intune 外部で更新された後に、製品のバージョンがアプリの情報と一致しない。</li></ul> ユーザーは、ポータル サイトからアプリを再インストールするように指示されます。 デバイスが次回チェックインするときに、必要なアプリが自動的に再インストールされることに注意してください。  |
|  0x8000FFFF  |  インストール中に予期しないエラーが発生しました。 詳細については、インストールログを確認してください。  |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Microsoft ストア アプリのトラブルシューティング

トピック「[Troubleshooting packaging, deployment, and query of Microsoft Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx)」 (Microsoft ストア アプリのパッケージ化、展開、およびクエリのトラブルシューティング) に記載されている情報は、Microsoft ストアからアプリをインストールする際に発生する可能性がある一般的な問題のトラブルシューティングで役に立ちます (Intune を使用する場合、または他の手段を使用する場合に関係なく)。

## <a name="app-troubleshooting-resources"></a>アプリのトラブルシューティングに関するリソース
- [Office Pro Plus の展開の一部として Visio と Project を展開する](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Windows 10 1903 に Intune を使用して展開された MSfB アプリを確認するためのアクションを実行します](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Microsoft Intune での MSI アプリの展開のトラブルシューティング](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Intune クラシック Windows PC エージェントへのソフトウェアの配布に関するベストプラクティス](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>次の手順

- Intune のトラブルシューティングに関する追加情報については、「[トラブルシューティング ポータルを使用して社内のユーザーをサポートする](../fundamentals/help-desk-operators.md)」をご覧ください。 
- Microsoft Intune の既知の問題について学習します。 詳細については、「 [Intune のお客様の成功](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)」を参照してください。
- さらに支援が必要ですか? 「[Microsoft Intune のサポートを受ける方法](../fundamentals/get-support.md)」を参照してください。
