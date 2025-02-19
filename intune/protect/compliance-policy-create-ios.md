---
title: Microsoft Intune での iOS デバイスのコンプライアンス設定 - Azure | Microsoft Docs
description: Microsoft Intune で iOS デバイスにコンプライアンスを設定するときに使用できるすべての設定の一覧を表示します。 電子メールの要求、脱獄されたまたはルート化されたデバイスの確認、許可される最小および最大のオペレーティング システムの設定、任意のパスワード制限の設定 (パスワードの長さと非アクティブの状態のデバイスを含む)、アプリの制限などを行います。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3b83b764af415349b287df2a09f9b4c355734c28
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72810238"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune を使用してデバイスを準拠または非準拠としてマークするための iOS 設定

この記事では、Intune で iOS デバイスに構成できるさまざまなコンプライアンス設定の一覧を示して説明します。 モバイル デバイス管理 (MDM) ソリューションの一部として、これらの設定を使用して、電子メールを要求する、ルート化された (脱獄された) デバイスを非準拠としてマークする、許容される脅威レベルを設定する、パスワードの有効期限を設定するなどを行います。

この機能は、以下に適用されます。

- iOS
- iPadOS

Intune サービス管理者は、組織のリソースの保護に役立てるために、これらのコンプライアンス設定を使用します。 コンプライアンス ポリシーの詳細およびその機能については、[デバイス コンプライアンスの概要](device-compliance-get-started.md)に関するページを参照してください。

## <a name="before-you-begin"></a>始める前に

[コンプライアンス ポリシーの作成](create-compliance-policy.md#create-the-policy)。 **[プラットフォーム]** で **[iOS/iPadOS]** を選択します。

## <a name="email"></a>電子メール

- **[モバイル デバイスは管理されているメール プロファイルを持つことが必要]** :  
  - **[未構成]** ("*既定値*") - この設定に対して準拠であるか非準拠であるかの評価は行われません。
  - **[必須]** - 電子メール プロファイルが Intune で管理されていないデバイスは非準拠と見なされます。 デバイスが誤って対象とされている場合、またはユーザーがデバイス上で電子メール アカウントを手動で設定した場合、デバイスには管理されたメール プロファイルが存在しません。

  デバイスは、次の状況で非準拠とみなされます。  
  - 電子メール プロファイルが、コンプライアンス ポリシーの対象となるユーザー グループとは異なるユーザー グループに割り当てられている。
  - ユーザーが、デバイスに展開された Intune 電子メール プロファイルと一致するメール アカウントを既にデバイスで設定している。 Intune でユーザー定義プロファイルを上書きすることはできず、管理することもできません。 準拠するためには、エンド ユーザーが既存の電子メール設定を削除する必要があります。 これにより、Intune は管理対象の電子メール プロファイルをインストールできるようになります。  

電子メール プロファイルの詳細については、[Intune で電子メール プロファイルを使用して組織の電子メールへのアクセスを構成する](../configuration/email-settings-configure.md)に関するページを参照してください。

## <a name="device-health"></a>デバイスのヘルス

- **[脱獄されたデバイス]** :  
  - **[未構成]** ("*既定値*") - この設定に対して準拠であるか非準拠であるかの評価は行われません。
  - **[ブロック]** - ルート化された (脱獄された) デバイスが非準拠としてマークされます。  

- **[デバイスは、デバイス脅威レベル以下であることが必要]** " *(iOS 8.0 以降)* ":  
  この設定を使用して、リスク評価をコンプライアンスの条件として実行します。 許容される脅威レベルを選択してください:  
  - **[未構成]** ("*既定値*") - この設定に対して準拠であるか非準拠であるかの評価は行われません。
  - **[セキュリティ保護]** - これはセキュリティ上最も安全なオプションであり、デバイスにはいかなる脅威も存在してはならないことを意味します。 デバイスでいずれかのレベルの脅威が検出された場合、非準拠と評価されます。
  - **[低]** - 存在する脅威が低レベルの場合のみ、デバイスは準拠として評価されます。 低レベルより高い脅威が存在する場合、デバイスは非準拠状態になります。
  - **[中]** - デバイスに存在する脅威が低レベルまたは中レベルの場合、デバイスは準拠として評価されます。 デバイスで高レベルの脅威が検出された場合は、非準拠と判定されます。
  - **[高]** - すべての脅威レベルが許容されるため、最も安全性の低いオプションとなります。 このソリューションをレポート目的のみで使用した場合、役立つ場合があります。

## <a name="device-properties"></a>デバイスのプロパティ

### <a name="operating-system-version"></a>オペレーティング システムのバージョン  

- **必要な最小 OS** *(iOS 8.0 以降)* :  
  デバイスが最小 OS バージョンの要件を満たしていない場合、非準拠として報告されます。 アップグレード方法に関する情報のリンクが表示されます。 エンド ユーザーは、そのデバイスのアップグレードを行うことを選択できます。 その後、組織のリソースにアクセスできます。

- **許可される最大 OS バージョン** *(iOS 8.0 以降)* :  
  ルールに含まれるバージョンよりも新しいバージョンの OS がデバイスで使用されている場合、組織のリソースへのアクセスがブロックされます。 IT 管理者に問い合わせることをエンド ユーザーに促すメッセージが表示されます。 OS バージョンを許可するようにルールを変更するまで、デバイスは組織のリソースにアクセスできません。

- **OS の最小ビルドバージョン** *(iOS 8.0 以降)* :  
  Apple でセキュリティ更新プログラムが発行されるときは、通常、OS バージョンではなくビルド番号が更新されます。 この機能を使用して、デバイスで許可される最小ビルド番号を入力します。

- **OS ビルドの最大バージョン** *(iOS 8.0 以降)* :  
  Apple でセキュリティ更新プログラムが発行されるときは、通常、OS バージョンではなくビルド番号が更新されます。 この機能を使用して、デバイスで許可される最大ビルド番号を入力します。

## <a name="system-security"></a>システム セキュリティ

### <a name="password"></a>パスワード

> [!NOTE]
> iOS デバイスにコンプライアンスまたは構成ポリシーが適用されると、ユーザーは 15 分ごとにパスコードを設定するように求められます。 パスコードを設定するまで継続してユーザーは入力を求められます。 IOS デバイスにパスコードが設定されると、暗号化プロセスが自動的に開始されます。 パスコードが無効になるまで、デバイスは暗号化されたままになります。

- **[モバイル デバイスのロック解除にパスワードを必要とする]** :  
  - **[未構成]** ("*既定値*") - この設定に対して準拠であるか非準拠であるかの評価は行われません。  
  - **[必須]** - デバイスにアクセスするユーザーにパスワードを入力するよう求めます。 パスワードを使用する iOS デバイスは暗号化されます。

- **[単純なパスワード]** :  
  - **未構成**(*既定*)-ユーザーは、 **1234**や**1111**のような単純なパスワードを作成できます。
  - **[ブロック]** - ユーザーは単純なパスワード (**1234**、**1111** など) を作成できません。 

- **[パスワードの最小文字数]** :  
  パスワードに必要な数字または文字の最小数を入力します。  

- **[必要なパスワードの種類]** :  
  パスワードの内容を**数字**のみにするかどうか、あるいは数字とその他の文字との組み合わせ (**英数字**) にするかどうかを選択します。

- **[パスワードに使用する英数字以外の文字数]** :  
  パスワードに含める必要がある特殊文字 (`&`、`#`、`%`、`!` など) の最小数を指定します。 

  大きな数値を設定すると、ユーザーはより複雑なパスワードを作成する必要があります。

- **[画面ロック後にパスワードが要求されるまでの最長時間 (分)]** " *(iOS 8.0 以降)* ":  
  ユーザーがデバイスにアクセスするためにパスワードを入力する前に、画面がロックされた後の時間を指定します。 オプションには、既定値の [*未構成*]、[*直ち*]、および*1 分から* *4 時間*があります。

- **[画面がロックされるまでの非アクティブな最長時間 (分)]** :  
  デバイスが画面をロックするまでのアイドル時間を入力します。 オプションには、既定値の [*未構成*]、[*直ち*]、および*1 分から* *15 分*があります。

- **[パスワードの有効期限 (日数)]** :  
  新しいパスワードの作成が必要となるまでのパスワードの有効日数を選択します。 

- **[再使用を禁止するパスワード世代数]** " *(iOS 8.0 以降)* ":   
  何回前までのパスワードを使用できないようにするかを入力します。

### <a name="device-security"></a>［デバイス セキュリティ］

- **[制限付きアプリ]** :  
  バンドル ID をポリシーに追加することでアプリを制限できます。 デバイスにアプリがインストールされている場合、そのデバイスは非準拠としてマークされます。

  - **[アプリ名]** - バンドル ID の識別を容易にするわかりやすい名前を入力します。
  - **[アプリ バンドル ID]** - アプリ プロバイダーによって割り当てられた一意のバンドル ID を入力します。 バンドル ID を検索するには、「[How to find the bundle ID for an iOS app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app)」 (iOS アプリのバンドル ID を検索する方法) を参照してください (別の Microsoft Web サイトが開きます)。  

## <a name="next-steps"></a>次の手順

- [非準拠デバイスに対するアクションを追加](actions-for-noncompliance.md)し、[スコープのタグを使用してポリシーをフィルター処理する](../fundamentals/scope-tags.md)
- [コンプライアンス ポリシーを監視します](compliance-policy-monitor.md)。
- [macOS デバイス向けのコンプライアンス ポリシー設定](compliance-policy-create-mac-os.md)を確認します。
