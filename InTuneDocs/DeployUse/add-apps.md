---
# required metadata

title: アプリを追加する | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune でアプリを追加する
Microsoft Intune でアプリの展開を開始する前に、このトピックで説明している概念について理解を深めてください。 これらの概念は、アプリの展開先として使用できるプラットフォームや、展開に必要な前提条件を理解するのに役立ちます。

## Intune で展開できるアプリの種類
Intune でサポートされているすべての種類のデバイスにアプリを展開できます。 プロセスとサポートされているデバイスは、展開するアプリの種類によって異なります。 展開できるアプリと展開できないアプリについて、次の情報を参照してください。


### **Windows インストーラー (&#42;.exe, &#42;.msi)**
- この種類のアプリは、ユーザー入力なしのサイレント インストールをサポートする必要があります。 アプリのマニュアルに、サイレント インストールの実行に関連するコマンドライン オプションが記載されている必要があります (たとえば、**/q**)。 一般的なコマンド ライン オプションの一覧は、[こちら](https://support.microsoft.com/en-us/kb/227091)にあります。
- アプリのセットアップ プログラムに必要なその他のファイルとフォルダーは、アプリのセットアップ ファイルに指定した場所から使用できるようにする必要があります。
- 多くの場合、Intune で Windows インストーラー (.msi) と Windows インストーラー パッチ (.msp) ファイルをインストールするために必要なコマンドライン引数はありません。 詳細については、アプリのマニュアルを確認してください。 コマンドライン引数が必要な場合は、"名前=値" の対 (例: TRANSFORMS=custom_transform.mst) の形式で入力します。

この種類のアプリは、クラウドの記憶域にアップロードされます。
### **Android アプリ パッケージ (&#42;.apk ファイル)**
この種類のアプリは、クラウドの記憶域にアップロードされます。
### **iOS アプリ パッケージ (&#42;.ipa ファイル)**
- iOS アプリを展開するには、有効な .ipa パッケージ ファイルが必要です。
- .ipa パッケージは Apple によって署名され、プロビジョニング プロファイルに示されている有効期限の期限内である必要があります。 Intune では、エンタープライズ証明書付き iOS アプリケーションを配布できます。 Apple のデベロッパー証明書付きアプリがすべてサポートされているわけではありません。
- お客様の企業で、iOS Developer Enterprise Program に登録する必要があります。
- 組織のファイアウォールで、iOS の準備および認証用 Web サイトへのアクセスが許可されていることを確認してください。
- マニフェスト ファイル (.plist) は、アプリケーションと共に展開する必要はありません。

この種類のアプリは、クラウドの記憶域にアップロードされます。

現在、エンド ユーザーは iOS 向け Intune ポータル アプリから直接、会社のアプリをインストールできません。 これは、iOS アプリ ストアで公開されているアプリの制限によるもの (を参照してください [アプリ ストアのレビューのガイドライン](https://developer.apple.com/app-store/review/guidelines/))。 ユーザーが会社アプリ (管理されている App Store アプリ、基幹業務アプリなど) にアクセスするには、自身のデバイスでポータル サイト アプリを起動し、[会社のアプリ] タイルをタップします。タップすると、ブラウザーが開き、Intune Web ポータルに移動します。

### **Windows Phone アプリケーション パッケージ (&#42;.xap、.appx、.appxbundle)**
- アプリを展開するには、エンタープライズ モバイル コード署名証明書が必要です。 詳細については、「[Microsoft Intune を使用して Windows Phone の管理をセットアップする](set-up-windows-phone-management-with-microsoft-intune.md)」を参照してください。

この種類のアプリは、クラウドの記憶域にアップロードされます。

Intune で、基幹業務のユニバーサル Windows プラットフォーム (UWP) アプリをインストールする方法については後述します。

### **Windows アプリケーション パッケージ (.appx、.appxbundle)**
- アプリを展開するには、エンタープライズ モバイル コード署名証明書が必要です。 詳細については、「[Set up Windows device management with Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)」 (Microsoft Intune を使用して Windows デバイスの管理をセットアップする) を参照してください。

この種類のアプリは、クラウドの記憶域にアップロードされます。
### **MDM を介した Windows インストーラー (&#42;.msi)**
このインストーラーの種類では、Windows インストーラー ベースのアプリを作成して、Windows 10 を実行する登録済み PC に展開できます。<br /><br />このインストーラーの種類を使用する場合は、次の点を考慮してください。
- 拡張子が .msi のファイルを 1 つだけアップロードできます。
- アプリの検出では、ファイルの製品コードと製品バージョンが使用されます。
- アプリの既定の再起動動作が使用されます。 Intune ではこの機能を制御しません。
- ユーザー単位の MSI パッケージは単一のユーザーにインストールされます。
- コンピューター単位の MSI パッケージはデバイス上のすべてのユーザーにインストールされます。
- デュアル モードの MSI パッケージは現在、デバイス上のすべてのユーザーに対するインストールのみが実行されます。
- アプリの更新プログラムは、各バージョンの MSI 製品コードが同じである場合にサポートされます。

この種類のアプリは、クラウドの記憶域にアップロードされます。
### **外部リンク**
以下の場合に使用します。
- アプリ ストアからユーザーがアプリをダウンロードできる **URL**。
- Web ブラウザーから実行する Web ベース アプリの**リンク**。

外部リンク ベースののアプリは、Intune のクラウド記憶域には格納されません。
### **App Store の管理対象 iOS アプリ**
App Store から無料で利用できる iOS アプリを管理および展開できます。 [モバイル アプリケーションの管理ポリシー](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md)を[互換性のあるアプリ](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)に関連付け、その状態を管理コンソールで確認することもできます。<br /><br />管理対象の iOS アプリは、Intune のクラウド記憶域には格納されません。
> [!TIP] [[モバイル デバイス管理機関の設定]](get-ready-to-enroll-devices-in-microsoft-intune.md) を Intune に設定すると、モバイル デバイス用のオプションを使用できるようになります。

## ユニバーサル Windows プラットフォーム (UWP) アプリのサポート
Windows 10 デバイスで基幹業務アプリをインストールする場合、サイドローディング キーは不要です。 ただし、レジストリ キー **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** は、サイドローディングを有効にするため、値は **1** である必要があります。

このレジストリ キーが構成されていない場合は、アプリをデバイスに初めて展開する際に、Intune によってこの値が自動的に **1** に設定されます。 この値を **0** に設定した場合、Intune は値を自動的に変更することができず、基幹業務アプリの展開は失敗します。

ユニバーサル Windows プラットフォームの基幹業務アプリは、アプリが展開される各デバイス上で信頼されているコード署名証明書で署名される必要があります。 社内の PKI 基盤からの証明書を使用することも、デバイスにインストールされたサード パーティのパブリック ルート証明書からの証明書を使用することもできます。

Windows 10 Mobile デバイス上では、Symantec 以外のコード署名証明書を使用して、ユニバーサル **.appx** アプリに署名することができます。 **.xap** アプリの場合、また Windows 10 Mobile デバイスにインストールする Windows Phone 8.1 用にビルドされた **.appx** パッケージの場合は、Symantec コード署名証明書を使用する必要があります。

## 次のステップ 

次に、アプリを展開する前に、Intune コンソールでアプリを追加する必要があります。 [登録されたデバイス](add-apps-for-mobile-devices-in-microsoft-intune.md)と [Intune クライアント ソフトウェアで管理する Windows PC](add-apps-for-windows-pcs-in-microsoft-intune.md) にアプリを追加できます。

<!--HONumber=May16_HO4-->


