---
# required metadata

title: Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune によるモバイル アプリケーション管理のためにアプリを準備する方法を決める
Intune アプリ ラッピング ツールまたは Intune アプリ SDK のどちらかを使って、アプリでモバイル アプリケーション管理ポリシーを使えるようにできます。 ここでは、これら 2 つの方法の内容と用途について説明します。

## Intune アプリ ラッピング ツール
アプリ ラッピング ツールは、主として、内部基幹業務 (LOB) アプリケーションに使います。 このツールは、アプリのラッパーを作成するコマンド ライン アプリケーションです。このラッパーにより、アプリを Intune モバイル アプリケーション管理ポリシーで管理できるようになります。 このツールを使うためにソース コードは必要ありませんが、署名資格情報が必要です。  署名資格情報について詳しくは、[Intune のブログ](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx)をご覧ください。 アプリ ラッピング ツールのドキュメントとしては、[Android アプリ ラッピング ツール](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)と [iOS アプリ ラッピング ツール](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)をご覧ください。.

アプリ ラッピング ツールは、アプリ ストアまたは Play ストアにあるアプリ、あるいは開発時の統合を必要とする機能をサポートしていません (次の機能比較表をご覧ください)。

アプリが既に完成している場合、またはソース コードが利用できない場合は、SDK ではなく、アプリ ラッピング ツールを使用する必要があります。

## Intune アプリ SDK
アプリ SDK は、主として、App Store または Play ストアにあるアプリを Intune で管理できるようにするお客様向けに設計されています。 ただし、どのようなアプリでも (LOB アプリでさえ)、SDK の統合を利用できます。

SDK を統合するには、アプリのソース コードにアクセスする必要があります。 SDK を統合する方法について詳しくは、「[Microsoft Intune アプリ SDK](https://msdn.microsoft.com/library/mt627769.aspx)」をご覧ください。.

## 機能の比較
アプリ SDK とアプリ ラッピング ツールに対して利用できる設定を、次の表に示します。

> [!NOTE]
> アプリ ラッピング ツールは、スタンドアロンの Intune または Configuration Manager と統合した Intune で使用できます。

|機能|アプリ SDK|アプリ ラッピング ツール|
|-----------|---------------------|-----------|
|[Web コンテンツを会社の管理対象ブラウザーで表示するように制限する]|○|○|
|[Android、iTunes、iCloud のバックアップを禁止する]|○|○|
|[アプリで他のアプリへのデータ転送を許可する]|○|○|
|[アプリで他のアプリからのデータの受信を許可する]|○|○|
|[切り取り、コピー、および他のアプリでの貼り付けを制限する]|○|○|
|[アクセスには簡易暗証番号が必要]|○|○|
|[組み込みアプリ PIN を Intune PIN で置き換える]|○||
|[PIN をリセットするまでの試行数を指定する]|○|○|
|[PIN の代わりに指紋を要求する (iOS のみ)]<br></br>**注:** MAM 専用の環境でのみ使用できます。|○||
|[アクセスには会社の資格情報が必要]|○|○|
|[脱獄またはルート化されたデバイスで管理対象アプリが実行されないようにブロックする]|○|○|
|[アプリ データの暗号化]|○|○|
|[指定した時間 (分) 後にアクセス要件を再確認する]|○|○|
|[オフラインの猶予期間を指定する]|○|○|
|[画面キャプチャをブロック] (Android のみ)|○|○|
|完全なワイプ|○|○|
|選択的なワイプ <br></br>**注:** iOS では、管理プロファイルを削除するとアプリも削除されます。|○||
|[[名前を付けて保存] を禁止する] |○||
|[マルチ ID アプリのサポート]|○||

### 関連項目
[Android アプリ ラッピング ツール](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS アプリ ラッピング ツール](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK を使用してモバイル アプリケーション管理に対応する](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


