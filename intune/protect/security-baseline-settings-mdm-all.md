---
title: Windows 10 MDM 用の Intune セキュリティ ベースラインの設定
titleSuffix: Microsoft Intune
description: Microsoft Intune で管理できるさまざまなバージョンの Windows MDM セキュリティベースラインの既定値と使用可能な設定を確認します。
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
zone_pivot_groups: windows-mdm-versions
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6b2cb1b277f78ed81dea8c2d82eff6860182ea5d
ms.sourcegitcommit: 7cc45ef52dda08479bc6bdff7d11d2f6c0e7b93b
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "74899265"
---
# <a name="windows-mdm-security-baseline-settings-for-intune"></a>Intune 用の Windows MDM セキュリティ ベースラインの設定

Windows 10 以降を実行しているデバイスに対して Microsoft Intune がサポートする MDM セキュリティベースライン設定を表示します。 このベースラインの設定の既定値は、適用可能なデバイスに推奨される構成を表します。 1つのベースラインの既定値が、他のセキュリティ基準またはこの基準の他のバージョンの既定値と一致しない場合があります。

- セキュリティベースラインを Intune で使用する方法と、セキュリティベースラインプロファイルのベースラインバージョンをアップグレードする方法については、「[セキュリティベースラインの使用](../security-baselines.md)」を参照してください。
- 最新の基準バージョンは、 **2019 年5月の MDM セキュリティベースライン**です。

表示するベースラインのバージョンを選択してください。
<!-- Cookies might be required to enable some browsers to display the zone options -->

::: zone pivot="mdm-may-2019"
**2019 年 5 月の MDM セキュリティ ベースライン**:  
> [!NOTE]
> 2019年6月に、5月*2019 テンプレートの MDM セキュリティベースライン*が一般公開 (プレビューではない) としてリリースされました。 このバージョンのセキュリティベースラインは、 *2018 年10月の MDM セキュリティ基準*である前の基準を置き換えます。  2019年5月の使用が可能になる前に作成されたプロファイルは、5月2019バージョンの設定と値を反映して更新されません。  プレビューテンプレートに基づいて新しいプロファイルを作成することはできませんが、プレビューテンプレートに基づいて以前に作成したプロファイルを編集し、引き続き使用することができます。

以前のバージョンのベースラインのこのバージョンで変更された点については、「[新しいテンプレートの変更点](#whats-changed-in-the-new-template)」を参照してください。

::: zone-end
::: zone pivot="mdm-preview"
**プレビュー - 2018 年 10 月の MDM セキュリティ ベースライン**:  
> [!NOTE]
> これは、2018年10月にリリースされた MDM セキュリティベースラインのプレビューバージョンです。 このプレビュー基準は、2019年6月にリリースされました。このテンプレートは一般公開されています (プレビュー *2019*版ではありません)。 2019年 5*月の Mdm セキュリティ*ベースラインが使用可能になる前に作成されたプロファイルは、年 5 2019 月バージョンの Mdm セキュリティ基準に含まれる設定と値を反映して更新されません。 プレビューテンプレートに基づいて新しいプロファイルを作成することはできませんが、プレビューテンプレートに基づいて以前に作成したプロファイルを編集し、引き続き使用することができます。

::: zone-end
::: zone pivot="mdm-may-2019,mdm-preview"

## <a name="above-lock"></a>Above Lock (上でロック)

詳細については、Windows の「[Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock)」(ポリシー CSP - AboveLock) を参照してください。  

- **[Block display of toast notifications]\(トースト通知の表示をブロックする\)** :  
  このポリシー設定では、アプリ通知をロック画面に表示しないように設定します。 このポリシー設定を有効にした場合、ロック画面にどのアプリ通知も表示されません。 このポリシー設定を無効にした場合、または構成しなかった場合、ロック画面に通知を表示するアプリをユーザーが選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067101)

  **既定値**: はい

::: zone-end
::: zone pivot="mdm-may-2019"

- **[ロック画面から音声でアプリをアクティブ化する]** :  
  **既定値**: 無効

::: zone-end
::: zone pivot="mdm-may-2019,mdm-preview"

## <a name="app-runtime"></a>[アプリ実行時]

詳細については、Windows の「[Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime)」(ポリシー CSP - AppRuntime) を参照してください。

- **[Microsoft accounts optional for Windows Store apps]\(Windows ストア アプリで Microsoft アカウントの省略を許可する\)** :  
  このポリシー設定によって、サインインにアカウントを必要とする Windows ストア アプリで Microsoft アカウントを省略可能にするかどうかを制御できます。 このポリシーが影響するのは、このポリシーをサポートする Windows ストア アプリだけです。 このポリシー設定を有効にした場合、通常はサインインに Microsoft アカウントを必要とする Windows ストア アプリで、ユーザーは、代わりにエンタープライズ アカウントを使用してサインインできます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは Microsoft アカウントを使用してサインインする必要があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067104)
  
  **既定値**: 有効

## <a name="application-management"></a>アプリケーション管理

詳細については、Windows の「[Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement)」(ポリシー CSP - ApplicationManagement) を参照してください。

::: zone-end
::: zone pivot="mdm-may-2019"

- **ユーザーによるインストールの制御をブロック**する:  
  このポリシー設定を使用すると、通常はシステム管理者のみが使用できるインストールのオプションをユーザーが変更できるようになります。 このポリシー設定を有効にした場合、Windows インストーラーの一部のセキュリティ機能がバイパスされます。 このポリシーを使用すると、通常はセキュリティ違反のため強制的に中止されるインストールを完了させることができます。 このポリシー設定を無効にした場合、または構成しなかった場合、Windows インストーラーでは、通常システム管理者のみに許可されているインストールのオプション (たとえば、ファイルのインストール先ディレクトリの指定) をユーザーが変更することはできません。 保護されているオプションをユーザーが変更しようとすると、インストールは中止されエラー メッセージが表示されます。 このセキュリティ機能は、インストール プログラムが特権付きセキュリティ コンテキストで実行されており、ユーザーがアクセス許可を持っていないディレクトリにプログラムがアクセスできるときに機能します。 このポリシー設定は、規制を緩和するためのものです。 ソフトウェアのインストールを妨げるようなインストールのエラーを回避するためにも使用できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067060)

  **既定値**: はい

- **管理者特権での MSI アプリのインストールをブロック**する:  
  このポリシー設定を使用すると、Windows インストーラーを使ってシステムにプログラムをインストールするときに管理者特権のアクセス許可が使用されます。

  - "*このポリシー設定を有効にすると*"、特権がすべてのプログラムに適用されます。 通常、これらの特権はユーザー (デスクトップ上で提供されている) に割り当てられたプログラム、コンピューター (自動的にインストールされている) に割り当てられたプログラム、またはコントロール パネルの [プログラムの追加と削除] で利用できるプログラム用に予約されています。 このプロファイル設定を使うと、ユーザーはアクセス許可が与えられていないため表示も変更もできないディレクトリ (厳しく制限されているコンピューター上のディレクトリを含む) へのアクセスを必要とするプログラムをインストールできます。

  - "*このポリシー設定を無効にした場合、または構成しなかった場合*"、システム管理者から配布または提供されていないプログラムのインストール時に、システムによってユーザーの現在のアクセス許可が適用されます。 注: このポリシー設定は [コンピューターの構成] フォルダーおよび [ユーザーの構成] フォルダーにあります。 このポリシー設定を有効にするには、両方のフォルダーでこのポリシー設定を有効にする必要があります。 警告: 上級ユーザーは、このポリシー設定で付与されるアクセス許可を使って特権を変更し、制限付きのファイルおよびフォルダーに継続してアクセスできます。 このポリシー設定の [ユーザーの構成] バージョンのセキュリティ保護は必ずしも安全ではありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067134)

  **既定値**: はい

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Block game DVR (desktop only)]\(ゲーム DVR をブロックする (デスクトップのみ)\)**  
  ゲームの録画とブロードキャストを許可するかどうか設定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067056)

  **既定値**: はい

## <a name="auto-play"></a>Auto Play (自動再生)

詳細については、Windows の「[Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay)」(ポリシー CSP - Autoplay) を参照してください。

- **[Auto play default auto run behavior]\(自動再生の既定の自動実行の動作\)**  
  この設定は、自動実行コマンドの既定の動作に影響します。 自動実行コマンドは、autorun.inf ファイルに保存されており、インストール プログラムやその他のルーチンを開始できます。 これを*有効*にすると、管理者は Windows Vista 以降を実行するデバイスの自動実行の既定の動作を変更することができます。 次の動作に設定できます: a) 自動実行コマンドを完全に無効にする、b) 自動実行コマンドを自動的に実行する Windows Vista 以前の動作に戻す。 *無効*または*未構成*にすると、Windows Vista 以降を実行するコンピューターで自動実行コマンドを実行するかユーザーはたずねられます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067133)

  **既定値**: 実行しない

- **[Auto play mode]\(自動再生のモード\)**  
  このポリシー設定では、自動再生機能をオフにできます。 自動再生とは、ドライブにメディアを挿入すると同時にドライブからの読み込みを開始する機能です。 この機能によって、プログラムのセットアップ ファイルやオーディオ メディアの音楽などがすぐに開始されます。 Windows XP SP2 以前では、自動再生は、フロッピー ディスク ドライブなどのリムーバブル ドライブ (CD-ROM ドライブは除く) およびネットワーク ドライブ上では既定で無効になっています。 Windows XP SP2 以降では、自動再生は Zip ドライブや一部の USB 大容量記憶装置デバイスなどのリムーバブル ドライブでも有効になっています。 このポリシー設定を有効にした場合、CD-ROM およびリムーバブル メディア ドライブの自動再生を無効にするか、すべてのドライブの自動再生を無効にすることができます。 このポリシー設定によって、これ以外の種類のドライブでの自動再生を無効にすることができます。 この設定を使用して、既定で無効になっているドライブ上の自動再生を有効にすることはできません。 このポリシー設定を無効にした場合、または構成しなかった場合、自動再生が有効になります。 注: このポリシー設定は [コンピューターの構成] フォルダーおよび [ユーザーの構成] フォルダーにあります。 ポリシー設定が競合する場合、[コンピューターの構成] にあるポリシー設定が [ユーザーの構成] にあるポリシー設定より優先されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066793)

  **既定値**: 無効

- **[Block auto play for non-volume devices]\(ボリューム以外のデバイスの自動再生をブロックする\)** :  
  このポリシー設定では、カメラや電話などの MTP デバイスの自動再生を許可しません。 このポリシー設定を有効にした場合、カメラや電話などの MTP デバイスの自動再生が許可されません。 このポリシー設定を無効にした場合、または構成しなかった場合、ボリューム以外のデバイスに対する自動再生が有効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067106)

  **既定値**: 有効

## <a name="bitlocker"></a>BitLocker

詳細については、Windows ドキュメントの「[ポリシー CSP - BitLocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker)」を参照してください。

- **[BitLocker removable drive policy]/(Bitlocker のリムーバブル ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067140)

  BitLocker リムーバブル ドライブ ポリシーの場合は、次の設定を構成します。

  - **[Require encryption for write access]\(書き込みアクセス用に暗号化が必要\)** :  
    **既定値**: はい

::: zone-end
::: zone pivot="mdm-preview"

- **[BitLocker removable drive policy]/(Bitlocker のリムーバブル ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067140)

  BitLocker リムーバブル ドライブ ポリシーの場合は、次の設定を構成します。

  - **[Require encryption for write access]\(書き込みアクセス用に暗号化が必要\)** :  
    **既定値**: はい  

  - **[暗号化方法]** :  
    **既定値**: AES 256 ビット CBC  

- **[BitLocker fixed drive policy]\(BitLocker の固定ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。

  BitLocker 固定ドライブ ポリシーの場合は、次の設定を構成します。

  - **[暗号化方法]** :  
    **既定値**: AES 256 ビット XTS  

- **[BitLocker system drive policy]\(BitLocker のシステム ドライブのポリシー\)**  
  このポリシー設定は、暗号化方法および暗号化強度を制御するために使用します。 このポリシーの値は、BitLocker が暗号化に使用する暗号化強度を決定します。 企業では、セキュリティを強化するために、暗号化のレベルを制御したい場合があります (AES-256 は AES-128 よりも強力です)。 この設定を有効にした場合は、固定データ ドライブやオペレーティング システム ドライブ、リムーバブル データ ドライブのそれぞれに、暗号化アルゴリズムとキーの暗号化強度を構成できます。 固定ドライブやオペレーティング システム ドライブには、XTS-AES アルゴリズムを使用することをお勧めします。 リムーバブル ドライブには、Windows 10 バージョン 1511 以降を実行していないその他のデバイスでドライブを使用する場合は、AES-CBC 128 ビットまたは AES-CBC 256 ビットを使用する必要があります。 ドライブが既に暗号化されているか、暗号化が進行中の場合は、暗号化の種類を変更しても影響はありません。 このような場合、このポリシー設定は無視されます。

  BitLocker システム ドライブ ポリシーの場合は、次の設定を構成します。

  - **[暗号化方法]** :  
    **既定値**: AES 256 ビット XTS

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="browser"></a>ブラウザー

詳細については、Windows の「[Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser)」(ポリシー CSP - Browser) を参照してください。

- **[Require SmartScreen for Microsoft Edge]\(Microsoft Edge で SmartScreen が必要\)**  
  Microsoft Edge では、(オンになった) Microsoft Defender SmartScreen を使用して、フィッシング詐欺にあう可能性や悪意のあるソフトウェアから既定でユーザーを保護しています。 また、既定では、ユーザーは Microsoft Defender SmartScreen を無効 (オフ) にできません。 このポリシーを有効にすると、Microsoft Defender SmartScreen がオフになり、ユーザーがそれをオンにできないようになります。 ユーザーが Microsoft Defender SmartScreen のオンとオフを選択できるようにする場合は、このポリシーを構成しないでください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067029)

  **既定値**: はい

- **[Block malicious site access]\(悪意のあるサイトへのアクセスをブロックする\)** :  
  既定では、Microsoft Edge では、悪意のある可能性があるサイトに関する Microsoft Defender SmartScreen の警告をユーザーがバイパス (無視) して、サイトに進むことができます。 このポリシーを使用すると、ユーザーが警告をバイパスし、サイトに進めないように Microsoft Edge を構成できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067040)
  
  **既定値**: はい
  
- **[Block unverified file download]\(確認されていないファイルのダウンロードをブロックする\)** :  
  既定では、Microsoft Edge では、悪意のある可能性があるファイルに関する Microsoft Defender SmartScreen の警告をユーザーがバイパス (無視) して、未確認のファイルのダウンロードを続行することができます。 このポリシーを有効にすると、ユーザーはこの警告をバイパスして、確認されていないファイルをダウンロードできなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067023)
  
  **既定値**: はい
  
- **[Block Password Manager]\(Password Manager をブロックする\)** :  
  Microsoft Edge で既定で Password Manager が自動的に使用されることによって、ユーザーはパスワードをローカルで管理できるようになります。 このポリシーを無効にすると、Microsoft Edge で Password Manager が使用されなくなります。 ユーザーに Password Manager を使用してローカルでパスワードを保存および管理させる場合には、このポリシーは設定しないでください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067128)
  
  **既定値**: はい
  
- **[Prevent certificate error overrides]\(証明書エラーのオーバーライドを防ぐ\)**  
  このポリシー設定は、Internet Explorer での閲覧を妨げる Secure Sockets Layer/トランスポート層セキュリティ (SSL/TLS) 証明書エラー (期限切れ、失効、名前の不一致などのエラー) をユーザーが無視できないようにします。 このポリシー設定を有効にすると、ユーザーは閲覧を継続できません。 このポリシー設定を無効にするか、構成しない場合、ユーザーは証明書エラーを無視して閲覧を継続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067126)
  
  **既定値**: はい

## <a name="connectivity"></a>接続

詳細については、Windows の「[Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity)」(ポリシー CSP - Connectivity) を参照してください。

- **[Block Internet download for web publishing and online ordering wizards]\(Web 発行およびオンライン注文ウィザードのインターネット ダウンロードをブロックする\)** :  
  このポリシー設定では、Web 発行ウィザードおよびオンライン注文ウィザード用のプロバイダーの一覧をダウンロードするかどうかを指定します。 これらのウィザードでは、オンライン記憶域や写真印刷などのサービスを提供する会社の一覧から会社を選択できます。 既定では、レジストリで指定されているプロバイダーに加えて Windows Web サイトからダウンロードしたプロバイダーも表示されます。 このポリシー設定を有効にした場合、プロバイダーはダウンロードされず、ローカル レジストリにキャッシュされたサービス プロバイダーのみが表示されます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーが Web 発行ウィザードまたはオンライン注文ウィザードを使用するときに、プロバイダーの一覧がダウンロードされます。 レジストリでサービス プロバイダーを指定する方法などの詳細については、Web 発行ウィザードおよびオンライン注文ウィザードのドキュメントを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067136)
  
  **既定値**: 有効

::: zone-end
::: zone pivot="mdm-may-2019"

- **UNC パスへのセキュリティで保護されたアクセスを構成し**ます。  
  このポリシー設定では、UNC パスへのセキュリティで保護されたアクセスを構成します。 このポリシーを有効にすると、追加のセキュリティ要件を満たした後に、指定した UNC パスへのアクセスのみが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067243)

  **既定**: 追加のセキュリティ要件を満たした後に、指定した UNC パスへのアクセスのみを許可するように Windows を構成します。

  [追加のセキュリティ要件を満たす] を選択した後に、*指定した unc パスへのアクセスのみを許可するように Windows を構成*する場合は、[書き込み済み*unc パス] の一覧*を構成できます。

  - **書き込まれる UNC パスの一覧**:  
    追加のセキュリティフラグとサーバーパスを指定するには、 **[追加]** を選択します。

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Block downloading of print drivers over HTTP]\(プリンター ドライバーの HTTP 経由でのダウンロードをブロックする\)**  
  このポリシー設定では、クライアントが HTTP 経由でプリンター ドライバー パッケージをダウンロードするかどうかを指定します。 HTTP 経由の印刷をセットアップするには、付属していないドライバーを HTTP 経由でダウンロードする必要があります。 注: このポリシー設定が有効になっている場合でも、クライアントはイントラネットやインターネットのプリンターに HTTP 経由で出力できます。 ローカルにインストールされていないドライバーのダウンロードのみを禁止します。 この設定を有効にした場合、プリンター ドライバーは HTTP 経由でダウンロードできません。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは HTTP 経由でプリンター ドライバーをダウンロードできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067141)
  
  **既定値**: 有効

## <a name="credentials-delegation"></a>資格情報の委任

詳細については、Windows の「[Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation)」(ポリシー CSP - CredentialsDelegation) を参照してください。

- **[Remote host delegation of non-exportable credentials]\(リモート ホストでエクスポートできない資格情報を委任する\)**  
  リモート ホストでは、エクスポートできない資格情報を委任できます。 資格情報の委任を使用する場合、エクスポート可能なバージョンの資格情報がデバイスからリモート ホストに提供されます。これにより、ユーザーはリモート ホスト上の攻撃者に資格情報が盗まれるというリスクにさらされます。 このポリシー設定を有効にした場合、ホストは制限付き管理モードまたは Remote Credential Guard モードをサポートします。 このポリシー設定を無効にするか、構成しなかった場合、制限付き管理モードと Remote Credential Guard モードはサポートされません。 ユーザーは常に資格情報をホストに渡す必要があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067103)
  
  **既定値**: 有効

## <a name="credentials-ui"></a>Credentials UI (資格情報 UI)

詳細については、Windows の「[Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui)」(ポリシー CSP - CredentialsUI) を参照してください。

- **[Enumerate administrators]\(管理者の列挙\)** :  
  このポリシー設定により、ユーザーが実行中のアプリケーションの昇格を試みたときに、管理者アカウントが表示されるかどうかを制御します。 既定では、ユーザーが実行中のアプリケーションの昇格を試みたときに、管理者アカウントは表示されません。 このポリシー設定を有効にした場合、PC 上のローカル管理者アカウントがすべて表示され、ユーザーがその 1 つを選択して、正しいパスワードを入力できます。 このポリシー設定を無効にした場合、ユーザーは、昇格時にユーザー名とパスワードを常に入力するよう要求されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067021)

  **既定値**: 無効

## <a name="data-protection"></a>データ保護

詳細については、Windows の「[Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection)」(ポリシー CSP - DataProtection) を参照してください。

- **[Block direct memory access]\(ダイレクト メモリ アクセスをブロックする\)** :  
  このポリシー設定では、ユーザーが Windows にログインするまで、ホット プラグ可能なすべての PCI ダウンストリーム ポートへのダイレクト メモリ アクセス (DMA) をブロックできます。 ユーザーがログインすると、Windows はホット プラグ PCI ポートに接続されている PCI デバイスを列挙します。 ユーザーがコンピューターをロックするたびに、ユーザーが再ログインするまで、子デバイスが接続されていないホット プラグ PCI ポートで DMA がブロックされます。 コンピューターのロックが解除された際に既に列挙されていたデバイスは、取り外されるまで機能を維持します。 このポリシー設定は、BitLocker またはデバイスの暗号化が有効な場合にのみ適用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067031)

  **既定値**: はい

## <a name="device-guard"></a>[Device Guard]

詳細については、Windows の「[Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard)」(ポリシー CSP - DeviceGuard) を参照してください。

- **[Credential Guard]\(資格情報ガード\)** :  
  ユーザーはこの設定で、次回の再起動時に資格情報が保護されるよう、仮想化ベースのセキュリティで Credential Guard をオンにできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067044)

  **既定値**: UEFI ロックで有効化

::: zone-end
::: zone pivot="mdm-may-2019"

- **[仮想化ベースのセキュリティ]** :  
  **既定**: セキュアブートで VBS を有効にする

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Enable virtualization based security]\(仮想化ベースのセキュリティを有効にする\)** :  
  仮想化ベースのセキュリティ (VBS) を次の再起動時にオンにします。 仮想化ベースのセキュリティは、Windows ハイパーバイザーを使ってセキュリティ サービスのサポートを提供します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067066)
  
  **既定値**: はい

- **[Launch system guard]\(System Guard を起動する\)** :  
  **既定値**: 有効

## <a name="device-installation"></a>デバイスのインストール

詳細については、Windows の「[Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation)」(ポリシー CSP - DeviceInstallation) を参照してください。

- **[Hardware device installation by device identifiers]\(デバイス識別子を使用してハードウェア デバイスをインストールする\)** :  
  このポリシー設定では、インストールを禁止するデバイスのプラグ アンド プレイ ハードウェア ID および互換性 ID を指定できます。 このポリシー設定は、デバイスのインストールを許可する他のポリシー設定よりも優先されます。 このポリシー設定を有効にした場合、ハードウェア ID または互換性 ID が作成した一覧に含まれているデバイスはインストールできません。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、このポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。 この設定を無効にした場合、または構成しなかった場合は、他のポリシー設定に従って、デバイスのインストールや更新が許可されるかどうかが決まります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066794)

  **既定値**: Block hardware device installation (ハードウェア デバイスのインストールをブロックする)

  *[ハードウェア デバイスのインストールをブロックする]* を選択すると、次の設定が利用できます。

  - **[Remove matching hardware devices]\(一致するハードウェア デバイスを削除する\)** :  
    この設定は *[Hardware device installation by device identifiers]\(デバイス識別子でハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**: はい

  - **[Hardware device identifiers that are blocked]\(ブロックされているハードウェア デバイス識別子\)** :  
    この設定は *[Hardware device installation by device identifiers]\(デバイス識別子でハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**: はい

- **[Hardware device installation by setup classes]\(セットアップ クラスを使用してハードウェア デバイスをインストールする\)** :  
  このポリシー設定では、インストールを禁止するデバイス ドライバーのデバイス セットアップ クラス GUID (グローバル一意識別子) の一覧を指定できます。 このポリシー設定は、デバイスのインストールを許可する他のポリシー設定よりも優先されます。 このポリシー設定を有効にした場合、デバイス セットアップ クラス GUID が作成した一覧に含まれているデバイス ドライバーはインストールすることも更新することもできません。 リモート デスクトップ サーバーでこのポリシー設定を有効にした場合、このポリシー設定は、リモート デスクトップ クライアントからリモート デスクトップ サーバーへの指定されたデバイスのリダイレクトに影響します。 この設定を無効にした場合、または構成しなかった場合は、他のポリシー設定に従って、デバイスのインストールや更新が許可されるかどうかが決まります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067048)

  **既定値**: Block hardware device installation (ハードウェア デバイスのインストールをブロックする)

  *[ハードウェア デバイスのインストールをブロックする]* を選択すると、次の設定が利用できます。

  - **[Remove matching hardware devices]\(一致するハードウェア デバイスを削除する\)** :  
    この設定は *[Hardware device installation by setup classes]\(設定クラスでハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**: *既定の構成はありません*

  - **[Hardware device identifiers that are blocked]\(ブロックされているハードウェア デバイス識別子\)** :  
    この設定は *[Hardware device installation by setup classes]\(設定クラスでハードウェア デバイスをインストールする\)* が *[Block hardware device installation]\(ハードウェア デバイスのインストールをブロックする\)* に設定されているときのみ使用できます。

    **既定値**: *既定の構成はありません*

## <a name="device-lock"></a>デバイスのロック

詳細については、Windows の「[Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)」(ポリシー CSP - DeviceLock) を参照してください。

- **[Prevent use of camera]\(カメラの使用を禁止する\)** :  
  PC 設定でロック画面カメラのトグル スイッチを無効にし、ロック画面でカメラを呼び出せないようにします。 既定では、ユーザーはロック画面で使用可能なカメラを呼び出すことができます。 この設定を有効にした場合、ユーザーは、PC 設定でロック画面カメラへのアクセスを有効または無効にできず、ロック画面でカメラを呼び出せません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067052)

  **既定値**: 有効

- **[Require password]\(パスワードを必須にする\)** :  
  デバイスのロックを有効にするかどうかを指定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067049)  

  **既定値**: はい
  
  *[パスワードを要求する]* を *[はい]* に設定すると、次の設定が利用できます。

  - **[Password minimum character set count]\(パスワードの最小文字セット数\)** :  
    強力な PIN またはパスワードに必要な複合要素の種類 (大文字、小文字、数字、句読点) の数です。 デスクトップおよびモバイル デバイスには次の動作が PIN によって強制されます。1 - 数字のみ 2 - 数字と小文字が必要 3 - 数字、小文字、および大文字が必要。 デスクトップの Microsoft アカウントおよびドメイン アカウントではサポートされていません。 4 - 数字、小文字、大文字、および特殊文字が必要。 デスクトップではサポートされていません。 既定値は 1 です。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067055)

    **既定値**: 3

  - **[デバイスがワイプされるまでのサインイン失敗回数]** :  
    デバイスがワイプされるまでに許容される認証の失敗回数。 値 0 を指定すると、デバイスのワイプ機能が無効になります。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067030)

    **既定値**: 10  

  - **[パスワードの有効期限 (日数)]** :  
    パスワードの最大有効期間ポリシー設定によって、ユーザーがパスワードの変更を要求されるまでにパスワードを使用できる期間 (日数) が決まります。 1 から 999 までの日数の経過後にパスワードが期限切れになるように設定できます。また、日数を 0 に設定することでパスワードが期限切れにならないように指定することもできます。 [Maximum password age]\(パスワードの最大有効期間\) が 1 から 999 日の間である場合、パスワードの最小有効期間はパスワードの最大有効期間よりも短くする必要があります。 [Maximum password age]\(パスワードの最大有効期間\) が 0 に設定されている場合、[Minimum password]\(パスワードの最小有効期間\) には 0 から 998 日の値を設定できます。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067028)

    **既定値**: 60

  - **[必要なパスワードの種類]** :  
    必要な PIN またはパスワードの種類を決定します。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067027)

    **既定値**: 英数字

  - **[パスワードの最小文字数]** :  
    [Minimum password length]\(最小のパスワードの長さ\) ポリシー設定によって、ユーザー アカウントのパスワードを構成できる最小文字数が決まります。 1 から 14 文字の値を設定できます。また、文字数を 0 に設定して、パスワードが必須ではないことを設定できます。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067024)

    **既定値**: 8

  - **[Block simple passwords]\(単純なパスワードをブロックする\)** :  
    "1111" や "1234" などの PIN またはパスワードを許可するかどうかを指定します。 デスクトップでは、ピクチャ パスワードの使用も制御します。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067127)

    **既定値**: はい  
    *[Yes]\(はい\) に設定すると、単純なパスワードを使用できなくなります。*

  - **[以前のパスワードを再利用できないようにする]** :  
    使用できないパスワードを履歴にいくつ保存するかを指定します。 この値には、ユーザーの現在のパスワードも含まれます。 たとえば、設定が *1* の場合、ユーザーは新しいパスワードを選択すると、現在のパスワードは再利用できません。 設定が *5* の場合は、ユーザーは新しいパスワードを現在のパスワードに設定することも、以前の 4 つのパスワードのいずれかに設定することもできません。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066795)

    **既定値**: 24

- **[Prevent slide show]\(スライド ショーを禁止する\)** :  
  PC 設定でロック画面スライド ショー設定を無効にし、ロック画面でスライド ショーを再生できないようにします。 既定では、ユーザーは、コンピューターのロック後に実行されるスライド ショーを有効にできます。 この設定を有効にした場合、ユーザーは [PC 設定] でスライド ショー設定を修正することができず、スライド ショーは開始できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067105)

  **既定値**: 有効  

  *有効に設定すると、スライド ショーは実行されなくなります。*

- **[Password minimum age in days]\(パスワードの最小有効期間 (日)\)** :  
  パスワードの最小有効期間ポリシー設定によって、ユーザーがパスワードを変更できるようになるまでの使用する必要がある期間 (日数) が決まります。 1 から 998 日の値を設定できます。また、日数を 0 に設定することで、パスワードの変更をすぐに許可することもできます。 パスワードの最大有効期間が 0 (パスワードが期限切れにならないことを示します) に設定されている場合を除き、パスワードの最小有効期間はパスワードの最大有効期限よりも短くする必要があります。 パスワードの最大有効期間が 0 に設定されている場合、パスワードの最小有効期間は 0 から 998 の任意の値に設定できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067022)

  **既定値**: 1

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="dma-guard"></a>DMA ガード

詳細については、Windows ドキュメントの「[Policy CSP - DmaGuard (ポリシー CSP - DmaGuard)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard)」をご覧ください。

- **[Kernel DMA Protection と互換性のない外部デバイスの列挙]** :  
  このポリシーは、外部 DMA 対応デバイスに対して追加のセキュリティを提供することを目的としています。 これにより、DMA の再マッピング/デバイス メモリの分離およびサンドボックス化と互換性のない外部 DMA 対応デバイスの列挙をより詳細に制御できます。 このポリシーが有効になるのは、Kernel DMA Protection がシステム ファームウェアによってサポートされていて、それによって有効にされた場合のみです。 カーネル DMA 保護は、ポリシーまたはエンドユーザーが制御できないプラットフォーム機能です。 これは、製造時にシステムによってサポートされている必要があります。 システムでカーネル DMA 保護がサポートされているかどうかを確認するには、MSINFO32 の [概要] ページにある [カーネル DMA 保護] フィールドをオンにします。  
  [詳細情報](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **既定値**: すべてブロックする

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="event-log-service"></a>イベント ログ サービス

詳細については、Windows の「[Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice)」(ポリシー CSP - EventLogService) を参照してください。

- **[Security log maximum file size in KB]\(セキュリティ ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定は、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にした場合、ログ ファイルの最大サイズを KB 単位で 1 MB (1024 KB) から 2 TB (2147483647 KB) までの範囲内に設定できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 ローカル管理者は [ログのプロパティ] ダイアログを使用してこの値を変更できます。既定値は 20 MB に設定されています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067042)

   **既定値**: 196608

- **[System log maximum file size in KB]\(システム ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定は、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にした場合、ログ ファイルの最大サイズを KB 単位で 1 MB (1024 KB) から 2 TB (2147483647 KB) までの範囲内に設定できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 ローカル管理者は [ログのプロパティ] ダイアログを使用してこの値を変更できます。既定値は 20 MB に設定されています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066798)

  **既定値**: 32768

- **[Application log maximum file size in KB]\(アプリケーション ログの最大ファイル サイズ (KB)\)** :  
  このポリシー設定は、ログ ファイルの最大サイズを KB 単位で指定します。 このポリシー設定を有効にした場合、ログ ファイルの最大サイズを KB 単位で 1 MB (1024 KB) から 2 TB (2147483647 KB) までの範囲内に設定できます。 このポリシー設定を無効にした場合、または構成しなかった場合、ログ ファイルの最大サイズはローカルで構成された値に設定されます。 ローカル管理者は [ログのプロパティ] ダイアログを使用してこの値を変更できます。既定値は 20 MB に設定されています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067125)

  **既定値**: 32768

## <a name="experience"></a>エクスペリエンス

詳細については、Windows の「[Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)」(ポリシー CSP - Experience) を参照してください。

- **[Block Windows Spotlight]\(Windows スポットライトをブロックする\)** :  
  ロック画面上の Windows スポットライト、Windows のヒント、Microsoft のコンシューマー向け機能、その他の関連機能など、すべての Windows スポットライト機能を IT 管理者がオフにできるようにします。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067037)

  **既定値**: はい

  *[Windows Spotlight をブロックする]* を *[はい]* に設定すると、次の設定が利用できるようになります。

  - **[Block third-party suggestions in Windows Spotlight]\(Windows スポットライトでのサードパーティのおすすめをブロックする\)** :  
    ロック画面上のスポットライト、[スタート] メニューのおすすめのアプリ、Windows のヒントなど、Windows スポットライト機能でサードパーティのソフトウェア発行元からのアプリやコンテンツのおすすめを許可するかどうかを指定します。 ただし、Microsoft の機能、アプリ、およびサービスに関するおすすめはユーザーに表示されることがあります。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067045)

    **既定値**: はい

  - **[Block consumer specific features]\(コンシューマー向け機能をブロックする\)** :  
    通常はコンシューマー向けのエクスペリエンスを IT 管理者がオンにできるようにします。たとえば、開始時の提案、メンバーシップ通知、OOBE 後のアプリ インストール、リダイレクト タイルなどです。  
    [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067054)

    **既定値**: はい

## <a name="exploit-guard"></a>Exploit Guard

詳細については、Windows の「[Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard)」(ポリシー CSP - ExploitGuard) を参照してください。

- **[Exploit Protection XML]** :  
  IT 管理者が、組織内のすべてのデバイスに対して、目的のシステムとアプリケーションの軽減策オプションを表す構成をプッシュできるようにします。 この構成は XML で表されます。 Exploit Protection は、拡散と感染のためにエクスプロイトを使用するマルウェアからデバイスを保護するのに役立ちます。 Windows セキュリティ アプリまたは PowerShell を使用して、一連の軽減策 (構成と呼ばれます) を作成します。 次に、この構成を XML ファイルとしてエクスポートし、ネットワーク上の複数のマシンと共有して、すべてのマシンに同じ軽減策設定が適用されるようにすることができます。 既存の EMET 構成 XML ファイルを変換して Exploit Protection 構成 XML にインポートすることもできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067035)

  **既定値**: *サンプル XML を指定する*

## <a name="file-explorer"></a>エクスプローラー

詳細については、Windows の「[Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer)」(ポリシー CSP - FileExplorer) を参照してください。  

- **[Block data execution prevention]\(データ実行防止をブロックする\)** :  
  データ実行防止を無効にすると、エクスプローラーを終了せずに特定のレガシ プラグイン アプリケーションを実行できるようになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067043)  

  **既定値**: 無効

- **[Block heap termination on corruption]\(破損後のヒープ終了をブロックする\)** :  
  破損後のヒープ終了を無効にすると、エクスプローラーを直ちに終了せずに特定のレガシ プラグイン アプリケーションを機能させることができます。ただし、エクスプローラーは後で予期せず終了する可能性があります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067107)

  **既定値**: 無効

## <a name="internet-explorer"></a>Internet Explorer

詳細については、Windows の「[Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer)」(ポリシー CSP - InternetExplorer) を参照してください。

- **[Internet Explorer の制限付きゾーンでのスクリプトによるステータス バーの更新]** :  
  このポリシー設定を使用すると、スクリプトを介してゾーン内のステータス バーを更新できるかどうかを管理できます。

  - "*このポリシー設定を有効にすると*"、スクリプトを使用してステータス バーを更新できます。
  - "*このポリシー設定を無効にした場合、または構成しなかった場合*"、スクリプトを使用してステータス バーを更新することはできません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067074)

  **既定値**: 無効

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Internet Explorer のインターネット ゾーンでのファイルのドラッグ アンド ドロップまたはコピーと貼り付け]** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のソースからファイルのドラッグまたはコピーと貼り付けを行うことができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、このゾーンからファイルをドラッグまたはコピーするかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできません。 このポリシー設定を構成しない場合は、自動的に、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067076)

  **既定値**: 無効にする

- **[Internet Explorer の制限付きゾーンでの .NET Framework 依存コンポーネント]** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されていない .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照された管理されたコントロール、リンクから参照された管理された実行可能ファイルなどが含まれます。 このポリシー設定を有効にすると、Internet Explorer は署名されていない管理されたコンポーネントを実行します。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名されていない管理されたコンポーネントを実行するかどうかを確認するメッセージが Internet Explorer によって表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みではない管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer によって署名済みではない管理されたコンポーネントは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067077)

  **既定値**: 無効にする

- **[Internet Explorer のローカル コンピューター ゾーンで Active X コントロールに対してマルウェア対策を実行しない]** :  
  このポリシー設定では、ActiveX コントロールをページに読み込んでも安全かどうかを調べるために Internet Explorer がマルウェア対策プログラムを実行するかどうかを決定します。 このポリシー設定を有効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 このポリシー設定を無効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 このポリシー設定を構成しない場合、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 ユーザーは、Internet Explorer の [セキュリティ] 設定を使用して、この動作の有効と無効を切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067152)

  **既定値**: 無効

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer internet zone access to data sources]\(Internet Explorer のインターネット ゾーンにあるデータ ソースへのアクセス\)** :  
  このポリシー設定を使用すると、Internet Explorer が Microsoft XML パーサー (MSXML) または ActiveX Data Objects (ADO) を使用して他のセキュリティ ゾーンからデータにアクセスできるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。 このポリシー設定を構成しないと、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067078)  

  **既定値**: 無効にする

- **[Internet Explorer restricted zone drag content from different domains within windows]\(Internet Explorer の制限付きゾーンでウィンドウ内の異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定により、移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして、[有効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして、[無効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることはできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が同じウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067079)  

  **既定値**: 無効

- **[Internet Explorer certificate address mismatch warning]\(Internet Explorer の証明書アドレスの不一致についての警告\)** :  
  このポリシー設定では、証明書アドレスの不一致についてのセキュリティ警告を有効にできます。 このポリシー設定が有効である場合、ユーザーが別の Web サイト アドレス用に発行された証明書を提示する Secure HTTP (HTTPS) Web サイトを訪問すると、警告が表示されます。 この警告により、スプーフィング攻撃を防止できます。 このポリシー設定を有効にすると、証明書のアドレスの不一致についての警告が常に表示されます。 このポリシー設定を無効にするか、構成しないと、ユーザーはインターネット コントロール パネルの [詳細] ページを使用して、証明書のアドレスの不一致についての警告を表示するかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067153)  

  **既定値**: 有効

- **[Internet Explorer restricted zone less privileged sites]\(Internet Explorer の制限付きゾーンのより権限の少ないサイト\)** :  
  このポリシー設定を使用すると、インターネット サイト ゾーンなどのより権限の少ないゾーンにある Web サイトがこのゾーンに移動できるかどうかを管理できます。 このポリシー設定を有効にすると、より権限の少ないゾーンの Web サイトがこのゾーンで新しいウィンドウを開いたり、このゾーンに移動したりできます。 セキュリティ ゾーンは、[ゾーン昇格からの保護] のセキュリティ機能で提供されるセキュリティの追加のレイヤーなしに実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、危険を及ぼす可能性のあるナビゲーションが実行されるときにユーザーに警告が表示されます。 このポリシー設定を無効にすると、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。 このポリシー設定を構成しないと、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067148)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone automatic prompt for file downloads]\(Internet Explorer の制限付きゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーによってダウンロードが開始された場合はファイル ダウンロードのダイアログが表示されます。 この設定を有効にすると、ダウンロードが自動的に試行されたときにファイル ダウンロードのダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 その後、ユーザーは通知バーをクリックしてファイル ダウンロードのダイアログ表示を許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067150)

  **既定値**: 無効

- **[Internet Explorer internet zone .NET Framework reliant components]\(Internet Explorer のインターネット ゾーンでの .NET Framework 依存コンポーネント\)** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照された管理されたコントロール、リンクから参照された管理された実行可能ファイルなどが含まれます。 このポリシー設定を有効にすると、Internet Explorer は署名されていない管理されたコンポーネントを実行します。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名されていない管理されたコンポーネントを実行するかどうかを確認するメッセージが Internet Explorer によって表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みではない管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みではない管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067073)

  **既定値**: 無効にする

- **[Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls]\(Internet Explorer のインターネット ゾーンで承認済みドメインにのみ tdc ActiveX コントロールを使用できるようにする\)** :  
  このポリシー設定では、Web サイト上でユーザーが TDC ActiveX コントロールを実行できるようにするかどうかを制御します。 このポリシー設定を有効にすると、TDC ActiveX コントロールはこのゾーン内の Web サイトから実行されません。 このポリシー設定を無効にすると、TDC Active X コントロールがこのゾーンのすべてのサイトから実行されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067151)

  **既定値**: 有効

- **[Internet Explorer restricted zone script initiated windows]\(Internet Explorer の制限付きゾーンのスクリプトによって開かれるウィンドウ\)** :  
  このポリシー設定を使用すると、スクリプトによって起動されるポップアップ ウィンドウ、およびタイトルとステータス バーを持ったウィンドウの制限を管理できます。 このポリシー設定を有効にすると、Windows Restrictions セキュリティはこのゾーンでは適用されません。 セキュリティ ゾーンは、この機能で提供されるセキュリティの追加のレイヤーなしに実行されます。 このポリシー設定を無効にすると、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。 このポリシー設定を構成しないと、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067075)

  **既定値**: 無効

- **[Internet Explorer internet zone include local path when uploading files to server]\(Internet Explorer のインターネット ゾーンでサーバーへのファイルのアップロード時にローカル パスを含める\)** :  
  このポリシー設定では、ユーザーが HTML フォーム経由でファイルをアップロードするときに、ローカル パス情報が送信されるかどうかが制御されます。 ローカル パス情報が送信された場合、意図せずに、一部の情報がサーバーに公開されることがあります。 たとえば、ユーザーのデスクトップから送信されたファイルに、パスの一部としてユーザー名が含まれている可能性があります。 このポリシー設定を有効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が送信されます。 このポリシー設定を無効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報は削除されます。 このポリシー設定を構成しないと、ユーザーは、HTML フォーム経由でファイルをアップロードするときに、パス情報を送信するかどうかを選択できます。 既定では、パス情報は送信されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067072)

  **既定値**: 無効

- **[Internet Explorer disable processes in enhanced protected mode]\(Internet Explorer の拡張保護モードでプロセスを無効にする\)** :  
  このポリシー設定では、64 ビット バージョンの Windows の拡張保護モードで実行しているときに Internet Explorer 11 で (セキュリティの向上を目的として) 64 ビット プロセスを使用するか、または (互換性の向上を目的として) 32 ビット プロセスを使用するかを決定します。 重要: 64 ビット プロセスを使用する場合、一部の ActiveX コントロールおよびツール バーが使用できなくなる可能性があります。 このポリシー設定を有効にすると、64 ビット バージョンの Windows の拡張保護モードで実行しているときに Internet Explorer 11 で 64 ビット タブ プロセスを使用します。 このポリシー設定を無効にすると、64 ビット バージョンの Windows の拡張保護モードで実行しているときに Internet Explorer 11 で 32 ビット タブ プロセスを使用します。 このポリシー設定を構成しない場合、ユーザーは、Internet Explorer の設定を使用して、この機能の有効と無効を切り替えることができます。 この機能は既定で無効になっています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067149)

  **既定値**: 有効

- **[Internet Explorer ignore certificate errors]\(Internet Explorer で証明書エラーを無視する\)** :  
  このポリシー設定は、Internet Explorer での閲覧を妨げる Secure Sockets Layer/トランスポート層セキュリティ (SSL/TLS) 証明書エラー (期限切れ、失効、名前の不一致などのエラー) をユーザーが無視できないようにします。 このポリシー設定を有効にすると、ユーザーは閲覧を継続できません。 このポリシー設定を無効にするか、構成しない場合、ユーザーは証明書エラーを無視して閲覧を継続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067071)

  **既定値**: 無効

- **[Internet Explorer internet zone loading of XAML files]\(Internet Explorer のインターネット ゾーンでの XAML ファイルの読み込み\)** :  
  このポリシー設定を使用すると、Extensible Application Markup Language (XAML) ファイルの読み込みを管理できます。 XAML は、XML をベースにした宣言型マークアップ言語であり、Windows Presentation Foundation を活用した高度なユーザー インターフェイスやグラフィックスを作成するために一般に使用されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、XAML ファイルは Internet Explorer 内で自動的に読み込まれます。 ユーザーはこの動作を変更できません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、XAML ファイルを読み込むかどうかを確認するダイアログが表示されます。 このポリシー設定を無効にすると、XAML ファイルは Internet Explorer 内で読み込まれません。 ユーザーはこの動作を変更できません。 このポリシー設定を構成しなかった場合、ユーザーは XAML ファイルを Internet Explorer 内で読み込むかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067147)

  **既定値**: 無効にする

::: zone-end
::: zone pivot="mdm-may-2019"

- **[Internet Explorer internet zone automatic prompt for file downloads]\(Internet Explorer のインターネット ゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーによってダウンロードが開始された場合はファイル ダウンロードのダイアログが表示されます。 この設定を有効にすると、ダウンロードが自動的に試行されたときにファイル ダウンロードのダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 その後、ユーザーは通知バーをクリックしてファイル ダウンロードのダイアログ表示を許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067117)

  **既定値**: 無効

::: zone-end
::: zone pivot="mdm-preview"

- **[Internet Explorer internet zone automatic prompt for file downloads]\(Internet Explorer のインターネット ゾーンでのファイルのダウンロードに対する自動プロンプト\)** :  
  このポリシー設定を使用すると、ファイルのダウンロードがユーザー以外によって開始されたときにユーザーにメッセージを表示するかどうかを管理できます。 この設定に関係なく、ユーザーによってダウンロードが開始された場合はファイル ダウンロードのダイアログが表示されます。 この設定を有効にすると、ダウンロードが自動的に試行されたときにファイル ダウンロードのダイアログが表示されます。 この設定を無効にした場合、または構成しなかった場合は、ユーザー以外によって開始されたファイルのダウンロードはブロックされ、ファイル ダウンロードのダイアログの代わりに通知バーがユーザーに表示されます。 その後、ユーザーは通知バーをクリックしてファイル ダウンロードのダイアログ表示を許可できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067117)

  **既定値**: 有効

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer restricted zone security warning for potentially unsafe files]\(Internet Explorer の制限付きゾーンでの安全でない可能性があるファイルに対するセキュリティ警告\)** :  
  このポリシー設定では、ユーザーが (たとえば、エクスプローラーを使用してイントラネット ファイル共有から) 実行可能ファイルまたはその他の安全でない可能性があるファイルを開こうとしたときに、"ファイルを開く - セキュリティ警告" というメッセージが表示されるかどうかを制御します。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、そうしたファイルを開くときにセキュリティ警告は表示されません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ファイルを開く前にセキュリティ警告が表示されます。 このポリシー設定を無効にした場合、そうしたファイルは開きません。 このポリシー設定を構成しなかった場合、ユーザーがそうしたファイルの処理方法を構成できます。 既定では、そうしたファイルは制限付きゾーンではブロックされ、イントラネットおよびローカル コンピューター ゾーンでは有効になり、インターネットおよび信頼済みゾーンではダイアログを表示するように設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066797)

  **既定値**: 無効にする

- **[Internet Explorer internet zone cross site scripting filter]\(Internet Explorer のインターネット ゾーンのクロスサイト スクリプト フィルター\)** :  
  このポリシーでは、クロスサイト スクリプト (XSS) フィルターがこのゾーン内の Web サイトにあるクロスサイト スクリプト インジェクションを検出して防止するかどうかを制御します。 このポリシー設定を有効にすると、XSS フィルターはこのゾーン内のサイトに対して有効になり、クロスサイト スクリプト インジェクションのブロックを試みます。 このポリシー設定を無効にすると、XSS フィルターはこのゾーン内のサイトに対して無効となり、Internet Explorer ではクロスサイト スクリプト インジェクションが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067053)

  **既定値**: 有効

- **[Internet Explorer fallback to SSL3]\(Internet Explorer の SSL3 へのフォールバック\)** :  
  このポリシー設定を使用すると、SSL 3.0 への安全ではないフォールバックをブロックできます。 このポリシーが有効な場合、Internet Explorer では TLS 1.0 以降が失敗すると SSL 3.0 以前を使用してサイトへの接続を試行します。 中間者攻撃を防ぐために、安全でないフォールバックを許可しないことをお勧めします。 このポリシーは、どのセキュリティ プロトコルが有効になっているかには影響しません。 このポリシー設定を無効にすると、システムの既定値が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067118)

  **既定値**: サイトなし

::: zone-end
::: zone pivot="mdm-may-2019"

- **Internet Explorer の暗号化のサポート**:  
  このポリシー設定では、ブラウザーで Transport Layer Security (TLS) 1.0、TLS 1.1、TLS 1.2、Secure Sockets Layer (SSL) 2.0、または SSL 3.0 のサポートを無効にできます。 TLS と SSL は、ブラウザーとターゲット サーバー間の通信を保護するのに役立つプロトコルです。 ブラウザーがターゲット サーバーとの保護された通信を設定しようとすると、ブラウザーとサーバーは使用するプロトコルとバージョンについてネゴシエートします。 ブラウザーとサーバーは、サポートするプロトコルとバージョンに関する互いの一覧を照らし合わせ、最善の組み合わせを選択します。 このポリシー設定を有効にした場合、ブラウザーは、ユーザーがドロップダウン リストから選択した暗号化方法を使用して暗号トンネルをネゴシエートするときとしないときがあります。 このポリシー設定を無効にするか構成しない場合、ユーザーはブラウザーがサポートする暗号化方法を選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067057)

  **既定値**: 2 項目: tls V1.1 および tls v1.0  
  *下矢印を選択すると、この設定で選択できるオプションが表示されます。*

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Internet Explorer locked down internet zone smart screen]\(Internet Explorer のロックダウンされたインターネット ゾーンでのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。 このポリシー設定を有効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンします。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注: Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067059)

  **既定値**: 有効

- **[Internet Explorer restricted zone launch applications and files in an iFrame]\(Internet Explorer の制限付きゾーンで iFrame のアプリケーションとファイルを起動する\)** :  
  このポリシー設定を使用すると、このゾーン内のページの HTML にある IFRAME 参照からアプリケーションを実行したりファイルをダウンロードしたりすることができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかをユーザーにたずねます。 このポリシー設定を無効にした場合、ユーザーは、このゾーン内のページの Iframe からアプリケーションを実行したりファイルをダウンロードしたりすることはできません。 このポリシー設定を構成しない場合は、ユーザーはこのゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりすることができません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067061)

  **既定値**: 無効にする

- **[Internet Explorer での一般的ではないファイルに関するスマート スクリーン警告のバイパス]** :  
  このポリシー設定では、ユーザーが SmartScreen フィルター機能からの警告をバイパスできるかどうかを決定します。 SmartScreen フィルター機能では、ダウンロードしたユーザー数が少ない実行可能ファイルについてユーザーに警告します。 このポリシー設定を有効にすると、ユーザーは SmartScreen フィルター機能の警告によってブロックされます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは SmartScreen フィルター機能の警告をバイパスできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067068)

  **既定値**: 無効

- **[Internet Explorer internet zone popup blocker]\(Internet Explorer のインターネット ゾーンのポップアップ ブロッカー\)** :  
  このポリシー設定を使用すると、不要なポップアップ ウィンドウが表示されるかどうかを管理できます。 エンド ユーザーがリンクをクリックしたときに開かれるポップアップ ウィンドウはブロックされません。 このポリシー設定を有効にすると、不要なポップアップ ウィンドウは表示されません。 このポリシー設定を無効にすると、ポップアップ ウィンドウの表示は禁止されません。 このポリシー設定を構成しない場合は、不要なポップアップ ウィンドウは表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067069)

  **既定値**: 有効にする

- **[Internet Explorer processes consistent MIME handling]\(Internet Explorer での一貫性のある MIME 処理\)** :  
  Internet Explorer には動的なバイナリ ビヘイビアー (動作が関連付けられている HTML 要素のための特定の機能をカプセル化するコンポーネント) が含まれます。 このポリシー設定はバイナリ ビヘイビアーのセキュリティの制限の設定を許可するかまたは使用不可にするかを制御します。 このポリシー設定を有効にすると、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスでは使用不可になります。 このポリシー設定を無効にすると、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスで許可されます。 このポリシー設定を構成しない場合は、バイナリ ビヘイビアーはエクスプローラーおよび Internet Explorer のプロセスでは使用不可になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067144)  

  **既定値**: 有効

- **[Internet Explorer の制限付きゾーンの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067132)

  **既定値**: Java を無効にする

- **[Internet Explorer Active X controls in protected mode]\(Internet Explorer の保護モードでの ActiveX コントロール\)** :  
  このポリシー設定を使用すると、拡張保護モードが有効になっている場合に保護モードで ActiveX コントロールを実行できなくなります。 拡張保護モードと互換性がない ActiveX コントロールがインストールされ、Web サイトがそのコントロールの読み込みを試行した場合、Internet Explorer によってユーザーに通知が行われ、Web サイトを通常の保護モードで実行するためのオプションが表示されます。 本ポリシー設定を使用すると、この通知が無効になり、すべての Web サイトが拡張保護モードで実行されるようになります。 拡張保護モードでは、64 ビット バージョンの Windows で 64 ビット プロセスが使用され、悪意のある Web サイトに対する保護が強化されています。 Windows 8 以降が実行されているコンピューターでは、拡張保護モードによって、Internet Explorer が読み取り元に設定できる場所もレジストリとファイル システムに制限されています。 拡張保護モードが有効になっていて、拡張保護モードと互換性がない ActiveX コントロールの読み込みを試行する Web サイトをユーザーが表示しようとした場合は、Internet Explorer によってユーザーに通知が行われ、その Web サイトで拡張保護モードを無効にするためのオプションが表示されます。 このポリシー設定を有効にすると、拡張保護モードを無効にするオプションは Internet Explorer でユーザーに表示されなくなります。 保護モードの Web サイトはすべて、拡張保護モードで実行されます。 このポリシー設定を無効にした場合、または構成しない場合は、Internet Explorer によってユーザーに通知が行われ、互換性がない ActiveX コントロールが含まれている Web サイトを通常の保護モードで実行するためのオプションが表示されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067145)

  **既定値**: 無効

- **[Internet Explorer restricted zone loading of XAML files]\(Internet Explorer の制限付きゾーンでの XAML ファイルの読み込み\)** :  
  このポリシー設定を使用すると、Extensible Application Markup Language (XAML) ファイルの読み込みを管理できます。 XAML は、XML をベースにした宣言型マークアップ言語であり、Windows Presentation Foundation を活用した高度なユーザー インターフェイスやグラフィックスを作成するために一般に使用されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、XAML ファイルは Internet Explorer 内で自動的に読み込まれます。 ユーザーはこの動作を変更できません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、XAML ファイルを読み込むかどうかを確認するダイアログが表示されます。 このポリシー設定を無効にすると、XAML ファイルは Internet Explorer 内で読み込まれません。 ユーザーはこの動作を変更できません。 このポリシー設定を構成しなかった場合、ユーザーは XAML ファイルを Internet Explorer 内で読み込むかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067070)

  **既定値**: 無効にする

- **[Internet Explorer processes scripted window security restrictions]\(Internet Explorer プロセスでのスクリプト化されたウィンドウのセキュリティ制限\)**  
  Internet Explorer は、スクリプトがプログラムを使ってさまざまな種類のウィンドウを開いたり、ウィンドウのサイズや場所を変更したりすることを許可しています。 ウィンドウ制限のセキュリティ機能は、ポップアップ ウィンドウを制限し、スクリプトがタイトル バーやステータス バーがユーザーに表示されないウィンドウ、または Windows の他のタイトル バーやステータス バーと混乱するようなウィンドウを表示することを禁止します。 このポリシー設定を有効にすると、スクリプト化されたウィンドウはすべてのプロセスで制限されます。 このポリシー設定を無効にするか、または構成しない場合は、スクリプト化されたウィンドウには制限は適用されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067146)

  **既定値**: 有効

- **[Internet Explorer restricted zone run Active X controls and plugins]\(Internet Explorer の制限付きゾーンで Active X コントロールおよびプラグインを実行する\)** :  
  このポリシー設定を使用すると、指定されたゾーンのページ上で ActiveX コントロールおよびプラグインが実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、コントロールやプラグインを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールやプラグインの実行を許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、コントロールとプラグインは実行されません。 このポリシー設定を構成しない場合は、コントロールとプラグインは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067114)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone script Active X controls marked safe for scripting]\(Internet Explorer の制限付きゾーンでスクリプトを実行しても安全であるとマークされた Active X コントロールをスクリプト化する\)** :  
  このポリシー設定を使用すると、スクリプトを実行しても安全であるとマークされた ActiveX コントロールがスクリプトと対話できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、スクリプトの対話を自動的に実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、スクリプトの対話を許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、スクリプトの対話は実行されません。 このポリシー設定を構成しない場合は、スクリプトの対話は実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067062)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone logon options]\(Internet Explorer の制限付きゾーンのログオン オプション\)** :  
  このポリシー設定を使用すると、サインイン オプションの設定を管理できます。 このポリシー設定を有効にすると、次のサインイン オプションから選択できます。

  - *匿名* - HTTP 認証を無効にして、Common Internet File System (CIFS) プロトコル用にのみ guest アカウントを使用する場合は、匿名サインインを使用します。

  - *プロンプト* - ユーザーの ID とパスワードを照会するために、ユーザー名とパスワードの入力を求めます。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。

  - *イントラネット ゾーンでのみ自動的にサインインする* - 他のゾーンでのユーザー ID とパスワードをユーザーに照会するには、このオプションを使用します。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。

  - *現在のユーザー名とパスワードで自動的にサインインする* - Windows NT チャレンジ応答 (別名 NTLM 認証) を使用してログオンを試みるには、このオプションを使用します。 サーバーで Windows NT チャレンジ応答がサポートされている場合、サインインでは、ユーザーのサインイン用のネットワーク ユーザー名とパスワードが使用されます。 サーバーで Windows NT チャレンジ応答がサポートされていない場合、ユーザーはユーザー名とパスワードを提供する必要があります。

  このポリシー設定を無効にすると、サインインは "*イントラネット ゾーンでのみ自動的にサインインする*" に設定されます。 このポリシー設定を構成しなかった場合、サインインは "*プロンプト*" に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067110)

  **既定値**: 匿名

- **[Internet Explorer trusted zone initialize and script Active X controls not marked as safe]\(Internet Explorer の信頼済みゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全であるとマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定では、安全なコントロールと安全ではないコントロールの両方を初期化およびスクリプト化します。[スクリプトを実行しても安全だとマークされている ActiveX コントロールのスクリプトの実行] オプションは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、コントロールにパラメーターを読み込んだりスクリプト化したりするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067137)

  **既定値**: 無効にする

- **[Internet Explorer check server certificate revocation]\(Internet Explorer でサーバー証明書の失効状態を確認する\)** :  
  このポリシー設定を使うと、サーバーの証明書の失効状態を確認するかどうかを管理できます。 証明書は、危害を受けたか、有効ではなくなった場合に失効されます。このオプションを使うと、詐欺目的であるか、安全ではない可能性があるサイトにユーザーが機密データを送信するのを防ぐことができます。 このポリシー設定を有効にすると、サーバーの証明書が失効したかどうかが確認されます。 このポリシー設定を無効にすると、サーバーの証明書が失効したかどうかが Internet Explorer によって確認されません。 このポリシー設定を構成しなかった場合、サーバーの証明書が失効したかどうかが Internet Explorer によって確認されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067046)

  **既定値**: 有効

- **[Internet Explorer internet zone less privileged sites]\(Internet Explorer のインターネット ゾーンのより権限の少ないサイト\)** :  
  このポリシー設定を使用すると、制限付きサイト ゾーンなどのより特権が低いゾーンにある Web サイトがこのゾーンに移動できるかどうかを管理できます。 このポリシー設定を有効にすると、より権限の少ないゾーンの Web サイトがこのゾーンで新しいウィンドウを開いたり、このゾーンに移動したりできます。 セキュリティ ゾーンは、[ゾーン昇格からの保護] のセキュリティ機能で提供されるセキュリティの追加のレイヤーなしに実行されます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、危険を及ぼす可能性のあるナビゲーションが実行されるときにユーザーに警告が表示されます。 このポリシー設定を無効にすると、危害を及ぼす可能性のあるナビゲーションは禁止されます。 Internet Explorer のセキュリティ機能は、[ゾーン昇格からの保護] 機能コントロールで設定されているように、このゾーンでオンになります。 このポリシー設定を構成しない場合は、より権限の少ないゾーンの Web サイトがこのゾーンで新しいウィンドウを開いたり、このゾーンに移動したりできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067109)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone file downloads]\(Internet Explorer の制限付きゾーンでのファイルのダウンロード\)** :  
  このポリシー設定を使用すると、ゾーンからのファイルのダウンロードが許可されるかどうかを管理できます。 このオプションは、ファイルの配信元のゾーンではなく、ダウンロードを開始するリンクがあるページのゾーンによって決定されます。 このポリシー設定を有効にすると、ゾーンからファイルをダウンロードできます。 このポリシー設定を無効にすると、ゾーンからファイルをダウンロードできません。 このポリシー設定を構成しない場合は、ゾーンからファイルをダウンロードできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067038)

  **既定値**: 無効にする

- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode\(Internet Explorer のインターネット ゾーンで Authenticode 署名済みの .NET Framework 依存コンポーネントを実行する\)** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照された管理されたコントロール、リンクから参照された管理された実行可能ファイルなどが含まれます。 このポリシー設定を有効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行します。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名済みの管理されたコンポーネントを実行するかどうかを確認するメッセージが Internet Explorer によって表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みの管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067033)

  **既定値**: 無効にする

- **[Internet Explorer でユーザーごとに Active X コントロールをインストールできないようにする]** :  
  このポリシー設定では、ActiveX コントロールをユーザーごとにインストールできないようにできます。 このポリシー設定を有効にすると、ActiveX コントロールはユーザーごとにインストールできなくなります。 このポリシー設定を無効にするか構成しないと、ActiveX コントロールはユーザーごとにインストールできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067058)

  **既定値**: 有効

- **[Internet Explorer prevent managing smart screen filter]\(Internet Explorer でスマート スクリーン フィルターを管理できないようにする\)** :  
  このポリシー設定は、ユーザーが SmartScreen フィルターを管理できないようにします。SmartScreen フィルターを有効にすると、"フィッシング" を通じて個人情報を不正に収集することがわかっている Web サイト、または悪意のあるソフトウェアをホストしていることがわかっている Web サイトにアクセスしようとすると警告が表示されます。 このポリシー設定を有効にすると、ユーザーには、SmartScreen フィルターを有効にするためのダイアログは表示されません。 フィルターの許可リストに含まれない Web サイトのアドレスはすべて Microsoft に自動的に送信され、ユーザーにはダイアログは表示されません。 このポリシー設定を無効にするか、構成しない場合、ユーザーには、初回実行時に SmartScreen フィルターを有効にするかどうかを選択するためのダイアログが表示されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067135)

  **既定値**: 有効にする

- **[Internet Explorer processes MIME sniffing safety feature]\(Internet Explorer プロセスでの MIME スニッフィングの安全機能\)** :  
  このポリシー設定は、ある種類のファイルをより危険な種類のファイルに昇格することを Internet Explorer MIME スニッフィングが防止するかどうかを決定します。 このポリシー設定を有効にすると、MIME スニッフィングは、ある種類のファイルをより危険な種類に昇格することはありません。 このポリシー設定を無効にすると、Internet Explorer プロセスで、MIME スニッフィングがファイルをより危険な種類に昇格することは許可されます。 このポリシー設定を構成しない場合は、MIME スニッフィングは、ある種類のファイルをより危険な種類に昇格することはありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067124)

  **既定値**: 有効

- **[Internet Explorer restricted zone download signed Active X controls]\(Internet Explorer の制限付きゾーンで署名された Active X コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンにあるページから署名された ActiveX コントロールをダウンロードすることを許可するかどうかを管理できます。 このポリシーを有効にすると、ユーザーによる手動操作を必要とすることなく、署名されたコントロールをダウンロードできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼されている発行元によって署名されたコードは警告なしにダウンロードされます。 このポリシー設定を無効にすると、署名されたコントロールはダウンロードできません。 このポリシー設定を構成しない場合は、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼されている発行元によって署名されたコードは警告なしにダウンロードされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067120)

  **既定値**: 無効にする

- **[Internet Explorer auto complete]\(Internet Explorer のオート コンプリート\)** :  
  このオートコンプリート機能では、フォーム上のユーザー名とパスワードを記憶して、候補を表示できます。 この設定を有効にすると、ユーザーは [フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] のオプションを変更できません。 フォームのユーザー名とパスワードのオートコンプリート機能は有効になります。 "パスワードを保存する確認をする" オプションを選択するかどうかを決定します。 この設定を無効にすると、ユーザーは [フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] を変更できません。 フォームのユーザー名とパスワードのオートコンプリート機能は無効になります。 ユーザーは、パスワードの保存を確認するように選択することもできません。 この設定を構成しない場合、ユーザーは、[フォームのユーザー名およびパスワード] や [パスワードを保存する確認をする] のオプションを有効にすることができます。 このオプションを表示するには、ユーザーは [インターネット オプション] ダイアログ ボックスを開いて、[コンテンツ] タブ、[設定] ボタンの順にクリックします。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067122)

  **既定値**: 無効

- **[Internet Explorer internet zone allow VBscript to run]\(Internet Explorer のインターネット ゾーンで VB スクリプトの実行を許可する\)** :  
  このポリシー設定では、VB スクリプトが特定の Internet Explorer のゾーンでページを実行できるかどうかを決定できます。 次のオプションがあります。

  - "*有効*" - 対話式の操作を行くことなく、VB スクリプトが特定のゾーンのページ上で実行されます。

  - "*プロンプト*" - 従業員は VB スクリプトをそのゾーンで実行できるようにするかどうかを確認されます。

  - "*無効*" - VB スクリプトはそのゾーンで実行できないようにされます。 このポリシー設定を無効にした場合、または構成しない場合は、VBScript は特定のゾーンで対話式の操作を行くことなく実行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067119)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone allow only approved domains to use tdc Active X controls]\(Internet Explorer の制限付きゾーンで承認済みドメインのみ TDC Active X コントロールを使用できるようにする\)** :  
  このポリシー設定では、Web サイト上でユーザーが TDC ActiveX コントロールを実行できるようにするかどうかを制御します。 このポリシー設定を有効にすると、TDC ActiveX コントロールはこのゾーン内の Web サイトから実行されません。 このポリシー設定を無効にすると、TDC Active X コントロールがこのゾーンのすべてのサイトから実行されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067032)

  **既定値**: 有効

- **[Internet Explorer trusted zone don't run antimalware against Active X controls]\(Internet Explorer の信頼済みゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、ActiveX コントロールをページに読み込んでも安全かどうかを調べるために Internet Explorer がマルウェア対策プログラムを実行するかどうかを決定します。 このポリシー設定を有効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 このポリシー設定を無効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 このポリシー設定を構成しない場合、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 ユーザーは、Internet Explorer の [セキュリティ] 設定を使用して、この動作の有効と無効を切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067115)

  **既定値**: 無効

- **[Internet Explorer local machine zone java permissions]\(Internet Explorer のローカル コンピューター ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 中] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067113)

  **既定値**: Java を無効にする

- **[Internet Explorer intranet zone do not run antimalware against Active X controls]\(Internet Explorer のイントラネット ゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、ActiveX コントロールをページに読み込んでも安全かどうかを調べるために Internet Explorer がマルウェア対策プログラムを実行するかどうかを決定します。 このポリシー設定を有効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 このポリシー設定を無効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 このポリシー設定を構成しない場合、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 ユーザーは、Internet Explorer の [セキュリティ] 設定を使用して、この動作の有効と無効を切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067138)

  **既定値**: 無効

- **[Internet Explorer restricted zone scriptlets]\(Internet Explorer の制限付きゾーンのスクリプトレット\)** :  
  このポリシー設定を使用すると、ユーザーがスクリプトレットを実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはスクリプトレットを実行できます。 このポリシー設定を無効にすると、ユーザーはスクリプトレットを実行できません。 このポリシー設定を構成しなかった場合、ユーザーはスクリプトレットを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067112)

  **既定値**: 無効

- **[Internet Explorer processes notification bar]\(Internet Explorer プロセスの通知バー\)** :  
  このポリシー設定を使うと、ファイルやコードのインストールが制限されている場合に、Internet Explorer プロセスに対して通知バーを表示するかどうかを管理できます。 既定では、通知バーは Internet Explorer プロセスに対して表示されます。 このポリシー設定を有効にすると、通知バーは Internet Explorer プロセスに対して表示されます。 このポリシー設定を無効にすると、通知バーは Internet Explorer プロセスに対して表示されません。 このポリシー設定を構成しない場合は、通知バーは Internet Explorer プロセスに対して表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067139)

  **既定値**: 有効

- **[Internet Explorer internet zone download signed ActiveX controls]\(Internet Explorer のインターネット ゾーンで署名された ActiveX コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンにあるページから署名された ActiveX コントロールをダウンロードすることを許可するかどうかを管理できます。 このポリシーを有効にすると、ユーザーによる手動操作を必要とすることなく、署名されたコントロールをダウンロードできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼されている発行元によって署名されたコードは警告なしにダウンロードされます。 このポリシー設定を無効にすると、署名されたコントロールはダウンロードできません。 このポリシー設定を構成しない場合は、信頼されていない発行元によって署名されたコントロールをダウンロードするかどうかをユーザーにたずねます。 信頼されている発行元によって署名されたコードは警告なしにダウンロードされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067064)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone smart screen]\(Internet Explorer の制限付きゾーンのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。 このポリシー設定を有効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンします。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注: Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067034)

  **既定値**: 有効

- **[Internet Explorer remove run this time button for outdated Active X controls]\(Internet Explorer で古い Active X コントロール用の [今回は実行] ボタンを削除する\)** :  
  このポリシー設定を使用すると、Internet Explorer で [今回は実行] ボタンが表示されないようにして、ユーザーが特定の古い ActiveX コントロールを実行できないようにすることができます。 このポリシー設定を有効にした場合、Internet Explorer で古い ActiveX コントロールがブロックされるときに表示される警告メッセージに [今回は実行] ボタンが表示されなくなります。 このポリシー設定を無効にした場合、または構成しなかった場合、Internet Explorer で古い ActiveX コントロールがブロックされるときに表示される警告メッセージに [今回は実行] ボタンが表示されます。 このボタンをクリックすると、ユーザーは古い ActiveX コントロールを 1 回実行できます。 詳細については、Internet Explorer TechNet ライブラリの古い ActiveX コントロールに関するページを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067123)

  **既定値**: 有効

- **[Internet Explorer internet zone launch applications and files in an iframe]\(Internet Explorer のインターネット ゾーンで IFRAME のアプリケーションとファイルを起動する\)** :  
  このポリシー設定を使用すると、このゾーン内のページの HTML にある IFRAME 参照からアプリケーションを実行したりファイルをダウンロードしたりすることができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかをユーザーにたずねます。 このポリシー設定を無効にした場合、ユーザーは、このゾーン内のページの Iframe からアプリケーションを実行したりファイルをダウンロードしたりすることはできません。 このポリシー設定を構成しない場合は、このゾーンにあるページ上の IFRAME からアプリケーションを実行したりファイルをダウンロードしたりするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067020)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone navigate windows and frames across different domains]\(Internet Explorer の制限付きゾーンで異なるドメインを超えてウィンドウとフレームを移動する\)** :  
  このポリシー設定により、移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067050)

  **既定値**: 無効にする

- **[Internet Explorer internet zone smart screen]\(Internet Explorer のインターネット ゾーンのスマート スクリーン\)** :  
  このポリシー設定では、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。 このポリシー設定を有効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンします。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注: Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067047)

  **既定値**: 有効

- **[Internet Explorer locked down trusted zone java permissions]\(Internet Explorer のロックダウンされた信頼済みゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067142)

  **既定値**: Java を無効にする

- **[Internet Explorer check signatures on downloaded programs]\(Internet Explorer でダウンロードされたプログラムの署名を確認する\)** :  
  このポリシー設定を使うと、実行可能プログラムをダウンロードする前に、(署名済みソフトウェアの発行者を識別し、変更や改ざんが行われていないことを確認する) デジタル署名をコンピューター上で確認するかどうかを管理できます。 このポリシー設定を有効にすると、コンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名を確認し、識別情報を表示します。 このポリシー設定を無効にすると、コンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名の確認や識別情報の表示を行いません。 このポリシー設定を構成しなかった場合、コンピューターに実行可能プログラムをダウンロードする前に、プログラムのデジタル署名の確認や識別情報の表示を行いません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067051)

  **既定値**: 有効

- **[Internet Explorer restricted zone scripting of web browser controls]\(Internet Explorer の制限付きゾーンでの Web ブラウザー コントロールのスクリプト化\)** :  
  このポリシー設定では、ページで、スクリプトを使用して埋め込みの WebBrowser コントロールを制御できるかどうかを決定します。 このポリシー設定を有効にすると、WebBrowser コントロールへのスクリプト アクセスが許可されます。 このポリシー設定を無効にすると、WebBrowser コントロールへのスクリプト アクセスは許可されません。 このポリシー設定を構成しなかった場合、ユーザーは WebBrowser コントロールへのスクリプト アクセスを有効または無効にできます。 既定では、WebBrowser コントロールへのスクリプト アクセスは、ローカル コンピューターおよびイントラネット ゾーン内でのみ許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067098)

  **既定値**: 無効

- **[Internet Explorer restricted zone cross site scripting filter]\(Internet Explorer の制限付きゾーンのクロスサイト スクリプト フィルター\)** :  
  このポリシーでは、クロスサイト スクリプト (XSS) フィルターがこのゾーン内の Web サイトにあるクロスサイト スクリプト インジェクションを検出して防止するかどうかを制御します。 このポリシー設定を有効にすると、XSS フィルターはこのゾーン内のサイトに対して有効になり、クロスサイト スクリプト インジェクションのブロックを試みます。 このポリシー設定を無効にすると、XSS フィルターはこのゾーン内のサイトに対して無効となり、Internet Explorer ではクロスサイト スクリプト インジェクションが許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067178)

  **既定値**: 有効

- **[Internet Explorer restricted zone binary and script behaviors]\(Internet Explorer の制限付きゾーンでのバイナリ ビヘイビアーとスクリプト ビヘイビアー\)** :  
  このポリシー設定を使用すると、動的なバイナリ ビヘイビアーとスクリプト ビヘイビアー (動作が関連付けられた HTML 要素のための特定の機能をカプセル化するコンポーネント) を管理できます。 このポリシー設定を有効にすると、バイナリ ビヘイビアーとスクリプト ビヘイビアーを利用できます。 ドロップダウン ボックスで [管理者の許可済み] を選択した場合、[バイナリ ビヘイビアーのセキュリティの制限] ポリシーの管理者によって許可されたビヘイビアーに一覧表示されている動作のみ利用できます。 このポリシー設定を無効にした場合、アプリケーションがカスタムのセキュリティ マネージャーを実装していない限り、バイナリ ビヘイビアーとスクリプト ビヘイビアーは利用できません。 このポリシー設定を構成しない場合は、アプリケーションがカスタムのセキュリティ マネージャーを実装していない限り、バイナリ ビヘイビアーとスクリプト ビヘイビアーは利用できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067224)

  **既定値**: 無効にする

- **[Internet Explorer security settings check]\(Internet Explorer のセキュリティ設定のチェック\)** :  
  このポリシー設定は、セキュリティ設定チェック機能を無効にします。この機能は、Internet Explorer のセキュリティ設定をチェックして、Internet Explorer を危険にさらす設定が含まれていないか確認します。 このポリシー設定を有効にすると、機能は無効になります。 このポリシー設定を無効にするか、構成しない場合、機能は有効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067182)

  **既定値**: 有効

- **[Internet Explorer internet zone security warning for potentially unsafe files]\(Internet Explorer のインターネット ゾーンでの安全でない可能性があるファイルに対するセキュリティ警告\)** :  
  このポリシー設定では、ユーザーが (たとえば、エクスプローラーを使用してイントラネット ファイル共有から) 実行可能ファイルまたはその他の安全でない可能性があるファイルを開こうとしたときに、"ファイルを開く - セキュリティ警告" というメッセージが表示されるかどうかを制御します。 このポリシー設定を有効にして、ドロップダウン ボックスで [有効にする] を選択した場合、そうしたファイルを開くときにセキュリティ警告は表示されません。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ファイルを開く前にセキュリティ警告が表示されます。 このポリシー設定を無効にした場合、そうしたファイルは開きません。 このポリシー設定を構成しなかった場合、ユーザーがそうしたファイルの処理方法を構成できます。 既定では、そうしたファイルは制限付きゾーンではブロックされ、イントラネットおよびローカル コンピューター ゾーンでは有効になり、インターネットおよび信頼済みゾーンではダイアログを表示するように設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067204)

  **既定値**: プロンプト

- **[Internet Explorer intranet zone java permissions]\(Internet Explorer のイントラネット ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 中] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067206)

  **既定値**: 安全性 - 高

- **[Internet Explorer で古い Active X コントロールをブロックする]** :  
  このポリシー設定では、Internet Explorer で特定の古い ActiveX コントロールをブロックするかどうかを決定します。 イントラネット ゾーンでは、古い ActiveX コントロールがブロックされません。 このポリシー設定を有効にした場合、Internet Explorer では、古い ActiveX コントロールのブロックが停止します。 このポリシー設定を無効にした場合、または構成しなかった場合、Internet Explorer では、引き続き特定の古い ActiveX コントロールがブロックされます。 詳細については、Internet Explorer TechNet ライブラリの古い ActiveX コントロールに関するページを参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067203)

  **既定値**: 有効

- **[Internet Explorer restricted zone popup blocker]\(Internet Explorer の制限付きゾーンでのポップアップ ブロック\)** :  
  このポリシー設定を使用すると、不要なポップアップ ウィンドウが表示されるかどうかを管理できます。 エンド ユーザーがリンクをクリックしたときに開かれるポップアップ ウィンドウはブロックされません。 このポリシー設定を有効にすると、不要なポップアップ ウィンドウは表示されません。 このポリシー設定を無効にすると、ポップアップ ウィンドウの表示は禁止されません。 このポリシー設定を構成しない場合は、不要なポップアップ ウィンドウは表示されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067180)

  **既定値**: 有効にする

- **[Internet Explorer processes MK protocol security restriction]\(Internet Explorer プロセスでの MK プロトコル セキュリティの制限\)** :  
  [MK プロトコル セキュリティの制限] ポリシー設定を使うと、MK プロトコルを使用不可にすることで危険を回避できます。 MK プロトコルでホストされているリソースはエラーになります。 このポリシー設定を有効にすると、エクスプローラーおよび Internet Explorer で MK プロトコルが使用不可になり、MK プロトコルでホストされているリソースはエラーになります。 このポリシー設定を無効にすると、アプリケーションは MK プロトコル API を使うことができます。 MK プロトコルでホストされているリソースは、エクスプローラーおよび Internet Explorer のプロセスで機能します。 このポリシー設定を構成しない場合は、エクスプローラーおよび Internet Explorer で MK プロトコルが使用不可になり、MK プロトコルでホストされているリソースはエラーになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067179)

  **既定値**: 有効

- **[Internet Explorer の信頼済みゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、アクセス許可は [安全性 - 低] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067200)

  **既定値**: 安全性 - 高

- **[Internet Explorer restricted zone scripting of java applets]\(Internet Explorer の制限付きゾーンでの Java アプレットのスクリプト化\)** :  
  このポリシー設定を使用すると、ゾーン内のスクリプトがアプレットにアクセスできるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、スクリプトはアプレットに自動的にアクセスできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、スクリプトがアプレットにアクセスすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、スクリプトはアプレットにアクセスできません。 このポリシー設定を構成しなかった場合、スクリプトはアプレットにアクセスできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067202)

  **既定値**: 無効にする

- **[Internet Explorer のロックダウンされた制限付きゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067181)

  **既定値**: Java を無効にする

- **[Internet Explorer のインターネット ゾーンで承認済みドメインだけが ActiveX コントロールを使用できるようにする]** :  
  このポリシー設定では、ActiveX コントロールをインストールした Web サイト以外の Web サイトで ActiveX コントロールを実行する許可を求めるメッセージをユーザーに表示するかどうかを制御します。 このポリシー設定を有効にすると、このゾーン内の Web サイトで ActiveX コントロールが実行される前に、ユーザーにメッセージが表示されます。 ユーザーは、現在のサイトからのコントロールの実行を許可するか、すべてのサイトからのコントロールの実行を許可するかを選択できます。 このポリシー設定を無効にすると、ユーザーにはサイトごとの ActiveX 警告は表示されず、ActiveX コントロールはこのゾーン内のすべてのサイトから実行できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067091)

  **既定値**: 有効

- **[Internet Explorer include all network paths]\(Internet Explorer ですべてのネットワーク パスを含める\)** :  
  Internet Explorer にはすべてのネットワーク パスが含まれます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067090)

  **既定値**: 無効

- **[Internet Explorer internet zone protected mode]\(Internet Explorer のインターネット ゾーンの保護モード\)** :  
  このポリシー設定を使用すると、保護モードを有効にできます。 保護モードを使用すると、Internet Explorer が書き込むことができるレジストリやファイル システム内の場所を制限することで、脆弱点を悪用した攻撃から Internet Explorer を保護できます。 このポリシー設定を有効にすると、保護モードが有効になります。 ユーザーは保護モードを無効にできません。 このポリシー設定を無効にすると、保護モードが無効になります。 ユーザーは保護モードを有効にできません。 このポリシー設定を構成しなかった場合、ユーザーは保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067171)

  **既定値**: 有効にする

- **[Internet Explorer internet zone initialize and script Active X controls not marked as safe]\(Internet Explorer のインターネット ゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全であるとマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定では、安全なコントロールと安全ではないコントロールの両方を初期化およびスクリプト化します。[スクリプトを実行しても安全だとマークされている ActiveX コントロールのスクリプトの実行] オプションは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067170)

  **既定値**: 無効にする

- **[Internet Explorer のロックダウンされた制限付きゾーンでのスマート スクリーン]** :  
  このポリシー設定では、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。 このポリシー設定を有効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンします。 このポリシー設定を無効にすると、SmartScreen フィルターはこのゾーンのページの悪意のあるコンテンツをスキャンしません。 このポリシー設定を構成しない場合、SmartScreen フィルターがこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかをユーザーが選択できます。 注: Internet Explorer 7 の場合、このポリシー設定では、フィッシング詐欺検出機能がこのゾーンのページの悪意のあるコンテンツをスキャンするかどうかを制御します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067092)

  **既定値**: 有効

- **[Internet Explorer crash detection]\(Internet Explorer のクラッシュの検出\)** :  
  このポリシー設定を使うと、アドオン管理のクラッシュ検出機能を管理できます。 このポリシー設定を有効にすると、Internet Explorer でクラッシュが起きた場合、Windows XP Professional Service Pack 1 またはそれ以前の場合と同様に、Windows エラー報告が起動されます。 Windows エラー報告のポリシー設定はすべて引き続き適用されます。 このポリシー設定を無効にするか、または構成しない場合は、アドオン管理のクラッシュ検出機能は動作します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067094)

  **既定値**: 無効

- **[Internet Explorer internet zone java permissions]\(Internet Explorer のインターネット ゾーンでの Java のアクセス許可\)** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しない場合は、アクセス許可は [安全性 - 高] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067174)

  **既定値**: Java を無効にする

- **[Internet Explorer restricted zone active scripting]\(Internet Explorer の制限付きゾーンでのアクティブ スクリプティング\)** :  
  このポリシー設定を使用すると、ゾーンのページにあるスクリプト コードを実行するかどうかを管理できます。 このポリシー設定を有効にすると、ゾーン内のページ上のスクリプト コードを自動的に実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ゾーン内のページ上のスクリプト コードの実行を許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ゾーンのページ上のスクリプト コードは実行されません。 このポリシー設定を構成しない場合は、ゾーンのページ上のスクリプト コードは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067172)

  **既定値**: 無効にする

- **[Internet Explorer internet zone logon options]\(Internet Explorer のインターネット ゾーンのログオン オプション\)** :  
  このポリシー設定を使用すると、サインイン オプションの設定を管理できます。 このポリシー設定を有効にすると、次のサインイン オプションから選択できます。 HTTP 認証を無効にして、Common Internet File System (CIFS) プロトコル用にのみ guest アカウントを使用する場合は、[匿名ログオン] を選択してください。 ユーザーの ID とパスワードを照会するために、ユーザー名とパスワードの入力を求めます。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。 他のゾーンでユーザーの ID とパスワードを照会するには [イントラネット ゾーンでのみ自動ログオンを許可する] を選択してください。 ユーザーが照会された後に、これらの値は残りのセッションで警告なしに使用されます。 現在のユーザー名とパスワードで自動的にサインインし、Windows NT チャレンジ応答 (別名 NTLM 認証) を使用してログオンを試みます。 サーバーで Windows NT チャレンジ応答がサポートされている場合、サインインでは、ユーザーのログオン用のネットワーク ユーザー名とパスワードが使用されます。 サーバーで Windows NT チャレンジ応答がサポートされていない場合、ユーザーはユーザー名とパスワードを提供する必要があります。 このポリシー設定を無効にすると、サインインは [イントラネット ゾーンでのみ自動ログオンを許可する] に設定されます。 このポリシー設定を構成しない場合、サインインは [イントラネット ゾーンでのみ自動的にサインインする] に設定されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067194)

  **既定値**: プロンプト

- **[Internet Explorer の制限付きゾーンで VB スクリプトの実行を許可する]** :  
  このポリシー設定を使用すると、Internet Explorer 内の指定されたゾーンのページ上で VB スクリプトを実行できるかどうかを管理できます。 ドロップダウン ボックスで [有効にする] を選択すると、ユーザーによる手動操作を必要とすることなく、VB スクリプトを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ユーザーは VB スクリプトの実行を許可するかどうかをたずねられます。 ドロップダウン ボックスで [無効にする] を選択した場合、VB スクリプトは実行されません。 このポリシー設定を構成しなかった場合、または無効にした場合、VB スクリプトは実行されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067173)

  **既定値**: 無効にする

- **[Internet Explorer internet zone drag content from different domains across windows]\(Internet Explorer のインターネット ゾーンでウィンドウを超えて異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定により、移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067093)

  **既定値**: 無効

- **[Internet Explorer intranet zone initialize and script Active X controls not marked as safe]\(Internet Explorer のイントラネット ゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する\)** :  
  このポリシー設定を使用すると、安全であるとマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定では、安全なコントロールと安全ではないコントロールの両方を初期化およびスクリプト化します。[スクリプトを実行しても安全だとマークされている ActiveX コントロールのスクリプトの実行] オプションは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067175)

  **既定値**: 無効にする

- **[Internet Explorer download enclosures]\(Internet Explorer での添付ファイルのダウンロード\)** :  
  このポリシー設定は、添付ファイルをフィードからユーザーのコンピューターにダウンロードできないようにします。 このポリシー設定を有効にすると、フィードのプロパティ ページで、フィード同期エンジンが添付ファイルをダウンロードするように設定できません。 開発者は、フィードの API を使用してダウンロード設定を変更できません。 このポリシー設定を無効にするか、構成しない場合、フィードのプロパティ ページで、フィード同期エンジンが添付ファイルをダウンロードするように設定できます。 開発者は、フィードの API を使用してダウンロード設定を変更できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067245)

  **既定値**: 無効

- **[Internet Explorer restricted zone download unsigned Active X controls]\(Internet Explorer の制限付きゾーンで署名されていない Active X コントロールをダウンロードする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードすることを許可するかどうかを管理できます。 このようなコードは、特に信頼されていないゾーンから来た場合は、危険である可能性があります。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名されていないコントロールを実行することを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067177)

  **既定値**: 無効にする

- **[Internet Explorer internet zone drag content from different domains within windows]\(Internet Explorer のインターネット ゾーンでウィンドウ内の異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードすることを許可するかどうかを管理できます。 このようなコードは、特に信頼されていないゾーンから来た場合は、危険である可能性があります。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名されていないコントロールを実行することを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067095)

  **既定値**: 無効

- **[Internet Explorer プロセスで Active X インストールを制限する]** :  
  このポリシー設定は、Web ブラウザー コントロールをホストしているアプリケーションで、ActiveX コントロール インストールの確認ダイアログの自動表示のブロックを有効にします。 このポリシー設定を有効にすると、すべてのプロセスにおいて ActiveX コントロール インストールの確認ダイアログの自動表示は Web ブラウザー コントロールによってブロックされます。 このポリシー設定を無効にするか、または構成しない場合は、ActiveX コントロール インストールの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067250)

  **既定値**: 有効

- **Internet Explorer のインターネットゾーンのスクリプトレット**:  
  このポリシー設定を使用すると、ユーザーがスクリプトレットを実行できるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはスクリプトレットを実行できます。 このポリシー設定を無効にすると、ユーザーはスクリプトレットを実行できません。 このポリシー設定を構成しなかった場合、ユーザーはスクリプトレットを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067176)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone drag and drop or copy and paste files]\(Internet Explorer の制限付きゾーンでファイルのドラッグ アンド ドロップまたはコピーと貼り付けを行う\)** :  
  このポリシー設定を使用すると、ユーザーがゾーン内のソースからファイルのドラッグまたはコピーと貼り付けを行うことができるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、このゾーンからファイルをドラッグまたはコピーするかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーはこのゾーンからファイルをドラッグしたり、コピーして貼り付けたりできません。 このポリシー設定を構成しない場合は、このゾーンからファイルをドラッグまたはコピーするかどうかをユーザーにたずねます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067096)

  **既定値**: 無効にする

- **[Internet Explorer software when signature is invalid]\(Internet Explorer での署名が無効な場合のソフトウェア\)** :  
  このポリシー設定を使うと、署名が無効な場合でもユーザーがソフトウェア (ActiveX コントロールやファイル ダウンロードなど) をインストールまたは実行できるかどうかを管理できます。 署名が無効である場合、そのファイルをだれかが改ざんした可能性があります。 このポリシー設定を有効にすると、ユーザーが無効な署名を持つファイルをインストールまたは実行するときにダイアログが表示されます。 このポリシー設定を無効にすると、ユーザーは無効な署名を持つファイルを実行したりインストールしたりすることはできません。 このポリシーを構成しなかった場合は、ユーザーは無効な署名を持つファイルを実行またはインストールするかどうかを選択できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067201)

  **既定値**: 無効

- **[Internet Explorer restricted zone copy and paste via script]\(Internet Explorer の制限付きゾーンでのスクリプトによるコピーと貼り付け\)** :  
  このポリシー設定を使用すると、指定された領域でスクリプトがクリップボードの操作 (例: 切り取り、コピー、貼り付け) を実行できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトによりクリップボードの操作を実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、クリップボードの操作を実行するかどうかがユーザーにたずねられます。 このポリシー設定を無効にすると、スクリプトによってクリップボードの操作は実行されません。 このポリシー設定を構成しなかった場合、スクリプトはクリップボードの操作を実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067165)

  **既定値**: 無効にする

- **[Internet Explorer restricted zone drag content from different domains across windows]\(Internet Explorer の制限付きゾーンでウィンドウを超えて異なるドメインからコンテンツをドラッグする\)** :  
  このポリシー設定により、移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグするオプションを設定できます。 このポリシー設定を有効にして [有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。 このポリシー設定を有効にして [無効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウにある場合、あるドメインから別のドメインにコンテンツをドラッグできません。 この設定はユーザーが変更できません。 Internet Explorer 10 では、このポリシー設定を無効にする場合、または構成しない場合、[有効にする] をクリックすると、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグできません。 ユーザーは、[インターネット オプション] ダイアログでこの設定を変更できます。 Internet Explorer 9 以前のバージョンでは、このポリシーを無効にする場合、または構成しない場合は、ユーザーは移行元と移行先が異なるウィンドウの場合、あるドメインから別のドメインにコンテンツをドラッグすることができます。 この設定はユーザーが変更できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067166)

  **既定値**: 無効

- **[Internet Explorer のユーザーによるサイトの追加]** :  
  セキュリティ ゾーンからサイトを追加したり削除したりできないようにします。 セキュリティ ゾーンとは、同じセキュリティ レベルが設定されている Web サイトのグループのことです。 このポリシーを有効にすると、ユーザーは、セキュリティ ゾーンのサイト管理の設定画面を使用できなくなります (セキュリティ ゾーンのサイト管理の設定画面を表示するには、[インターネット オプション] ダイアログ ボックスで [セキュリティ] タブをクリックし、[サイト] ボタンをクリックします)。このポリシーを無効にするか、構成しない場合、ユーザーは [信頼済みサイト] および [制限付きサイト] ゾーンに対して Web サイトの追加と削除を行うことができます。また、[ローカル イントラネット] ゾーンの設定を変更できます。 このポリシーを有効にすると、ユーザーは、管理者が設定したセキュリティ ゾーンのサイト管理の設定を変更できなくなります。 注: インターフェイスから [セキュリティ] タブを削除する [[セキュリティ] ページの使用を許可しない] ポリシー (場所: \ユーザーの構成\管理用テンプレート\Windows コンポーネント\Internet Explorer\インターネット コントロール パネル) は、このポリシーより優先されます。 それが有効になっている場合、このポリシーは無視されます。 [セキュリティ ゾーン: コンピューターの設定のみ使用する] ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067167)

  **既定値**: 無効

- **[Internet Explorer のインターネット ゾーンのスクリプトによって開かれるウィンドウ]** :  
  このポリシー設定を使用すると、スクリプトによって起動されるポップアップ ウィンドウ、およびタイトルとステータス バーを持ったウィンドウの制限を管理できます。 このポリシー設定を有効にすると、Windows Restrictions セキュリティはこのゾーンでは適用されません。 セキュリティ ゾーンは、この機能で提供されるセキュリティの追加のレイヤーなしに実行されます。 このポリシー設定を無効にすると、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。 このポリシー設定を構成しないと、スクリプトによって起動されたポップアップ ウィンドウや、タイトルとステータス バーを含むウィンドウに含まれる、危害を及ぼす可能性のある動作は実行されません。 この Internet Explorer のセキュリティ機能は、プロセスの [スクリプト化されたウィンドウのセキュリティ制限] 機能コントロール設定で指定されたように、このゾーンでオンになります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067088)

  **既定値**: 無効

- **[Internet Explorer のセキュリティ ゾーンでコンピューターの設定のみ使用する]** :  
  セキュリティ ゾーンの設定情報をコンピューターに接続するすべてのユーザーに適用します。 セキュリティ ゾーンとは、同じセキュリティ レベルが設定されている Web サイトのグループのことです。 このポリシーを有効にすると、変更したセキュリティ ゾーンの設定はコンピューターに接続するすべてのユーザーに適用されます。 このポリシーを無効にしたり構成しない場合には、ユーザーは、独自のセキュリティ ゾーンを設定できます。 このポリシーを使用すると、セキュリティ ゾーンの設定が同じコンピューターに統一して適用され、ユーザーごとに設定を変えることはできません。 [セキュリティ ゾーン: ポリシーの変更を許可しない] ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067086)

  **既定値**: 有効

- **[Internet Explorer のロックダウンされたローカル コンピューター ゾーンの Java アクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067253)

  **既定値**: Java を無効にする

- **[Internet Explorer の制限付きゾーンで Active X コントロールに対してマルウェア対策を実行しない]** :  
  このポリシー設定では、ActiveX コントロールをページに読み込んでも安全かどうかを調べるために Internet Explorer がマルウェア対策プログラムを実行するかどうかを決定します。 このポリシー設定を有効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 このポリシー設定を無効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 このポリシー設定を構成しない場合、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 ユーザーは、Internet Explorer の [セキュリティ] 設定を使用して、この動作の有効と無効を切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067089)

  **既定値**: 無効

- **[Internet Explorer の制限付きゾーンで Authenticode 署名済みの .NET Framework 依存コンポーネントを実行する]** :  
  このポリシー設定を使用すると、Authenticode を使用して署名されている .NET Framework コンポーネントを Internet Explorer から実行できるかどうかを管理できます。 これらのコンポーネントには、object タグから参照された管理されたコントロール、リンクから参照された管理された実行可能ファイルなどが含まれます。 このポリシー設定を有効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行します。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名済みの管理されたコンポーネントを実行するかどうかを確認するメッセージが Internet Explorer によって表示されます。 このポリシー設定を無効にすると、Internet Explorer は署名済みの管理されたコンポーネントを実行しません。 このポリシー設定を構成しない場合は、Internet Explorer は署名済みの管理されたコンポーネントを実行します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067169)

  **既定値**: 無効にする

- **[Internet Explorer の制限付きゾーンにあるデータ ソースへのアクセス]** :  
  このポリシー設定を使用すると、Internet Explorer が Microsoft XML パーサー (MSXML) または ActiveX Data Objects (ADO) を使用して他のセキュリティ ゾーンからデータにアクセスできるかどうかを管理できます。 このポリシー設定を有効にすると、ユーザーはゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。 このポリシー設定を構成しないと、ゾーン内の他のサイトにあるデータに MSXML または ADO を使用してアクセスするゾーン内のページを読み込むことはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067161)

  **既定値**: 無効にする

- **[Internet Explorer internet zone don't run antimalware against ActiveX controls]\(Internet Explorer のインターネット ゾーンで Active X コントロールに対してマルウェア対策を実行しない\)** :  
  このポリシー設定では、ActiveX コントロールをページに読み込んでも安全かどうかを調べるために Internet Explorer がマルウェア対策プログラムを実行するかどうかを決定します。 このポリシー設定を有効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するためにマルウェア対策プログラムを実行しません。 このポリシー設定を無効にすると、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 このポリシー設定を構成しない場合、Internet Explorer は、ActiveX コントロールのインスタンスを安全に作成できるかどうかを確認するために常にマルウェア対策プログラムを実行します。 ユーザーは、Internet Explorer の [セキュリティ] 設定を使用して、この動作の有効と無効を切り替えることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067162)

  **既定値**: 無効

- **[Internet Explorer のインターネット ゾーンでのスクリプトによるコピーと貼り付け]** :  
  このポリシー設定を使用すると、指定された領域でスクリプトがクリップボードの操作 (例: 切り取り、コピー、貼り付け) を実行できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトによりクリップボードの操作を実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、クリップボードの操作を実行するかどうかがユーザーにたずねられます。 このポリシー設定を無効にすると、スクリプトによってクリップボードの操作は実行されません。 このポリシー設定を構成しなかった場合、スクリプトはクリップボードの操作を実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067084)

  **既定値**: 無効にする

- **[Internet Explorer での Activex インストーラー サービスの使用]** :  
  このポリシー設定では、ActiveX コントロールのインストール方法を指定できます。 このポリシー設定を有効にすると、ActiveX インストーラー サービスが存在し、ActiveX コントロールのインストールを許可するように構成されている場合のみ、ActiveX コントロールがインストールされます。 このポリシー設定を無効にするか、または構成しない場合、ActiveX コントロール (ユーザーごとのコントロールを含む) は標準インストール プロセスを使用してインストールされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067163)

  **既定値**: 有効

- **[Internet Explorer でゾーン昇格からの保護を処理する]** :  
  Internet Explorer は開く Web サイトのページに制限を付けます。 制限は Web ページの場所 (インターネット ゾーン、イントラネット ゾーン、ローカル コンピューター ゾーンなど) によって決まります。 たとえば、ローカル コンピューターにある Web ページはローカル コンピューター セキュリティ ゾーンにあり、最小限の制限を受けるため、ローカル コンピューター セキュリティ ゾーンは悪意のあるユーザーの一番のターゲットとなります。 このポリシー設定を有効にすると、すべてのプロセスにおいて、どのゾーンもゾーン昇格から保護されます。 このポリシー設定を無効にするか、または構成しない場合は、Internet Explorer のプロセス以外のプロセス、またはプロセスの一覧にあるプロセス以外のプロセスは、このような保護を受けません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067160)

  **既定値**: 有効

- **[Internet Explorer のインターネット ゾーンで署名なしの Active X コントロールをダウンロードする]** :  
  このポリシー設定を使用すると、ユーザーがゾーンから署名されていない ActiveX コントロールをダウンロードすることを許可するかどうかを管理できます。 このようなコードは、特に信頼されていないゾーンから来た場合は、危険である可能性があります。 このポリシー設定を有効にすると、ユーザーによる手動操作を必要とすることなく、署名されていないコントロールを実行できます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、署名されていないコントロールを実行することを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーは署名されていないコントロールを実行できません。 このポリシー設定を構成しない場合、ユーザーは署名されていないコントロールを実行できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067325)

  **既定値**: 無効にする

- **[Internet Explorer のインターネット ゾーンで異なるドメインとの間でウィンドウとフレームを移動する]** :  
  このポリシー設定を使用すると、異なるドメイン間でウィンドウとフレームを開くことや、アプリケーションにアクセスすることを管理できます。 このポリシー設定を有効にすると、ユーザーは他のドメインからウィンドウとフレームを開くことや、アプリケーションにアクセスすることができます。 ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、他のドメインからウィンドウとフレームを開いたりアプリケーションにアクセスしたりするかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、ユーザーは他のドメインからウィンドウとフレームを開けることや、アプリケーションにアクセスすることができません。 このポリシー設定を構成しない場合は、ユーザーは他のドメインからウィンドウとフレームを開くことや、アプリケーションにアクセスすることができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067083)

  **既定値**: 無効にする

- **[Internet Explorer のインターネット ゾーンでスクリプトを介してステータス バーを更新する]** :  
  このポリシー設定を使用すると、スクリプトを介してゾーン内のステータス バーを更新できるかどうかを管理できます。 このポリシー設定を有効にすると、スクリプトを介してステータス バーを更新できます。 このポリシー設定を無効にした場合、または構成しなかった場合、スクリプトを介してステータス バーを更新できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067087)

  **既定値**: 無効

- **[Internet Explorer の制限付きゾーンでサーバーへのファイルのアップロード時にローカル パスを含める]** :  
  このポリシー設定では、ユーザーが HTML フォーム経由でファイルをアップロードするときに、ローカル パス情報が送信されるかどうかが制御されます。 ローカル パス情報が送信された場合、意図せずに、一部の情報がサーバーに公開されることがあります。 たとえば、ユーザーのデスクトップから送信されたファイルに、パスの一部としてユーザー名が含まれている可能性があります。 このポリシー設定を有効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報が送信されます。 このポリシー設定を無効にすると、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報は削除されます。 このポリシー設定を構成しなかった場合、ユーザーが HTML フォーム経由でファイルをアップロードするときに、パス情報を送信するかどうかをユーザーが選択できます。 既定では、パス情報は送信されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067085)

  **既定値**: 無効

- **[Internet Explorer のプロセスでファイルのダウンロードを制限する]** :  
  このポリシー設定は、Web ブラウザー コントロールをホストしているアプリケーションで、ユーザーが開始していないファイル ダウンロードの確認ダイアログの自動表示をブロックすることを有効にします。 このポリシー設定を有効にすると、ユーザーによって開始されていないファイル ダウンロードの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされます。 このポリシー設定を無効にすると、ユーザーによって開始されていないファイル ダウンロードの確認ダイアログの自動表示はすべてのプロセスにおいて Web ブラウザー コントロールによってブロックされません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067164)

  **既定値**: 有効

- **[Internet Explorer の制限付きゾーンで承認済みドメインのみが Active X コントロールを使用できるようにする]** :  
  このポリシー設定では、ActiveX コントロールをインストールした Web サイト以外の Web サイトで ActiveX コントロールを実行する許可を求めるメッセージをユーザーに表示するかどうかを制御します。 このポリシー設定を有効にすると、このゾーン内の Web サイトで ActiveX コントロールが実行される前に、ユーザーにメッセージが表示されます。 ユーザーは、現在のサイトからのコントロールの実行を許可するか、すべてのサイトからのコントロールの実行を許可するかを選択できます。 このポリシー設定を無効にすると、ユーザーにはサイトごとの ActiveX 警告は表示されず、ActiveX コントロールはこのゾーン内のすべてのサイトから実行できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067233)

  **既定値**: 有効

- **[Internet Explorer の制限付きゾーンで安全であるとマークされていない Active X コントロールを初期化およびスクリプト化する]** :  
  このポリシー設定を使用すると、安全であるとマークされていない ActiveX コントロールを管理できます。 このポリシー設定を有効にすると、ActiveX コントロールがパラメーターを読み込んで実行され、また、信頼されていないデータまたはスクリプトに対するオブジェクトの安全性を設定することなくスクリプト化されます。 この設定は、安全でかつ管理されたゾーン以外では推奨しません。 この設定では、安全なコントロールと安全ではないコントロールの両方を初期化およびスクリプト化します。[スクリプトを実行しても安全だとマークされている ActiveX コントロールのスクリプトの実行] オプションは無視されます。 このポリシー設定を有効にして、ドロップダウン ボックスで [ダイアログを表示する] を選択した場合、コントロールにパラメーターを読み込んだりスクリプト化したりすることを許可するかどうかをユーザーにたずねます。 このポリシー設定を無効にすると、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。 このポリシー設定を構成しなかった場合、安全であるとマークできない ActiveX コントロールにパラメーターを読み込んだりスクリプト化したりすることはできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067097)

  **既定値**: 無効にする

- **[Internet Explorer のユーザーによるポリシーの変更]** :  
  セキュリティ ゾーンの設定を変更できないようにします。 セキュリティ ゾーンとは、同じセキュリティ レベルが設定されている Web サイトのグループのことです。 このポリシーを有効にすると、ユーザーは、インターネット オプションの [セキュリティ] タブで表示される [レベルのカスタマイズ] ボタンとセキュリティ レベルを設定するスライダーを使用できなくなります。 このポリシーを無効にするか、または構成しない場合は、セキュリティ ゾーンの設定を変更できます。 このポリシーを有効にすると、ユーザーは、管理者が設定したセキュリティ ゾーンの設定を変更できなくなります。 注: このポリシーよりも優先される [[セキュリティ] ページの使用を許可しない] ポリシー (場所: \ユーザーの構成\管理用テンプレート\Windows コンポーネント\Internet Explorer\インターネット コントロール パネル) を有効にすると、コントロール パネルのインターネット オプションから [セキュリティ] タブが削除され、 それが有効になっている場合、このポリシーは無視されます。 [セキュリティ ゾーン: コンピューターの設定のみ使用する] ポリシーも参照してください。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067155)

  **既定値**: 無効

- **[Internet Explorer の制限付きゾーンでの保護モード]** :  
  このポリシー設定を使用すると、保護モードを有効にできます。 保護モードを使用すると、Internet Explorer が書き込むことができるレジストリやファイル システム内の場所を制限することで、脆弱点を悪用した攻撃から Internet Explorer を保護できます。 このポリシー設定を有効にすると、保護モードが有効になります。 ユーザーは保護モードを無効にできません。 このポリシー設定を無効にすると、保護モードが無効になります。 ユーザーは保護モードを有効にできません。 このポリシー設定を構成しなかった場合、ユーザーは保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067080)

  **既定値**: 有効にする

- **[Internet Explorer のインターネット ゾーンでのユーザー データ永続化]** :  
  このポリシー設定を使用すると、ブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存された Web ページ内に直接入っている情報の保管を管理できます。 このポリシー設定を正しく構成すると、ユーザーが固定されたページに戻ったときに、ページの状態を復元できます。 このポリシー設定を有効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。 このポリシー設定を無効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。 このポリシー設定を構成しなかった場合、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067156)

  **既定値**: 無効

- **[Internet Explorer のインターネット ゾーンでの Web ブラウザー コントロールのスクリプト化]** :  
  このポリシー設定では、ページで、スクリプトを使用して埋め込みの WebBrowser コントロールを制御できるかどうかを決定します。 このポリシー設定を有効にすると、WebBrowser コントロールへのスクリプト アクセスが許可されます。 このポリシー設定を無効にすると、WebBrowser コントロールへのスクリプト アクセスは許可されません。 このポリシー設定を構成しなかった場合、ユーザーは WebBrowser コントロールへのスクリプト アクセスを有効または無効にできます。 既定では、WebBrowser コントロールへのスクリプト アクセスは、ローカル コンピューターおよびイントラネット ゾーン内でのみ許可されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067157)

  **既定値**: 無効

- **[Internet Explorer の制限付きゾーンでのユーザー データ永続化]** :  
  このポリシー設定を使用すると、ブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存された Web ページ内に直接入っている情報の保管を管理できます。 このポリシー設定を正しく構成すると、ユーザーが固定されたページに戻ったときに、ページの状態を復元できます。 このポリシー設定を有効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できます。 このポリシー設定を無効にすると、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。 このポリシー設定を構成しなかった場合、ユーザーはブラウザーの履歴、お気に入り、XML ストア、またはディスクに保存されている Web ページ内に直接、情報を保管できません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067081)

  **既定値**: 無効

- **[Internet Explorer のロックダウンされた信頼済みゾーンでの Java のアクセス許可]** :  
  このポリシー設定を使用すると、Java アプレットのアクセス許可を管理できます。 このポリシー設定を有効にすると、ドロップダウン ボックスからオプションを選択できます。 アクセス許可の設定を個々に制御するには [カスタム] を選択してください。 [安全性 - 低] を選択すると、アプレットはすべての操作を実行できます。 [安全性 - 中] を選択すると、アプレットはサンドボックス (メモリ内の領域で、その外側にはプログラムは呼び出しを実行できない) 内で実行されます。また、スクラッチ領域 (クライアント コンピューター内の安全でセキュリティで保護された記憶域) やユーザーによって制御されたファイル I/O などの機能が利用できます。 [安全性 - 高] を選択すると、サンドボックス内でアプレットが実行されます。 アプレットを実行しないようにするには、[Java の無効化] を選択してください。 このポリシー設定を無効にすると、Java アプレットは実行されません。 このポリシー設定を構成しなかった場合、Java アプレットは無効になります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067082)

  **既定値**: Java を無効にする

- **[Internet Explorer の拡張保護モード]** :  
  拡張保護モードでは、64 ビット バージョンの Windows で 64 ビット プロセスが使用され、悪意のある Web サイトに対する保護が強化されています。 Windows 8 以降が実行されているコンピューターでは、拡張保護モードによって、Internet Explorer が読み取り元に設定できる場所もレジストリとファイル システムに制限されています。 このポリシー設定を有効にすると、拡張保護モードが有効になります。 保護モードが有効になっているゾーンでは、拡張保護モードが使用されます。 拡張保護モードを無効にすることはできません。 このポリシー設定を無効にすると、拡張保護モードが無効になります。 保護モードが有効になっているゾーンでは、Windows Vista の Internet Explorer 7 で導入されたバージョンの保護モードが使用されます。 このポリシー設定を構成しない場合、ユーザーは、[インターネット オプション] ダイアログの [詳細設定] タブで拡張保護モードを有効または無効にできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067158)

  **既定値**: 有効

- **[Internet Explorer のスマート スクリーン警告のバイパス]** :  
  このポリシー設定では、ユーザーが SmartScreen フィルター機能からの警告をバイパスできるかどうかを決定します。 SmartScreen フィルター機能では、ダウンロードしたユーザー数が少ない実行可能ファイルについてユーザーに警告します。 このポリシー設定を有効にすると、ユーザーは SmartScreen フィルター機能の警告によってブロックされます。 このポリシー設定を無効にした場合、または構成しなかった場合、ユーザーは SmartScreen フィルター機能の警告をバイパスできます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067159)

  **既定値**: 無効

- **[Internet Explorer の制限付きゾーンのメタ更新]** :  
  このポリシー設定を使用すると、Web ページの作成者がブラウザーを別の Web ページにリダイレクトするために Meta Refresh 設定 (タグ) を使用している場合に、ユーザーのブラウザーを別の Web ページにリダイレクトするかどうかを管理できます。 このポリシー設定を有効にすると、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできます。 このポリシー設定を無効にすると、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできません。 このポリシー設定を構成しなかった場合、アクティブな Meta Refresh 設定を含むページを読み込むブラウザーを他の Web ページにリダイレクトできません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067154)

  **既定値**: 無効

## <a name="local-policies-security-options"></a>ローカル ポリシーのセキュリティ オプション

詳細については、Windows のドキュメントの「[Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions)」(ポリシー CSP - LocalPoliciesSecurityOptions) を参照してください。

- **[名前付きパイプと共有への匿名アクセスを制限する]** :  
  このセキュリティ設定を有効にすると、次の設定と一致する共有およびパイプへの匿名アクセスが制限されます: (1) 匿名でアクセスできる名前付きパイプ (2) 匿名でアクセスできる共有。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067212)

  **既定値**: はい

- **[NTLM SSP ベースのサーバー向け最小セッション セキュリティ]** :  
  このセキュリティ設定を使用すると、サーバーで 128 ビット暗号化および NTLMv2 セッション セキュリティのネゴシエーションが必要になるようにすることができます。 これらの値は、LAN Manager 認証レベルのセキュリティ設定値に依存します。 オプションは次のとおりです。NTLMv2 セッション セキュリティが必要: メッセージの整合性がネゴシエートされていない場合、接続は失敗します。 128 ビット暗号化が必要: 強力な暗号化 (128 ビット) がネゴシエートされない場合、接続は失敗します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067246)

  **既定値**: NTLM V2 および 128 ビットの暗号化が必要

- **スクリーン セーバーがアクティブになるまでのロック画面の非アクティブ時間 (分)** :  
  ログオン セッションの非アクティブ状態が Windows によって通知されます。また、非アクティブ状態の時間が非アクティブ状態の上限を超えるとスクリーン セーバーが実行され、セッションがロックされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067210)

  **既定値**: 15

- **常に通信にデジタル署名をクライアントに要求する**:  
  このセキュリティ設定では、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてに対して署名または暗号化を行う必要があるかどうかを決定します。 コンピューターがドメインに参加すると、コンピューター アカウントが作成されます。 それ以降、システムでは起動時に、そのコンピューター アカウントのパスワードを使用して、そのドメイン用のドメイン コントローラーとの間でセキュリティで保護されたチャネルが確立されます。 このセキュリティで保護されたチャネルは、NTLM パススルー認証や LSA SID/名前の参照などの操作を実行するために使用されます。 この設定では、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてが最低限のセキュリティ要件を満たす必要があるかどうかを決定します。 具体的には、ドメインのメンバーによって開始された、セキュリティで保護されたチャネルのトラフィックすべてに対して署名または暗号化を行う必要があるかどうかを決定します。 このポリシーを有効にすると、セキュリティで保護されたチャネルのトラフィックすべてに対する署名または暗号化がネゴシエートされるまで、セキュリティで保護されたチャネルは確立されません。 このポリシーを無効にすると、セキュリティで保護されたチャネルのトラフィックすべてに対する暗号化および署名は、ドメイン コントローラーとネゴシエートされます。この場合、署名と暗号化のレベルは、ドメイン コントローラーのバージョンと次の 2 つのポリシーの設定によって決まります: ドメイン メンバー: セキュリティで保護されたチャネルのデータをデジタル的に暗号化する (可能な場合) ドメイン メンバー: セキュリティで保護されたチャネルのデータをデジタル的に署名する (可能な場合)。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067187)

  **既定値**: はい

- **[認証レベル]** :  
  このセキュリティ設定では、ネットワーク ログオンに使用されるチャレンジ/レスポンス認証プロトコルが決定されます。 この選択は、以下に示すように、クライアントで使用する認証プロトコルのレベル、ネゴシエートされるセッション セキュリティのレベル、およびサーバーによって受け入れられる認証レベルに影響します:

  - "*LM と NTLM 応答を送信する*" - クライアントでは LM および NTLM 認証が使用され、NTLMv2 セッション セキュリティは使用されません。ドメイン コントローラーでは LM、NTLM、および NTLMv2 認証が受け入れられます。

  - *ネゴシエートされた場合は lm と ntlm-ntlmv2 を送信*する-クライアントが lm 認証と ntlm 認証を使用し、サーバーがサポートしている場合は ntlmv2 セッションセキュリティを使用します。 ドメインコントローラーは、LM 認証、NTLM 認証、および NTLMv2 認証を受け付けます。

  - "*NTLM 応答のみ送信する*" - クライアントでは NTLM 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティも使用されます。ドメイン コントローラーでは、LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*NTLMv2 応答のみ送信する*" - クライアントでは NTLMv2 認証のみが使用され、サーバーでサポートされている場合は NTLMv2 セッション セキュリティも使用されます。ドメイン コントローラーでは、LM、NTLM、および NTLMv2 認証が受け入れられます。

  - "*NTLMv2 応答のみ送信する。LM* を拒否する-クライアントは NTLMv2 認証のみを使用し、サーバーでサポートされている場合は NTLMv2 セッションセキュリティを使用します。 ドメインコントローラーは LM を拒否します (NTLM と NTLMv2 認証のみを受け入れます)。

  - "*NTLMv2 応答のみ送信する。LM と NTLM の* を拒否する-クライアントは NTLMv2 認証のみを使用し、サーバーでサポートされている場合は NTLMv2 セッションセキュリティを使用します。 ドメインコントローラーは、LM と NTLM を拒否します (NTLMv2 認証のみを受け入れます)。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067189)

  **既定値**: NTLMv2 応答のみ送信する。 LM と NTLM を拒否する

- **[暗号化されていないパスワードがクライアントからサード パーティの SMB サーバーに送信されるのを防ぐ]** :  
  このセキュリティ設定を有効にすると、サーバー メッセージ ブロック (SMB) リダイレクターは、認証時にパスワードの暗号化をサポートしていない Microsoft 以外の SMB サーバーにプレーンテキストのパスワードを送信することができます。 暗号化されていないパスワードを送信することには、セキュリティ上のリスクがあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067235)

  **既定値**: はい

- **[サーバーが常に通信にデジタル署名を行うことを要求する]** :  
  このセキュリティ設定では、SMB クライアントによって SMB パケットの署名がネゴシエートされるかどうかが決定されます。 サーバー メッセージ ブロック (SMB) プロトコルは、Microsoft ファイルおよびプリンターの共有の基礎、さらにはリモート Windows 管理などのネットワーク操作の基礎となります。 転送中に SMB パケットを変更する中間者攻撃を防ぐために、SMB プロトコルでは SMB パケットのデジタル署名がサポートされています。 このポリシー設定では、SMB クライアント コンポーネントが SMB サーバーに接続するときに、その SMB クライアント コンポーネントによって SMB パケットの署名がネゴシエートされるかどうかが決定されます。 この設定を有効にすると、セッションのセットアップ時に SMB パケットの署名を実行するよう Microsoft ネットワーク クライアントからサーバーに要求が出されます。 サーバーでパケットの署名が有効になっている場合、パケットの署名がネゴシエートされます。 このポリシーを無効にすると、SMB クライアントによって SMB パケットの署名がネゴシエートされることはありません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067319)

  **既定値**: はい

- **[管理者に対する昇格時のプロンプトの動作]** :  
  このポリシー設定では、管理者に対する昇格時のプロンプトの動作が制御されます。 オプションは次のとおりです。

  - "*プロンプトを表示せずに昇格する*" - 昇格を必要とする操作を、同意または資格情報の必要なしに実行することを権限アカウントに許可します。 注: このオプションは非常に制限された環境内でのみ使用します。

  - "*セキュリティで保護されたデスクトップで資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で特権を持つユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*セキュリティで保護されたデスクトップで同意を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーは管理者のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*同意を要求する*" - 操作で特権の昇格が必要になると、ユーザーは許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  - "*非 Windows バイナリに対して同意を要求する*" - Microsoft 以外のアプリケーションの操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で許可または拒否のいずれかを選択するように求められます。 ユーザーが許可を選択すると、ユーザーが利用できる最も高い特権で操作が続行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067215)

  **既定値**: セキュリティで保護されたデスクトップで同意を要求する

- **[Minimum session security for NTLM SSP based clients]\(NTLM SSP ベースのクライアント向け最小セッション セキュリティ\)** :  
  このセキュリティ設定を使用すると、クライアントで 128 ビット暗号化および NTLMv2 セッション セキュリティのネゴシエーションが必要になるようにすることができます。 これらの値は、LAN Manager 認証レベルのセキュリティ設定値に依存します。 オプションは次のとおりです。

  - "*NTLMv2 セッション セキュリティが必要*" - NTLMv2 プロトコルがネゴシエートされていない場合、接続は失敗します。

  - "*128 ビット暗号化が必要*" - 強力な暗号化 (128 ビット) がネゴシエートされない場合、接続は失敗します。

  - *NTLMv2 および 128 ビットの暗号化が必要*。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067324)

  **既定値**: NTLM V2 128 暗号化が要求

- **スマート カードを取り外したときの動作**:  
  このセキュリティ設定では、ログオンしているユーザーのスマート カードがスマート カード リーダーから取り出されたときの動作を決定します。 オプションは次のとおりです。

  - *操作の必要なし*。

  - *ワークステーションをロックする* - スマート カードが取り出されたときにワークステーションはロックされます。これにより、ユーザーはスマート カードを持って場所を離れ、なおかつ、保護されたセッションを維持できます。

  - "*ログオフを強制する*" - スマート カードが取り出されると、ユーザーは自動的にログオフされます。

  - "*リモート デスクトップ セッションを切断する*" - スマート カードを取り出すと、ユーザーをログオフさせずにセッションを切断します。 このため、ユーザーは後でスマート カードを挿入し、セッションを再開することも、スマート カード リーダーを装備した別のコンピューターにスマート カードを挿入し、セッションを再開することもできます。もう一度ログオンする必要はありません。 セッションがローカルの場合、このポリシーの機能は [ワークステーションをロックする] と同じになります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067331)

  **既定値**: ワークステーションをロックする

- **[SAM アカウントと共有の匿名の列挙をブロックする]** :  
  このセキュリティ設定では、SAM アカウントと共有の匿名の列挙を許可するかどうかが決定されます。 Windows では匿名ユーザーがドメイン アカウントとネットワーク共有の名前の列挙など、特定の操作を行うことを許可しています。 これは、たとえば管理者が、相互信頼関係のない信頼される側のドメイン内のユーザーにアクセス許可を付与するのに便利です。 SAM アカウントおよび共有の匿名の列挙を許可しない場合は、このポリシーを "*はい*" に設定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067191)

  **既定値**: はい

- **[空のパスワードを使用したリモート ログオンをブロックする]** :  
  このセキュリティ設定では、パスワードで保護されていないローカル アカウントを使用して物理的なコンピューター コンソール以外の場所からログオンできるようにするかどうかが決定されます。 有効にすると、パスワードで保護されていないローカル アカウントには、そのコンピューターのキーボードを使用してログオンする必要があります。

  *警告*: 物理的に安全な場所に置かれていないコンピューターでは、すべてのローカル ユーザー アカウントに対して常に強力なパスワード ポリシーが適用される必要があります。 そうしないと、パスワードのないユーザー アカウントを使用し、コンピューターに物理的にアクセスできるすべてのユーザーがコンピューターにログオンできてしまいます。 これは、持ち運びができるコンピューターの場合に特に重要です。

  Everyone グループにこのセキュリティ ポリシーを適用すると、すべてのユーザーがリモート デスクトップ サービスを使用してログオンできなくなります。 ドメイン アカウントを使用するログオンにはこの設定は影響しません。 リモートからの対話型ログオンを使用するアプリケーションでは、この設定を回避できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067219)

  **既定値**: はい

- **[Standard user elevation prompt behavior]\(標準ユーザーに対する昇格時のプロンプトの動作\)** :  
  このポリシー設定では、標準ユーザーに対する昇格時のプロンプトの動作を制御します。

  - "*昇格要求を自動的に拒否する*" - 操作で特権の昇格が必要な場合、構成可能なアクセス拒否エラー メッセージが表示されます。 デスクトップの実行を標準ユーザーが行う企業では、ヘルプ デスクへの問い合わせを減らすためにこの設定が選択される場合があります。

  - "*セキュリティで保護されたデスクトップで資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーはセキュリティで保護されたデスクトップ上で別のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*資格情報を要求する*" - 操作で特権の昇格が必要になると、ユーザーは管理者のユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067183)

  **既定値**: 昇格要求を自動的に拒否する

- **[Require admin approval mode for administrators]\(管理者に管理者承認モードを要求する\)** :  
  このポリシー設定は、コンピューターのすべてのユーザー アカウント制御 (UAC) ポリシー設定の動作を制御します。 このポリシー設定を変更した場合、コンピューターを再起動する必要があります。 オプションは次のとおりです。

  - "*未構成*" - 管理者承認モードと関連するすべての UAC ポリシー設定が無効になります。 注: このポリシー設定を無効にすると、オペレーティング システムのセキュリティが全体的に低下したという通知が Security Center からあります。

  - "*はい*" - 管理者承認モードが有効になります。 組み込まれている管理者アカウントや管理者グループのその他のすべてのユーザーが管理者承認モードで実行することを許可するには、このポリシーを有効にし、関連する UAC ポリシー設定を正しく設定する必要があります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067184)

  **既定値**: はい

- **[Prevent anonymous enumeration of SAM accounts]\(SAM アカウントの匿名の列挙を防ぐ\)** :  
  このセキュリティ設定は、コンピューターに対する匿名接続にどのようなアクセス許可を追加付与するかを決定します。 Windows では匿名ユーザーがドメイン アカウントとネットワーク共有の名前の列挙など、特定の操作を行うことを許可しています。 これは、たとえば管理者が、相互信頼関係のない信頼される側のドメイン内のユーザーにアクセス許可を付与するのに便利です。 このセキュリティ オプションでは、次のような追加の制限が匿名接続に課せられます。

  - "*はい*" - SAM アカウントの列挙を許可しません。 このオプションでは、リソースに対するセキュリティのアクセス許可の Everyone を認証されたユーザーに置き換えます。

  - "*未構成*" - 追加の制限はありません。 既定のアクセス許可が使用されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067318)

  **既定値**: はい

- **[Allow remote calls to security accounts manager]\(セキュリティ アカウント マネージャーへのリモート呼び出しを許可する\)** :  
  このポリシー設定では、SAM へのリモート rpc 接続を制限することができます。 これを選択しない場合、既定のセキュリティ記述子が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067209)

  **既定値**: *O:BAG:BAD:(A;;RC;;;BA)*

- **[Use admin approval mode]\(管理者承認モードを使用する)** :  
  このポリシー設定は、組み込みの管理者アカウントの管理者承認モードの動作を制御します。 オプションは次のとおりです。

  - "*はい*" - あらかじめ登録された Administrator アカウントでは、管理者承認モードが使用されます。 既定では、特権の昇格が必要な操作では、ユーザーにその操作の承認が求められます。

  - "*未構成*" - あらかじめ登録された Administrator アカウントでは、すべてのアプリケーションが完全な管理特権で実行されます。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067186)

  **既定値**: はい
  
- **[Allow UI access applications for secure locations ]\(セキュリティで保護された場所に対して UI アクセス アプリケーションを許可する\)** :  
  このポリシー設定は、標準ユーザーに対して昇格がプロンプトされたときにセキュリティで保護されたデスクトップを、ユーザー インターフェイス アクセシビリティ (UIAccess または UIA) プログラムが自動的に無効にできるかどうかを制御します。

  - "*はい*" - Windows リモート アシスタンスなどの UIA プログラムは、昇格時のプロンプトに対してセキュリティで保護されたデスクトップを自動的に無効にします。 "ユーザー アカウント コントロールを無効にしない場合: 昇格のプロンプト時にセキュリティで保護されたデスクトップに切り替える" ポリシー設定を無効にしない場合、セキュリティで保護されたデスクトップではなく、対話ユーザーのデスクトップにプロンプトが表示されます。

  - "*未構成*" - セキュリティで保護されたデスクトップを無効にするには、対話型のデスクトップのユーザーが無効にするか、"ユーザー アカウント制御: 昇格のプロンプト時にセキュリティで保護されたデスクトップに切り替える" ポリシー設定を無効にする必要があります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067185)

  **既定値**: はい

- **[アプリケーションのインストールを検出し、昇格をプロンプトする]** :  
  このポリシー設定は、コンピューターへのアプリケーションのインストールの検出動作を制御します。 オプションは次のとおりです。

  - "*有効*" - 特権の昇格を必要とするアプリケーション インストール パッケージが検出されると、ユーザーは管理ユーザー名とパスワードを入力するように求められます。 ユーザーが有効な資格情報を入力すると、適用可能な特権で操作が続行されます。

  - "*無効*" - アプリケーション インストール パッケージは検出されず、昇格は求められません。 グループ ポリシー ソフトウェア インストールや Systems Management Server (SMS) などの委任されたインストール技術を活用している、標準ユーザー デスクトップを実行する企業では、この機能を無効にします。 この場合、インストーラーの検出は不要です。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067208)

  **既定値**: はい

- **[Prevent storing LAN manager hash value on next password change]\(次のパスワードの変更で LAN Manager のハッシュ値を保存しない\)** :  
  このセキュリティ設定は、次のパスワードの変更で、新しいパスワードの LAN Manager (LM) のハッシュ値を保存するかどうかを決定します。 LM ハッシュは、暗号化強度の高い Windows NT ハッシュと比べて比較的弱く、攻撃されやすいです。 LM ハッシュはセキュリティ データベースのローカル コンピューターに保存されるので、セキュリティ データベースが攻撃された場合、パスワードが漏えいすることがあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067213)

  **既定値**: はい

- **[ファイルおよびレジストリの書き込みエラーをユーザーごとの場所に仮想化する]** :  
  このポリシー設定は、アプリケーションの書き込みエラーを、定義されているレジストリおよびファイル システムの場所にリダイレクトするかどうかを制御します。 このポリシー設定は、管理者として実行されるアプリケーションが、実行時のアプリケーション データを *%ProgramFiles%* 、 *%Windir%* 、 *%Windir%\system32*、または *HKLM\Software* に書き込むよう緩和します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067321)

  **既定値**: はい

## <a name="ms-security-guide"></a>MS Security Guide (MS セキュリティ ガイド)

詳細については、Windows の「[Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide)」(ポリシー CSP - MSSecurityGuide) を参照してください。

- **[Apply UAC restrictions to local accounts on network logon]\(ネットワーク ログオン時にローカル アカウントに UAC 制限を適用する\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067188)

  **既定値**: 有効

- **[SMB v1 client driver start configuration]\(SMB v1 クライアント ドライバーの開始時の構成\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067214)

  **既定値**: 無効なドライバー

- **[SMB v1 server]\(SMB v1 サーバー\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067190)

  **既定値**: 無効

- **[Digest authentication]\(ダイジェスト認証\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067193)

  **既定値**: 無効

- **[Structured exception handling overwrite protection]\(構造化例外処理の上書き保護)\** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067217)

  **既定値**: 有効

## <a name="mss-legacy"></a>MSS Legacy (MSS レガシ)

詳細については、Windows の「[Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy)」(ポリシー CSP - MSSLegacy) を参照してください。

- **[Network IP source routing protection level]\(ネットワーク IP ソース ルーティングの保護レベル\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067220)

  **既定値**: 最高の保護  

- **[Network ignore NetBIOS name release requests except from WINS servers]\(ネットワークが WINS サーバーからのを除く NetBIOS 名のリリース要求を無視する\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067218)

  **既定値**: 有効

- **[Network IPv6 source routing protection level]\(ネットワーク IPv6 ソース ルーティングの保護レベル\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067216)

  **既定値**: 最高の保護

- **[Network ICMP redirects override OSPF generated]\(ネットワーク ICMP が生成されたオーバーライド OSPF をリダイレクトする\)** :  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067326)

  **既定値**: 無効

## <a name="power"></a>電源

詳細については、Windows の「[Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power)」(ポリシー CSP - Power) を参照してください。

- **[Require password on wake while plugged in]\(電源接続中のスリープ解除時にパスワードを要求する\)** :  
  このポリシー設定では、システムのスリープ状態を解除するときに、ユーザーにパスワードを要求するかどうかを指定します。 このポリシー設定を有効にした場合、または構成しなかった場合、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067221)

  **既定値**: 有効

- **[Standby states when sleeping while on battery]\(バッテリ使用中のスリープ状態時のスタンバイ状態\)** :  
  このポリシー設定では、コンピューターをスリープ状態にするときに Windows でスタンバイ状態を使用できるかどうかを管理します。 このポリシー設定を有効にしたり、構成しない場合、Windows はスタンバイ状態を使用してコンピューターをスリープ状態にします。 このポリシー設定を無効にすると、スタンバイ状態 (S1-S3) は許可されなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067195)

  **既定値**: 無効

- **[Standby states when sleeping while plugged in]\(電源接続中のスリープ状態時のスタンバイ状態\)** :  
  このポリシー設定では、コンピューターをスリープ状態にするときに Windows でスタンバイ状態を使用できるかどうかを管理します。 このポリシー設定を有効にしたり、構成しない場合、Windows はスタンバイ状態を使用してコンピューターをスリープ状態にします。 このポリシー設定を無効にすると、スタンバイ状態 (S1-S3) は許可されなくなります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067196)

  **既定値**: 無効

- **[Require password on wake while on battery]\(バッテリ使用中のスリープ解除時にパスワードを要求する\)** :  
  このポリシー設定では、システムのスリープ状態を解除するときに、ユーザーにパスワードを要求するかどうかを指定します。 このポリシー設定を有効にした場合、または構成しなかった場合、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーはシステムのスリープ状態を解除するときにパスワードを要求されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067322)

  **既定値**: 有効

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="remote-assistance"></a>リモート アシスタンス

詳細については、Windows ドキュメントの[ポリシー CSP - RemoteAssistance](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteassistance#remoteassistance-solicitedremoteassistance) に関するページをご覧ください。

- **リモートアシスタンスの要請**:  
  このポリシー設定を使用すると、このコンピューター上で要請されたリモート アシスタンスを有効または無効に設定することができます。
  
  - "*このポリシー設定を有効にすると*"、このコンピューターのユーザーは電子メールやファイル転送を使用して他のユーザーに支援を求めることができます。 また、ユーザーはインスタント メッセージング プログラムを使用してこのコンピューターへの接続を許可することができ、管理者は追加のリモート アシスタンスの設定を構成することができます。

  - "*このポリシー設定を無効にすると*"、このコンピューターのユーザーは電子メールやファイル転送を使用して他のユーザーに支援を求めることができません。 また、ユーザーは、インスタント メッセージング プログラムを使用してこのコンピューターへの接続を許可することができなくなります。

  - "*このポリシー設定を構成しない場合*" は、コントロール パネルの [システムのプロパティ] からユーザーが自分で、要請されたリモート アシスタンスを有効または無効に設定することができます。 ユーザーは、リモート アシスタンスの設定を構成することもできます。

  このポリシー設定を有効にすると、ヘルパーによるリモート アシスタンスの提供に、次の 2 つの方法が使用できます。[ヘルパーにコンピューターの閲覧のみを許可する] と [ヘルパーにコンピューターのリモート制御を許可する] です。 [チケットの最大時間] ポリシー設定は、電子メールまたはファイル転送を使用して作成されたリモートアシスタンスの招待が開いたままになる時間の制限を設定します。 [電子メールの招待の送信方法を選択する] 設定によって、リモート アシスタンスの招待の送信に使用する電子メール規格を指定できます。 お使いの電子メールのプログラムによって、*Mailto* 規格 (招待を受信する側がインターネット リンク経由で接続) か、または SMAPI (簡易 MAPI) 規格 (招待を電子メールのメッセージに添付) を使用できます。 Windows Vista では SMAPI だけがサポートされている方法であるため、このポリシー設定は使用できません。 このポリシー設定を有効にした場合は、リモート アシスタンスが通信できるように、適切なファイアウォールの例外を有効にする必要もあります。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067198)

  **既定**: リモートアシスタンスを無効にする

  *リモートアシスタンスを有効*にするように設定した場合は、次の追加設定を構成します。

  - **リモートアシスタンスの要請アクセス許可**:  
    **既定値**: ビュー

  - **[チケットの最大有効時間値]** :  
    **既定値**: *[未構成]*

  - **[チケットの最大有効期間]** :  
    **既定値**: Minutes

  - **電子メールの招待方法**:  
    **既定**: 簡易 MAPI

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="remote-desktop-services"></a>リモート デスクトップ サービス

詳細については、Windows ドキュメントの「[Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices)」(ポリシー CSP - RemoteDesktopServices) を参照してください。

- **[Block password saving]\(パスワードの保存をブロックする\)** :  
  リモート デスクトップ接続からこのコンピューター上でパスワードを保存できるようにするかどうかを制御します。 この設定を有効にすると、リモート デスクトップ接続のパスワードを保存するためのチェック ボックスが使用できなくなり、以降、ユーザーはパスワードを保存できなくなります。 ユーザーがリモート デスクトップ接続で RDP ファイルを開いて設定を保存した場合、RDP ファイルに以前から存在していたパスワードはすべて削除されます。 この設定を無効または未構成にする場合、ユーザーはリモート デスクトップ接続でパスワードを保存できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067301)

   **既定値**: 有効

- **[Secure RPC communication]\(セキュリティで保護された RPC 通信\)** :  
  リモート デスクトップ セッション ホスト サーバーに、クライアントすべてとのセキュリティで保護された RPC 通信が必要か、またはセキュリティで保護されていない通信を許可するかどうかを指定します。 この設定を使って、認証されて暗号化された要求のみを許可することで、クライアントとの RPC 通信のセキュリティを強化できます。 状態が有効に設定されている場合、リモート デスクトップ サービスは、セキュリティで保護された要求をサポートする RPC クライアントからの要求を受け入れて、信用されていないクライアントとのセキュリティで保護されていない通信を許可しません。 状態が無効に設定されている場合は、リモート デスクトップ サービスは RPC トラフィックすべてのセキュリティを常に要求します。 しかし、要求に応答しない RPC クライアントにはセキュリティで保護されていない通信が許可されます。 状態が未構成に設定されている場合は、セキュリティで保護されていない通信は許可されます。 注: RPC インターフェイスがリモート デスクトップ サービスの管理または構成に使用されています。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067248)

  **既定値**: 有効

- **[Block drive redirection]\(ドライブのリダイレクトをブロックする\)** :  
  このポリシー設定は、リモート デスクトップ サービス セッションで、クライアント ドライブのマッピングをしないようにするかどうかを指定します (ドライブ リダイレクト)。 既定では、RD セッション ホスト サーバーは接続時に自動的にクライアント ドライブをマップします。 マップされたドライブは、エクスプローラーまたは [コンピューター] のセッション フォルダー ツリーに、 *\<コンピューター名>* の *\<ドライブ文字>* という形式で表示されます。 このポリシー設定を使ってこの動作をオーバーライドできます。 このポリシー設定を有効にすると、クライアント ドライブのリダイレクトはリモート デスクトップ サービス セッションでは許可されません。また、クリップボードでのファイル コピーのリダイレクトは、Windows Server 2003、Windows 8、および Windows XP を実行しているコンピューターでは許可されません。 このポリシー設定を無効にすると、クライアント ドライブのリダイレクトは常に許可されます。 また、クリップボードのリダイレクトを許可すると、クリップボードでのファイル コピーのリダイレクトは常に許可されます。 このポリシー設定を構成しなかった場合、クライアント ドライブのリダイレクトおよびクリップボードでのファイル コピーのリダイレクトはグループ ポリシー レベルでは指定されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067197)

  **既定値**: 有効

- **[Prompt for password upon connection]\(接続するときにパスワードを要求する\)** :  
  このポリシー設定は、接続時にクライアントが、リモート デスクトップ サービスによって常にパスワードの入力を要求されるかどうかを指定します。 リモート デスクトップ サービスにログオンしているユーザーが、リモート デスクトップ接続のクライアントでパスワードを既に提供していても、この設定を使ってパスワードの入力を強制できます。 既定では、リモート デスクトップ サービスによりユーザーはリモート デスクトップ接続のクライアントにパスワードを入力して自動的にログオンできます。 このポリシー設定を有効にすると、ユーザーはリモート デスクトップ接続のクライアントでパスワードを供給しても、リモート デスクトップ サービスに自動的にログオンできません。 ユーザーは、ログオンするためにパスワードを要求されます。 このポリシー設定を無効にすると、ユーザーは常にリモート デスクトップ接続のクライアントでパスワードを供給することでリモート デスクトップ サービスに自動的にログオンできます。 このポリシー設定を構成しなかった場合、自動ログオンはグループ ポリシー レベルでは指定されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067328)

  **既定値**: 有効

- **[Remote desktop services client connection encryption level]\(リモート デスクトップ サービス クライアント接続の暗号化レベル\)** :  
  リモート デスクトップ プロトコル (RDP) 接続時に、クライアント コンピューターと RD セッション ホスト サーバー間の通信をセキュリティで保護するために、特定の暗号化レベルの使用を必要とするかどうかを指定します。 このポリシーは、ネイティブの RDP 暗号化を使用しているときにのみ適用されます。 ただし (SSL 暗号化と異なり) ネイティブ RDP 暗号化は推奨されません。 SSL 暗号化にこのポリシーは適用されません。 このポリシー設定を有効にした場合、リモート接続時のクライアントと RD セッション ホスト サーバー間のすべての通信で、この設定で指定された暗号化方法を使用する必要があります。 既定では、暗号化レベルは [高] に設定されています。 次の暗号化方法を利用できます。

  - "*高*" - [高] 設定では、強力な 128 ビット暗号化を使ってクライアントとサーバー間で送受信されるデータを暗号化します。 この暗号化レベルは、128 ビット クライアント (リモート デスクトップ接続クライアントなど) のみが含まれる環境で使用します。 この暗号化レベルをサポートしていないクライアントは RD セッション ホスト サーバーに接続できません。

  - "*クライアント互換*" - [クライアント互換] 設定では、クライアントとサーバーの間で送信されるすべてのデータは、クライアントでサポートされている最高のキー強度で暗号化されます。 この暗号化レベルは、128 ビット暗号化をサポートしていないクライアントが含まれる環境で使用します。

  - "*低*" - [低] 設定では、56 ビット暗号化を使ってクライアントからサーバーへ送信されるデータのみを暗号化します。  
  
  この設定を無効にするか、または構成しない場合は、RD セッション ホスト サーバーへのリモート接続に使用される暗号化レベルは、グループ ポリシーを通じて強制されません。 重要 FIPS 準拠は、システム暗号化を通じて構成できます。 グループ ポリシーの [暗号化、ハッシュ、署名のための FIPS 準拠アルゴリズムを使う] 設定 (場所: "コンピューターの構成\Windows の設定\セキュリティの設定\ローカル ポリシー\セキュリティ オプション")。[FIPS 準拠] 設定では、Microsoft 暗号化モジュールを使用して、Federal Information Processing Standard (FIPS) 140 暗号化アルゴリズムによって、クライアントとサーバー間で送受信されるデータを暗号化および暗号化解除します。 この暗号化レベルは、クライアントと RD セッション ホスト サーバー間の通信で最高レベルの暗号化が必要な場合に使用します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067222)

  **既定値**: 高

## <a name="remote-management"></a>リモート管理

詳細については、Windows ドキュメントの「[Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement)」(ポリシー CSP - RemoteManagement) を参照してください。

- **[Block storing run as credentials]\(実行アカウントの資格情報の保存をブロックする\)** :  
  クライアントの基本認証。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067300)

  **既定値**: 有効

- **[基本認証]** :  
  このポリシー設定を使用して、Windows リモート管理 (WinRM) サービスでリモート クライアントからの基本認証を受け付けるかどうかを管理できます。 このポリシー設定を有効にすると、WinRM サービスはリモート クライアントからの基本認証を受け付けます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM サービスはリモート クライアントからの基本認証を受け付けません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067223)

  **既定値**: 無効

- **[Block client digest authentication]\(クライアントのダイジェスト認証をブロックする\)** :  
  このポリシー設定を使用して、Windows リモート管理 (WinRM) クライアントでダイジェスト認証を使用するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントでダイジェスト認証は使用されません。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントでダイジェスト認証が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067302)

  **既定値**: 有効

- **[暗号化されていないトラフィック]** :  
  このポリシー設定を使用して、Windows リモート管理 (WinRM) サービスで、暗号化されていないメッセージをネットワーク経由で送受信するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントは、暗号化されていないメッセージをネットワーク経由で送受信します。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントは、暗号化されたメッセージのみをネットワーク経由で送受信します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067226)

  **既定値**: 無効

- **[クライアントが暗号化されていないトラフィック]** :  
  このポリシー設定を使用して、Windows リモート管理 (WinRM) クライアントで、暗号化されていないメッセージをネットワーク経由で送受信するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントは、暗号化されていないメッセージをネットワーク経由で送受信します。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントは、暗号化されたメッセージのみをネットワーク経由で送受信します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067304)

  **既定値**: 無効

- **[クライアントの基本認証]** :  
  このポリシー設定を使用して、Windows リモート管理 (WinRM) クライアントで基本認証を使用するかどうかを管理できます。 このポリシー設定を有効にすると、WinRM クライアントで基本認証が使用されます。 WinRM が HTTP トランスポートを使用するように構成されている場合は、ユーザー名とパスワードがクリア テキストとしてネットワーク経由で送信されます。 このポリシー設定を無効にした場合、または構成しなかった場合は、WinRM クライアントで基本認証は使用されません。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067252)

  **既定値**: 無効

## <a name="remote-procedure-call"></a>リモート プロシージャ コール

詳細については、Windows ドキュメントの「[Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall)」(ポリシー CSP - RemoteProcedureCall) を参照してください。

- **[RPC unauthenticated client options]\(RPC の認証されていないクライアント オプション\)** :  
  このポリシー設定は、RPC サーバーに接続する認証されていない RPC クライアントを RPC サーバー ランタイムが処理する方法を制御します。 このポリシー設定は、すべての RPC アプリケーションに影響します。 ドメイン環境では、このポリシー設定はグループ ポリシーの処理自体を含む広範な機能に影響する可能性があるため、注意して使用する必要があります。 このポリシー設定の変更を元に戻す場合、影響するコンピューターごとに手動での操作が必要になることがあります。 このポリシー設定をドメインコントローラーに適用しないでください。 このポリシー設定を無効にすると、RPC サーバー ランタイムは Windows クライアントでは [認証済み] の値を使用し、このポリシー設定をサポートする Windows Server バージョンでは [なし] の値を使用します。 このポリシー設定を構成しない場合、設定は無効のままになります。 RPC サーバー ランタイムは、Windows クライアントでは [認証済み] の値の使用が、このポリシー設定をサポートする Server SKU では [なし] の値の使用が有効にされた場合と同じように動作します。 このポリシー設定を有効にすると、コンピューター上の RPC サーバーに接続する、認証されていない RPC クライアントを制限するよう RPC サーバー ランタイムに指示します。 サーバーとの通信時に名前付きパイプを使用している場合、または RPC セキュリティを使用している場合に、クライアントは認証済みとして認識されます。 このポリシー設定で選択された値によっては、未認証のクライアントがアクセスできるよう明示的に要求した RPC インターフェイスは、この制限から除外される場合もあります。

  - *[なし]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、すべての RPC クライアントの接続を許可します。

  - *[認証済み]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、認証済み (前の定義による) の RPC クライアントのみの接続を許可します。 除外を要求したインターフェイスは除外されます。

  - *[認証済み (例外なし)]* では、このポリシー設定が適用されるコンピューター上で実行されている RPC サーバーへの、認証済み (前の定義による) の RPC クライアントのみの接続を許可します。 例外は許可されません。 注: このポリシー設定は、システムが再起動されるまで適用されません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067225)

  **既定値**: 認証済み

## <a name="search"></a>検索

詳細については、Windows ドキュメントの「[Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search)」(ポリシー CSP - Search) を参照してください。

- **[Disable indexing encrypted items]\(暗号化されたアイテムのインデックス作成を無効にする\)** :  
  アイテムのインデックス作成を許可または禁止します。 これは Windows Search Indexer 用のスイッチです。Windows 情報保護 (WIP) で保護されたファイルなど、暗号化されたアイテムにインデックスを付けるかどうかを制御します。 このポリシーが有効な場合、WIP で保護されたアイテムにインデックスが付けられ、それらのメタデータは暗号化されていない場所に保存されます。 メタデータには、ファイル パスや変更日などがあります。 このポリシーが無効な場合、WIP で保護されたアイテムにはインデックスが付けられず、Cortana またはエクスプローラーの結果に表示されません。 また、デバイスに WIP で保護されたメディア ファイルが多数ある場合は、写真や Groove アプリのパフォーマンスにも影響が出る可能性があります。  
  [詳細情報]( https://go.microsoft.com/fwlink/?linkid=2067303)

  **既定値**: はい

## <a name="smart-screen"></a>スマート スクリーン

詳細については、Windows ドキュメントの「[Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen)」 (ポリシー CSP - SmartScreen) を参照してください。

- **[Block execution of unverified files]\(確認されていないファイルの実行をブロックする\)** :  
  確認されていないファイルをユーザーが実行しないようにします。

  - "*未構成*" - 従業員は SmartScreen の警告を無視し、悪意のあるファイルを実行できます。

  - "*はい*" - 従業員は SmartScreen の警告を無視して、悪意のあるファイルを実行することはできません。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067228)

  **既定値**: はい

- **[Require SmartScreen for apps and files]\(アプリとファイルに SmartScreen を要求する\)** :  
  IT 管理者が Windows 用の SmartScreen を構成することを許可します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067168)

  **既定値**: はい

## <a name="system"></a>System (システム)

詳細については、Windows ドキュメントの「[Policy CSP - System ](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system)」(ポリシー CSP - System) を参照してください。

- **[System boot start driver initialization]\(システム ブート開始ドライバーの初期化\)** :  
  このポリシー設定を使用すると、起動時マルウェア対策のブート開始ドライバーによって決まる分類に基づいて、どのブート開始ドライバーを初期化するかを指定できます。 起動時マルウェア対策のブート開始ドライバーは、各ブート開始ドライバーに次のような分類を返します。

  - "*良好*" - ドライバーが署名されていて、改ざんされていません。

  - *不良* - ドライバーがマルウェアとして認識されました。 既知の不良のドライバーの初期化を許可しないことをお勧めします。

  - "*不良 (ブートに不可欠)* " - ドライバーはマルウェアとして認識されましたが、このドライバーを読み込まなければコンピューターを正常に起動できません。

  - "*不明*" - このドライバーは、マルウェアの検出アプリケーションで証明されていないため、起動時マルウェア対策のブート開始ドライバーによって分類されていません。

  このポリシー設定を有効にした場合、次にコンピューターを起動したときに初期化するブート開始ドライバーを選択できます。 このポリシー設定を無効にした場合、または構成しなかった場合、良好、不明、または不良 (ブートに不可欠) と判定されたブート開始ドライバーは初期化され、不良と判定されたドライバーの初期化はスキップされます。 お使いのマルウェアの検出アプリケーションに起動時マルウェア対策のブート開始ドライバーが含まれない場合、または起動時マルウェア対策のブート開始ドライバーが無効になっている場合、この設定は影響せず、すべてのブート開始ドライバーが初期化されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067307)

  **既定値**: 良好、不明、および不良 (ブートに不可欠)

## <a name="wi-fi"></a>Wi-Fi

詳細については、Windows ドキュメントの「[Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)」(ポリシー CSP - Wifi) を参照してください。

- **[インターネット共有をブロックする]** :  
  インターネット共有がデバイスで可能かどうかを指定します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067327)

  **既定値**: はい

- **[Block Automatically connecting to Wi-Fi hotspots]\(Wi-Fi ホットスポットへの自動接続をブロックする\)** :  
  デバイスが Wi-Fi ホットスポットに自動的に接続するのを許可または禁止します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067320)

  **既定値**: はい

## <a name="windows-connection-manager"></a>Windows 接続マネージャー

詳細については、Windows ドキュメントの「[Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager)」(ポリシー CSP - WindowsConnectionManager) を参照してください。

- **[Block connection to non-domain networks]\(非ドメイン ネットワークへの接続をブロックする\)** :  
  このポリシー設定は、コンピューターがドメイン ベースのネットワークと非ドメイン ベースのネットワークに同時に接続することを禁止します。 このポリシー設定を有効にした場合、コンピューターは次の状況で自動または手動のネットワーク接続試行に応答します。

  - *[自動接続試行]* - コンピューターがドメイン ベースのネットワークに既に接続している場合は、非ドメイン ネットワークへの自動接続試行がすべてブロックされます。 コンピューターが非ドメイン ベースのネットワークに既に接続している場合は、ドメイン ネットワークへの自動接続試行がブロックされます。

  - *[手動接続試行]* - コンピューターがイーサネット以外のメディアを介して非ドメイン ベースのネットワークまたはドメイン ベースのネットワークに接続しているときに、ユーザーがこのポリシー設定に違反して他のネットワークへの手動接続を作成しようとした場合は、既存のネットワーク接続が切断され、手動接続が許可されます。 コンピューターがイーサネットを介して非ドメイン ベースのネットワークまたはドメイン ベースのネットワークに接続しているときに、ユーザーがこのポリシー設定に違反して他のネットワークへの手動接続を作成しようとした場合は、既存のイーサネット接続が保持され、手動接続試行がブロックされます。

  このポリシー設定を構成しなかった場合、または無効にした場合、コンピューターはドメイン ネットワークと非ドメイン ネットワークの両方に同時に接続できます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067323)

  **既定値**: 有効

## <a name="microsoft-defender"></a>Microsoft Defender

詳細については、Windows ドキュメントの「[Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)」(ポリシー CSP - Defender) を参照してください。

- **[受信メール メッセージをスキャンする]** :  
  メールのスキャンを許可または禁止します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067116)

  **既定値**: はい

- **[Office apps launch child process type]\(Office アプリの子プロセスの起動の種類\)** :  
  Office アプリは子プロセスを作成できなくなります。 これには、Word、Excel、PowerPoint、OneNote、および Access が含まれます。 これは一般的なマルウェアの動作です。特に、Office アプリを使用して悪意のある実行可能ファイルを起動またはダウンロードしようとするマクロベースの攻撃の場合に一般的です。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067121)

  **既定値**: ブロック

- **[Defender sample submission consent type]\(Defender のサンプル送信の同意の種類\)** :  
  Microsoft Defender でデータを送信するためのユーザーの同意レベルを確認します。 必要な同意が既に与えられている場合、Microsoft Defender からそれらが送信されます。 それ以外の場合 (かつユーザーが "確認しない" を指定した場合)、(Defender/AllowCloudProtection が許可されている場合は) データを送信する前にユーザーの同意を求める UI が起動します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067131)

  **既定値**: 安全なサンプルを自動的に送信します

- **[署名更新間隔 (時単位)]** :  
  Defender の署名更新間隔 (時間)。

  **既定値**: 4

- **[Script downloaded payload execution type]\(スクリプトでダウンロードされたペイロードの実行タイプ\)** :  
  Defender スクリプトでダウンロードされたペイロードの実行タイプ。

  **既定値**: ブロック
  
- **[Prevent credential stealing type]\(資格情報盗難防止タイプ\)** :  
  Microsoft Defender Credential Guard では、仮想化ベースのセキュリティを使用してシークレットを分離し、特権を持つシステム ソフトウェアだけがアクセスできるようにします。 これらのシークレットへの不正アクセスは、Pass-the-Hash や Pass-The-Ticket などの、資格情報を盗む攻撃につながる可能性があります。 Microsoft Defender Credential Guard では、NTLM パスワード ハッシュ、Kerberos のチケット保証チケット、およびアプリケーションによってドメイン資格情報として格納された資格情報を保護することで、これらの攻撃を防ぎます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067065)
  
  **既定値**: 有効にする

- **[Email content execution type]\(電子メール コンテンツ実行タイプ\)** :  
  このルールでは、次の種類のファイルが Microsoft Outlook または Web メール (Gmail.com や Outlook.com など) に表示された電子メールから実行または起動されるのをブロックします: 実行可能ファイル (例: .exe、.dll、.scr)、スクリプト ファイル (例: PowerShell .ps、VisualBasic .vbs、JavaScript .js ファイル)、スクリプト アーカイブ ファイル。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067063)

  **既定値**: ブロック

::: zone-end
::: zone pivot="mdm-may-2019"

- **[子プロセスでの Adobe Reader の起動]** :  
  **既定値**: 有効にする

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[ネットワークの保護]** :  
  このポリシーを使うと、Microsoft Defender Exploit Guard でネットワーク保護 (ブロック/監査) をオンまたはオフにできるようになります。 ネットワーク保護は Microsoft Defender Exploit Guard の機能であり、任意のアプリを使用する従業員がインターネット上のフィッシング詐欺、悪用ホスティング サイト、悪意のあるコンテンツにアクセスするのを防ぎます。 これには、サード パーティ製のブラウザーが危険なサイトに接続するのを防ぐことが含まれます。 値の型は整数です。 この設定を有効にした場合、ネットワーク保護が有効になり、従業員では無効にできません。 その動作は次のオプションで制御できます: ブロックと監査。 このポリシーを "ブロック" オプションで有効にした場合、ユーザーとアプリは危険なドメインに接続するのをブロックされます。 このアクティビティは、Microsoft Defender セキュリティ センターで表示することができます。 このポリシーを "監査" オプションで有効にした場合、ユーザー/アプリは危険なドメインに接続するのをブロックされません。 ただし、それでもこのアクティビティは Microsoft Defender セキュリティ センターで表示されます。 このポリシーを無効にした場合、ユーザー/アプリは危険なドメインに接続するのをブロックされません。 ネットワーク アクティビティは、Microsoft Defender セキュリティ センターに表示されません。 このポリシーを構成しない場合、ネットワーク ブロックは既定で無効になります。  
  [詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-network-protection)

  **既定値**: 有効にする

- **[Defender schedule scan day]\(Defender のスキャン日スケジュール\)** :  
  Defender のスキャン日スケジュール。

  **既定値**: 毎日

- **[Cloud-delivered protection]\(クラウドによる保護\)** :  
  PC を最大限に保護するため、Microsoft Defender では検出した問題についての情報が Microsoft に送信されます。 Microsoft は、その情報を分析し、報告者や他の顧客に影響する問題について詳細に把握して、強化されたソリューションを提供します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067039)

  **既定値**: はい  

- **[Defender potentially unwanted app action]\(Defender の望ましくないアプリに対するアクション\)** :  
  Microsoft Defender ウイルス対策に備わっている望ましくない可能性があるアプリケーション (PUA) 保護機能では、PUA を特定して、ご使用のネットワーク内のエンドポイントへのダウンロードやインストールをブロックできます。 これらのアプリケーションはウイルス、マルウェア、または他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を与えるアクションをエンドポイントで実行する可能性があります。 PUA は、評価が低いと考えられるアプリケーションを指すこともあります。 一般的な PUA の動作は次のとおりです。さまざまな種類のソフトウェア バンドル。Web ブラウザーへの広告挿入。問題を検出し、エラーの修正に対して支払いを要求するが、エンドポイント上に残っていて変更や最適化を何も行わないドライバーやレジストリのオプティマイザー ("偽装ウイルス対策" プログラムとも呼ばれます)。 これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、識別困難なマルウェア感染を引き起こし、アプリケーションのクリーンアップで IT リソースを浪費させる可能性があります。  
  [詳細情報](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)

  **既定値**: ブロック  

- **[Script obfuscated macro code type]\(スクリプト難読化マクロ コード タイプ\)** :  
  マルウェアや他の脅威は、一部のスクリプト ファイルに悪意のあるコードを難読化または隠ぺいしようとすることがあります。 このルールは、難読化されているらしいスクリプトが実行するのを防ぎます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067026)

  **既定値**: ブロック

- **[フル スキャン中に、リムーバブル ドライブをスキャンする]** :  
  Microsoft Defender が、フル スキャン中にリムーバブル ドライブ (フラッシュ ドライブなど) 内の悪意のあるソフトウェアや望ましくないソフトウェアをスキャンできるようにします。 Microsoft Defender ウイルス対策では、実行する前に USB デバイス上のすべてのファイルがスキャンされます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067036)

  **既定値**: はい  

- **[アーカイブ ファイルをスキャンする]** :  
  Defender はアーカイブ ファイルをスキャンします。

  **既定値**: はい

- **[動作の監視]** :  
  Microsoft Defender の動作監視機能を許可または禁止します。 Windows 10 内蔵のこれらのセンサーでは、オペレーティング システムから動作信号を収集して処理し、プライベート クラウドに他から切り離されて存在する Microsoft Defender ATP インスタンスにこのセンサー データを送信します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067111)

  **既定値**: はい

- **[ネットワーク フォルダーから開いたファイルをスキャンする]** :  
  ファイルが読み取り専用の場合、ユーザーは検出されたマルウェアを削除できません。

  **既定値**: はい

- **[Untrusted USB process type]\(信頼されていない USB 処理タイプ\)** :  
  このルールでは、管理者は署名されていない実行可能ファイルまたは信頼されていない実行可能ファイルが SD カードも含む USB リムーバブル ドライブから実行されるのを防ぐことができます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067100)

  **既定値**: ブロック

- **[Office apps other process injection type]\(Office アプリによる他のプロセスへの挿入タイプ\)** :  
  Word、Excel、PowerPoint、OneNote などの Office アプリは、他のプロセスにコードを挿入できません。 これは通常、マルウェアがウイルス対策スキャン エンジンからアクティビティを隠ぺいする試みで、悪意のあるコードを実行するために使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067019)

  **既定値**:  ブロック

- **[Office macro code allow Win32 imports type]\(Office のマクロ コードによる Win32 のインポートの許可タイプ\)** :  
  マルウェアは、Office ファイルのマクロ コードを使用して、Win32 DLL をインポートして読み込んだ後、それを使用して API 呼び出しを行い、システム全体にさらに感染させる可能性があります。 このルールは、Win32 Dll をインポートできるマクロコードを含む Office ファイルをブロックしようとします。 これには、Word、Excel、PowerPoint、OneNote が含まれます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067130)

  **既定値**: ブロック

- **[Defender cloud block level]\(Defender クラウド ブロック レベル\)** :  
  Defender のクラウド ブロック レベルです。

  **既定値**: 未構成

- **[リアルタイム監視]** :  
  Defender では、リアルタイムの監視が必要です。

  **既定値**: はい

::: zone-end
::: zone pivot="mdm-may-2019"

- **[子プロセスでの Office 通信アプリの起動]** :  
  **既定値**: 有効にする

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

- **[Office apps executable content creation or launch type]\(Office アプリの実行可能コンテンツの作成または起動タイプ\)** :  
  このルールの対象は、実行可能ファイルを作成または起動する不審な悪意のあるアドオンとスクリプト (拡張機能) で使用される一般的な動作です。 これは、マルウェアの一般的な手法です。 拡張機能は、Office アプリによって使用されるのをブロックされます。 通常、これらの拡張機能では、特定のタスクを自動化したり、ユーザー作成のアドオン機能を提供したりするスクリプトを実行するために、Windows Scripting Host (.WSH ファイル) が使用されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067108)

  **既定値**: ブロック

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="microsoft-defender-firewall"></a>Microsoft Defender ファイアウォール

詳細については、Windows プロトコルのドキュメントの「 [2.2.2 FW_PROFILE_TYPE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) 」を参照してください。

- **ファイアウォールプロファイルドメイン**:  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、ドメインに接続されているネットワークのプロファイルを表します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2066796)

  - **[受信接続をブロック]** :  
    **既定値**: はい

  - **[送信接続が必要]** :  
    **既定値**: はい

  - **[着信通知をブロック]** :  
    **既定値**: はい

  - **[ファイアウォールの有効化]** :  
    **既定値**: 許可

- **ファイアウォールプロファイルのパブリック**:  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、パブリック ネットワークのプロファイルを表します。 これらのネットワークは、サーバー ホストで管理者によってパブリックとして分類されます。 分類は、ホストが初めてネットワークに接続したときに行われます。 通常、このようなネットワークは、空港や喫茶店など、ネットワーク内のピアまたはネットワーク管理者が信頼されていない公共の場所にあるものです。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067143)

  - **[受信接続をブロック]** :  
    **既定値**: はい

  - **[送信接続が必要]** :  
    **既定値**: はい

  - **[着信通知をブロック]** :  
    **既定値**: はい

  - **[ファイアウォールの有効化]** :  
    **既定値**: 許可

  - **[グループ ポリシーからの接続セキュリティ ルールをマージしない]** :  
    **既定値**: はい

  - **[グループ ポリシーからのポリシー ルールをマージしない]** :  
    **既定値**: はい

- **ファイアウォールプロファイルのプライベート**:  
  ルールが属するプロファイルを指定します: ドメイン、プライベート、パブリック。 この値は、プライベート ネットワークのプロファイルを表します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067041)

  - **[受信接続をブロック]** :  
    **既定値**: はい

  - **[送信接続が必要]** :  
    **既定値**: はい

  - **[着信通知をブロック]** :  
    **既定値**: はい

  - **[ファイアウォールの有効化]** :  
    **既定値**: 許可

## <a name="windows-hello-for-business"></a>Windows Hello for Business

- **使用可能な場合は、高度なスプーフィング対策を要求する**

  「はい」の場合、デバイスは拡張スプーフィング対策を使用します (使用可能な場合)。 それ以外の場合、スプーフィング対策はブロックされます。 構成されていない場合は、クライアントで行われた構成を優先します。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067192)

  **既定値**: はい

- **Windows Hello for Business の構成**

  Windows Hello for Business は、パスワード、スマート カード、および仮想スマート カードを置き換えることで Windows にサインインする代替方法です。

  > [!IMPORTANT]
  > この設定のオプションは、暗黙的な意味とは逆になります。 逆に、値が*Yes*の場合は、Windows Hello を有効にせずに、構成されて*いない*として扱われます。 この設定を [*未構成*] に設定すると、このベースラインを受信するデバイスで Windows Hello が有効になります。
  >
  > この動作を反映するために、次の説明が変更されています。 設定の反転は、このセキュリティベースラインの今後の更新で修正される予定です。

  - [*未構成*] に設定すると、windows hello が有効になり、デバイスは windows Hello for Business をプロビジョニングします。
  - *[はい]* に設定した場合、ベースラインはデバイスのポリシー設定に影響しません。 これは、Windows Hello for Business がデバイスで無効になっていると、無効のままになることを意味します。 有効になっている場合は、有効のままになります。
  <!-- expected behavior 
  - When set to *Yes*, you  enable this policy and the device provisions Windows Hello for Business.  
  - When set to *Not configured*, the baseline does not affect the policy setting of the device. This means that if Windows Hello for Business is disabled on a device, it remains disabled. If its enabled, it remains enabled. 
  -->

  この基準を使用して Windows Hello for Business を無効にすることはできません。 Windows Hello for Business を無効にするには、 [windows の登録](windows-hello.md)を構成するか、 [identity protection](identity-protection-configure.md)のデバイス構成プロファイルの一部としてを使用します。  

  **既定値**: はい

- **[PIN に小文字が必要]** :  
  必要に応じて、ユーザーの PIN には少なくとも1つの小文字を含める必要があります。

  **既定値**: 許可

- **[PIN に特殊文字が必要]** :  
  必要に応じて、ユーザーの PIN には少なくとも1つの特殊文字を含める必要があります。

  **既定値**: 許可

- **[PIN の長さの最小値]** :  
  PIN の最小長は 4 ~ 127 の範囲で指定する必要があります。

  **既定値**: 6

- **[PIN に大文字が必要]** :  
  必要に応じて、ユーザーの PIN には少なくとも1つの大文字を含める必要があります。

  **既定値**: 許可

::: zone-end
::: zone pivot="mdm-preview,mdm-may-2019"

## <a name="windows-ink-workspace"></a>Windows Ink ワークスペース

詳細については、Windows ドキュメントの「[Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)」(ポリシー CSP - WindowsInkWorkspace) を参照してください。

- **[Ink Workspace]\(Ink ワークスペース\)** :  
  ユーザーに Ink ワークスペースへのアクセスを許可するかどうかを指定します。

  - "*無効*" - Ink ワークスペースへのアクセスは無効にされます。 機能はオフになります。

  - "*有効*" - Ink ワークスペース機能はオンですが、ユーザーはロック画面上ではそれにアクセスできません。

  - *未構成* - Ink ワークスペース機能がオンにされ、ユーザーはロック画面上でそれを使用できるようになります。

  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067241)

  **既定値**: 有効

## <a name="windows-powershell"></a>Windows PowerShell

詳細については、Windows ドキュメントの「[Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell)」 (ポリシー CSP - WindowsPowerShell) を参照してください。

- **[Power shell shell script block logging]\(PowerShell シェル スクリプト ログ記録ブロック\)** :  
  このポリシー設定は、Microsoft-Windows-PowerShell/Operational イベント ログへのすべての PowerShell スクリプト入力のログ記録を有効にします。 このポリシー設定を有効にした場合、Windows PowerShell は対話的に、またはオートメーションを介して呼び出された、コマンド、スクリプト ブロック、関数、およびスクリプトの処理をログに記録します。 このポリシー設定を無効にすると、PowerShell スクリプトの入力のログ記録は無効になります。 スクリプト ブロックの呼び出しのログ記録を有効にすると、PowerShell はさらに、コマンド、スクリプト ブロック、関数、またはスクリプトの呼び出しの開始時または停止時にイベントを記録します。 呼び出しのログ記録を有効にすると、大量のイベント ログが生成されます。 注: このポリシー設定は、グループ ポリシー エディターの [コンピューターの構成] と [ユーザーの構成] の両方の下にあります。 [コンピューターの構成] のポリシー設定は、[ユーザーの構成] のポリシー設定よりも優先されます。  
  [詳細情報](https://go.microsoft.com/fwlink/?linkid=2067330)

  **既定値**: 有効

::: zone-end
::: zone pivot="mdm-may-2019"

## <a name="whats-changed-in-the-new-template"></a>新しいテンプレートの変更点

2019年 5*月の MDM セキュリティベースライン*テンプレートは、*プレビュー*テンプレートから次のように変更されています。

### <a name="changes-to-the-baseline-settings"></a>ベースライン設定の変更

以下の設定は、次のいずれかになります。

- この最新バージョンのベースラインに*新しく追加*された。
- この最新のベースラインバージョンから*削除さ*れましたが、以前のバージョンには存在していました。
- 以前のバージョンでの設定の表示から、何らかの方法で*変更*されています。

*[新規]* [**ロックを超え**](#above-lock)ています:

- **ロック画面から音声でアプリをアクティブ化する**

" *[新規]* " [**アプリケーション管理**](#application-management):

- **ユーザーによるインストールの制御をブロックする**
- **管理者特権での MSI アプリのインストールをブロックする**

*[削除]* [**BitLocker**](#bitlocker):

- BitLocker リムーバブルドライブポリシー >**暗号化方法**
- **BitLocker 固定ドライブポリシー** *(すべての設定)*
- **BitLocker システムドライブポリシー** *(すべての設定)*

" *[新規]* " [**接続**](#connectivity):

- **UNC パスへのセキュリティで保護されたアクセスの構成**

" *[新規]* " [**Device Guard**](#device-guard):

- **仮想化ベースのセキュリティ**

*[新規]* [**DMA ガード**](#dma-guard):

- **Kernel DMA Protection と互換性のない外部デバイスの列挙**

" *[新規]* " [**Internet Explorer**](#internet-explorer):

- **Internet Explorer のインターネット ゾーンでスクリプトを介してステータス バーを更新する**
- **Internet Explorer のインターネット ゾーンでのファイルのドラッグ アンド ドロップまたはコピーと貼り付け**
- **Internet Explorer の制限付きゾーンでの .NET Framework 依存コンポーネント**
- **Internet Explorer のローカル コンピューター ゾーンで Active X コントロールに対してマルウェア対策を実行しない**
- **Internet Explorer の暗号化のサポート**

*[変更済み]* [**Internet Explorer**](#internet-explorer):

- 既定値が**無効になっ**ている > **internet Explorer のインターネットゾーンの自動プロンプトでファイルのダウンロード**が有効になりました。 プレビューでは、この設定は [有効] に設定されました。

" *[新規]* " [**リモート アシスタンス**](#remote-assistance):

- **リモートアシスタンスの要請**
  - **リモートアシスタンスの要請アクセス許可**
  - **チケットの最大有効時間値**
  - **チケットの最大有効期間**
  - **電子メールの招待方法**

" *[新規]* " [**Microsoft Defender**](#microsoft-defender):

- **子プロセスでの Adobe Reader の起動**
- **子プロセスでの Office 通信アプリの起動**

*[新規]* [ **[Microsoft Defender ファイアウォール]** ](#microsoft-defender-firewall)

- **ファイアウォールプロファイルドメイン**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**
- **ファイアウォールプロファイルパブリック**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**
  - **グループ ポリシーからの接続セキュリティ ルールをマージしない**
  - **グループ ポリシーからのポリシー ルールをマージしない**
- **ファイアウォールプロファイルのプライベート**
  - **受信接続をブロック**
  - **送信接続が必要**
  - **着信通知をブロック**
  - **ファイアウォールの有効化**

" *[新規]* " [**Windows Hello for Business**](#windows-hello-for-business):

- **使用可能な場合は、高度なスプーフィング対策を要求する**
- **Windows Hello for Business の構成**
- **PIN に小文字が必要**
- **PIN に特殊文字が必要**
- **PIN の長さの最小値**
- **PIN に大文字が必要**

::: zone-end
