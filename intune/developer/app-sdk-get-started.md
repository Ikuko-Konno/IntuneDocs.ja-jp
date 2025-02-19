---
title: Microsoft Intune App SDK の概要
description: Microsoft Intune でモバイル アプリケーション管理 (MAM) 用のモバイル アプリをすぐに有効にできます。
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9742305905c5ba49930e13646bf13d8c248426b6
ms.sourcegitcommit: 7cc45ef52dda08479bc6bdff7d11d2f6c0e7b93b
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "74899401"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Microsoft Intune App SDK の概要

このガイドを利用すると、Microsoft Intune でアプリ保護ポリシーをサポートするように、モバイル アプリをすぐに有効にできます。 まず、「[Intune アプリ SDK の概要](app-sdk.md)」で説明されている Intune アプリ SDK の利点を理解しておくことをお勧めします。

Intune アプリ SDK は、iOS と Android で類似するシナリオをサポートしており、プラットフォーム全体にわたって一貫した操作性を IT 管理者に提供することを目的としています。 しかし、プラットフォームの違いや制限により、特定機能のサポートについてわずかな相違点があります。

## <a name="register-your-store-app-with-microsoft"></a>Microsoft でのストア アプリの登録

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>アプリが組織内向けであり、一般に公開できない場合:

アプリを登録する _**必要はありません**_ 。 会社が作成したまたは会社向けに作成された社内向け[基幹業務 (LOB) アプリ](../apps/apps-add.md#app-types-in-microsoft-intune)の場合、IT 管理者が社内にアプリを展開します。 Intune は、アプリが SDK でビルドされたことを検出し、IT 管理者がアプリ保護ポリシーを適用できるようにします。 「[アプリ保護ポリシーに対して iOS または Android アプリを有効にする](#enable-your-ios-or-android-app-for-app-protection-policy)」セクションに進んでください。

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Apple App Store や Google Play などのパブリック アプリ ストアにアプリをリリースする場合:

最初に Microsoft Intune にアプリを登録し、登録規約に同意する _**必要があります**_ 。 その後、IT 管理者はアプリ保護ポリシーを管理対象アプリに適用できるようになり、そのアプリは[保護されている Intune パートナーアプリ](../apps/apps-supported-intune-apps.md#partner-apps)としてリストされます。

登録が完了し、Microsoft Intune チームによって確認されるまで、Intune 管理者はアプリ保護ポリシーをアプリのディープ リンクに適用できません。 アプリは、[Microsoft Intune パートナーのページ](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)にも追加されます。 ここには、Intune のアプリ保護ポリシーに対応していることを示すアプリのアイコンが表示されます。

### <a name="the-registration-process"></a>登録プロセス
Microsoft 連絡先をまだ利用したことがない場合、登録プロセスを始めるには、[Microsoft Intune アプリ パートナー アンケート](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR80SNPjnVA1KsGiZ89UxSdVUMEpZNUFEUzdENENOVEdRMjM5UEpWWjJFVi4u)に記入します。

Microsoft が、アンケートに入力された電子メール アドレスを使用してご連絡し、登録プロセスを続行します。 また、何らかの問題が発生した場合の連絡にも、登録電子メール アドレスを使用します。

> [!NOTE]
> アンケートおよび Microsoft Intune チームとの電子メール通信で収集されたすべての情報は、[Microsoft のプライバシーに関する声明](https://www.microsoft.com/privacystatement/default.aspx)に従って処理されます。

**登録プロセスの流れ**:

1. アンケートを送信すると、正常に受信したことを確認するか、または登録を完了するための追加情報を要求する目的で、Microsoft から登録電子メール アドレスにご連絡します。

2. 必要な情報をすべて受け取った後、Microsoft は署名のために Microsoft Intune アプリ パートナー契約をお送りします。 この契約には、Microsoft Intune アプリ パートナーになる上でお客様の会社が同意する必要のある条項が記載されています。

3. また、アプリが正常に Microsoft Intune サービスに登録されたり、アプリが [Microsoft Intune パートナー](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)のサイトで推奨されたりした場合にも連絡があります。

4. 最後に、アプリのディープ リンクが、次の月の Intune サービス更新に追加されます。 たとえば、7 月に登録情報を完了した場合、ディープ リンクのサポートは 8 月中旬になります。

アプリのディープ リンクを今後変更する場合は、アプリを再登録する必要があります。

> [!NOTE]
> 新しいバージョンの Intune App SDK を使用してアプリを更新する場合は、Microsoft にご連絡いただく必要があります。

## <a name="download-the-sdk-files"></a>SDK ファイルをダウンロードする

ネイティブ iOS 用および Android 用の Intune アプリ SDK は、Microsoft GitHub アカウントでホストされています。 ネイティブ iOS 用および Android 用の SDK ファイルは、それぞれ以下のパブリック リポジトリにあります。

* [iOS 用 Intune App SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android 用 Intune App SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

お使いのアプリが Xamarin アプリの場合は、次の異なる SDK を使用してください。

* [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)

リポジトリのフォークとプルに使用できる GitHub アカウントにサインアップすることをお勧めします。 GitHub では、Microsoft 製品チームとのやり取り、問題の提出と迅速な応答、リリース ノートの表示、Microsoft へのフィードバックの提供が可能です。 Intune アプリ SDK GitHub についてご不明な点がある場合は、msintuneappsdk@microsoft.com にお問い合わせください。

## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>アプリ保護ポリシーに対して iOS または Android アプリを有効にする

以下の開発者ガイドのいずれかが必要になります。これらは、Intune アプリ SDK をご使用のアプリに統合するのに役立ちます。

* **[iOS 用 Intune アプリ SDK 開発者ガイド](app-sdk-ios.md)** : このドキュメントでは、Intune アプリ SDK を使用したネイティブ iOS アプリを有効にする方法について、段階的に説明しています。

* **[Android 用 Intune アプリ SDK 開発者ガイド](app-sdk-android.md)** : このドキュメントでは、Intune アプリ SDK を使用したネイティブ Android アプリを有効にする方法について、段階的に説明しています。

* **[Intune App SDK Xamarin Bindings ガイド](app-sdk-xamarin.md)** : このドキュメントは、iOS アプリと Android アプリを Xamarin を使用してビルドし、Intune アプリ保護ポリシーを適用するのに役立ちます。



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>アプリ ベースの条件付きアクセスに対して iOS または Android アプリを有効にする

アプリの保護ポリシーに対してアプリを有効することに加えて、Azure Active Directory (AAD) アプリ ベースの条件付きアクセスを使ってアプリを正常に機能させるには、以下が必要です。

* アプリのビルドには [Azure Active Directory Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) が使用されていて、AAD ブローカー認証に対してアプリが有効になっている。

* アプリの [AAD クライアント ID](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#configure-a-native-client-application) は、iOS および Android のプラットフォーム全体で一意である必要がある。

## <a name="configure-telemetry-for-your-app"></a>アプリの製品利用統計情報を構成する

Microsoft Intune はアプリの利用統計データを収集します。

* **iOS 用 Intune アプリ SDK**: SDK により、既定では、使用状況イベントに関する SDK 製品利用統計情報がログに記録されます。 このデータは、Microsoft Intune に送信されます。

  * アプリから SDK の製品利用統計情報を Microsoft Intune に送信しない場合は、IntuneMAMSettings ディレクトリのプロパティ `MAMTelemetryDisabled` を "YES" に設定して、製品利用統計情報の送信を無効にする必要があります。

* **Intune App SDK for Android**: Intune App SDK for Android は、アプリからのデータ収集を制御しません。 ポータル サイト アプリケーションでは、既定で、製品利用統計情報がログに記録されます。 このデータは、Microsoft Intune に送信されます。 Microsoft ポリシーに基づき、個人を特定できる情報 (PII) は収集しません。 

  * エンド ユーザーがこのデータの送信を選択しない場合、ポータル サイト アプリの [設定] で製品利用統計情報をオフにする必要があります。 詳しくは、「[Microsoft による使用状況データの収集を無効にする](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android)」をご覧ください。 

## <a name="line-of-business-app-version-numbers"></a>基幹業務アプリのバージョン番号

Intune では、iOS アプリと Android アプリを対象に、基幹業務アプリのバージョン番号が表示されるようになりました。 Azure Portal のアプリ一覧とアプリ概要ブレードで番号が表示されます。 エンド ユーザーは、ポータル サイト アプリと Web ポータルでアプリ番号を確認できます。

### <a name="full-version-number"></a>バージョン番号 (フル)

バージョン番号 (フル) は、アプリのリリースを特定する番号です。 この番号は _バージョン_(_ビルド_) の形式で表示されます。 たとえば、2.2(2.2.17560800) のようになります。 

バージョン番号 (フル) を構成する 2 つの要素:

- **バージョン**  
  バージョン番号は、人間が判読できるアプリのリリース番号です。 エンド ユーザーがアプリの各種リリースを区別するために使用されます。

- **ビルド番号**  
  ビルド番号は、アプリの検出に利用される内部番号です。また、プログラミングでアプリを管理するために利用されます。 ビルド番号は、コードの変更を参照するアプリのイテレーションを参照します。

### <a name="version-and-build-number-in-android-and-ios"></a>Android と iOS のバージョンおよびビルド番号

Android と iOS はいずれもバージョンおよびビルド番号を利用してアプリを参照します。 ただし、オペレーティング システムには OS 固有の意味があります。 次の表で以上の用語の関連性を説明します。

Intune で使用する基幹業務アプリを開発するときは、バージョン番号とビルド番号の両方を必ず使用してください。 Intune のアプリ管理機能では、意味のある **CFBundleVersion** (iOS の場合) と **PackageVersionCode** (Android の場合) が利用されます。 これらの番号はアプリ マニフェストに含まれます。 

Intune|iOS|Android|説明|
|---|---|---|---|
バージョン番号|CFBundleShortVersionString|PackageVersionName |この番号は、エンド ユーザー向けにアプリの特定のリリースを示します。|
ビルド番号|CFBundleVersion|PackageVersionCode |この番号は、アプリ コードのイテレーションを示すために使用されます。|

#### <a name="ios"></a>iOS

- **CFBundleShortVersionString**  
  バンドルのリリース バージョン番号を指定します。 この番号でアプリのリリース バージョンが識別されます。 この番号はエンド ユーザーがアプリを参照するために使用されます。
- **CFBundleVersion**  
  バンドルのビルド バージョン。バンドルのイテレーションが識別されます。 この番号でリリース バンドルまたは未リリース バンドルが識別されます。 この番号はアプリの検出に利用されます。

#### <a name="android"></a>Android

- **PackageVersionName**  
  ユーザーに表示されるバージョン番号。 この属性は、生文字列として、または文字列リソースの参照として設定できます。 この文字列には、ユーザーに表示する以外の目的はありません。
- **PackageVersionCode**  
  内部バージョン番号。 この番号は、ある番号が別の番号より新しいかどうかを判断するためにのみ利用されます。番号が大きければ、より新しいバージョンとなります。 これはバージョンではありません。 

## <a name="next-steps-after-integration"></a>統合後の次の手順

### <a name="test-your-app"></a>アプリのテスト
iOS または Android アプリを Intune アプリ SDK と統合するために必要な手順を完了した後、すべてのアプリ保護ポリシーが、ユーザーと IT 管理者に対して有効化され、機能していることを確認する必要があります。統合されたアプリをテストするには、次の手順を実行します。

* **Microsoft Intune のテスト アカウント**: Intune アプリ保護機能に対して Intune の管理対象アプリをテストするには、Microsoft Intune のアカウントが必要です。

  * Intune アプリ保護ポリシーに対して iOS または Android ストア アプリを有効化している ISV の場合は、登録ステップで説明した Microsoft Intune での登録が完了すると、プロモーション コードを受け取ります。 プロモーション コードを使用すると、Microsoft Intune の 1 年間の拡張使用試用版にサインアップできます。

  * ストアに出荷されない基幹業務アプリを開発している場合は、組織を介して Microsoft Intune へのアクセス権が付与されます。 この場合も、[Microsoft Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) で、1 か月間の無料試用版にサインアップできます。

  * エンド ユーザー アカウントを使用してモバイル デバイスでアプリをテストしている場合は、管理者アカウントを使用してログインした後、Microsoft 365 管理センター Web サイトによってそのアカウントに Intune ライセンスが付与されていることを確認します。[Microsoft Intune ライセンスの割り当て](../fundamentals/licenses-assign.md)に関するページを参照してください。

* **Intune のアプリ保護ポリシー**: Intune のすべてのアプリ保護ポリシーに対して、ご使用のアプリをテストするには、ポリシー設定ごとに想定される動作を把握する必要があります。 [iOS アプリ保護ポリシー](../apps/app-protection-policy-settings-ios.md)と [Android アプリ保護ポリシー](../apps/app-protection-policy-settings-android.md)の説明を参照してください。 アプリが Intune SDK を統合していても、不要アプリの一覧に表示されていない場合は、[カスタムアプリ] を選択するときに、テキストボックスにアプリのバンドル ID (iOS) またはパッケージ名 (Android) を指定できます。 

* **トラブルシューティング**: アプリのインストール ユーザー エクスペリエンスを手動でテストしているときに問題が発生した場合は、「[アプリのインストールに関する問題のトラブルシューティング](../apps/troubleshoot-app-install.md)」をご覧ください。 

### <a name="give-your-app-access-to-the-intune-app-protection-service-optional"></a>Intune アプリ保護サービスへのアクセス権をアプリに付与する (省略可能)

アプリで認証用に独自のカスタム Azure Active Directory (AAD) 設定を使用している場合、パブリック ストア アプリと内部 LOB アプリの両方に対して次の手順を実行する必要があります。 この手順は、**アプリで Intune SDK の既定のクライアント ID を使用している場合は実行する必要はありません**。 

アプリを Azure テナント内に登録し、それが **[すべてのアプリケーション]** の下に表示されたら、Intune アプリ保護サービス (旧称: MAM サービス) へのアクセス権をアプリに付与する必要があります。 Azure portal で次の操作を行います。

1. **[Azure Active Directory]** ブレードに移動します。
2. **[アプリ登録]** で、アプリケーション用に設定された一覧に移動します。
3. **[+ アクセス許可の追加]** をクリックします。
4. **[所属する組織で使用している API]** をクリックします。 
5. 検索ボックスに「**Microsoft Mobile Application Management**」と入力します。
6. **[委任されたアクセス許可]** で **[DeviceManagementManagedApps.ReadWrite: Read and Write the User’s App Management Data]\(DeviceManagementManagedApps.ReadWrite: ユーザーのアプリ管理データの読み取りと書き込み\)** * チェックボックスをオンにします。
7. **[アクセス許可の追加]** をクリックします。

> [!NOTE]
> アプリがこのリソースにアクセスするときにエラーが発生したためにサインインが制限されている場合: https://intunemam.microsoftonline.com 、アプリのクライアント ID で msintuneappsdk@microsoft.com にメモを送信する必要があります。 これは、今日の手動承認プロセスです。

### <a name="badge-your-app-optional"></a>アプリにバッジを付ける (省略可能)

Intune アプリ保護ポリシーがアプリで機能していることを確認したら、アプリ アイコンに Intune アプリ保護ロゴ バッジを付けることができます。

このバッジは、アプリに Intune アプリ保護ポリシーが適用されていることを、IT 管理者、エンド ユーザー、および Intune の見込み顧客に示すものです。 Intune の顧客によるアプリの使用と採用を促します。

ブリーフケース アイコンのバッジは、次のサンプルのように表示されます。

![Intune アプリ保護ポリシー - バッジの例 1](./media/app-sdk-get-started/badge-example-1.png) ![Intune アプリ保護ポリシー - バッジの例 2](./media/app-sdk-get-started/badge-example-2.png)

**アプリにバッジを付けるために必要なもの**:

* **.eps** ファイルを読み取れるイメージ操作アプリケーション、または **.ai** ファイルを読み取れる Adobe アプリケーション。

* [Intune アプリ バッジのアセットとガイドライン](https://github.com/msintuneappsdk/intune-app-partner-badge)は、Microsoft Intune GitHub にあります。
