---
title: EMS での BYOD に関する技術の決定事項
description: BYOD を有効にし、Microsoft Enterprise Mobility + Security で企業のデータを保護するための、技術に関する重要な決定事項です。
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/8/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 297926f6-c029-4003-bda4-9ee031d47dda
ms.reviewer: pfetty
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c1666c55455a630b839f1f007fc93e5a3da20832
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509119"
---
# <a name="technology-decisions-for-enabling-byod-with-microsoft-enterprise-mobility--security-ems"></a>Microsoft Enterprise Mobility + Security (EMS) で BYOD を有効にするための技術の決定事項

従業員が自分のデバイスを使ってリモートで作業できるようにする戦略を開発するときは (BYOD)、BYOD を有効にして企業データを保護するためのシナリオで重要な決定を行う必要があります。 幸い、EMS では包括的なソリューション セットにおいて必要なすべての機能が提供されています。  

このトピックでは、企業の電子メールへの BYOD アクセスを有効にする簡単なユース ケースを使って説明します。 デバイス全体とアプリケーションだけのどちらを管理する必要があるかに注目します。いずれも完全に有効な選択肢です。

## <a name="assumptions"></a>前提条件
* Azure Active Directory と Microsoft Intune についての基本的な知識があること
* メール アカウントが Exchange Online でホストされていること

## <a name="common-reasons-to-manage-the-device-mdm"></a>デバイスを管理する場合の一般的な理由 (MDM)
Exchange Online に[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ポリシーを展開することで、デバイス管理へのデバイスの登録をユーザーに簡単に促すことができます。 個人デバイスの管理が必要な理由としては次のようなものがあります。

**WiFi/VPN** – ユーザーが生産性を向上させる企業接続プロファイルを必要としている場合は、シームレスに構成できます。

**アプリケーション** – ユーザーのデバイスにアプリのセットをプッシュする必要がある場合は、シームレスに配信できます。 これには、Mobile Threat Defense アプリのようなセキュリティのために必要なアプリケーションが含まれます。

**コンプライアンス** – 組織によっては、特定の MDM 制御が求められる規制や他のポリシーに準拠することが必要な場合があります。 たとえば、MDM では、デバイス全体を暗号化したり、デバイス上のすべてのアプリのレポートを生成したりする必要があります。

## <a name="common-reasons-to-only-manage-the-apps-mam"></a>アプリのみを管理する場合の一般的な理由 (MAM)
MDM を行わない MAM は、BYOD をサポートする組織で非常によく利用されています。 Exchange Online に条件付きアクセス ポリシーを展開することで、Outlook Mobile (MAM 保護をサポートします) からメールにアクセスするようユーザーに促すことができます。 個人デバイスのアプリのみの管理が必要な理由としては次のようなものがあります。

**ユーザー エクスペリエンス** – MDM の登録には (プラットフォームにより表示される) 多くの警告プロンプトが伴うため、ユーザーが個人のデバイスでメールにアクセスすることをあきらめるという結論に達してしまうことがよくあります。 MAM で表示されるユーザーへの警告はずっと少なく、MAM による保護が適用されていることを伝えるポップアップが 1 回表示されるだけです。

**コンプライアンス** – 組織によっては、個人デバイスでの管理機能を少なくすることを求めるポリシーに準拠することが必要な場合があります。 たとえば、MAM ではアプリから企業データを削除することだけができるのに対し、MDM ではデバイスからすべてのデータを削除できます。

![モバイル デバイスでのデバイス管理とアプリ管理を比較した図](./media/byod-technology-decisions/byod-app-device-mgmt.png)

詳しくは、[デバイス管理とアプリ管理のライフサイクルに関するページ](device-lifecycle.md)をご覧ください。

## <a name="mdm-vs-mam-capability-comparison"></a>MDM と MAM の機能の比較
既に説明したように、条件付きアクセスを使うと、デバイスの登録、または Outlook Mobile などのマネージド アプリの使用をユーザーに促すことができます。 いずれの場合も、次のような他の多くの条件を適用できます。

* アクセスを試みているユーザー
* 信頼できる場所かどうか
* サインイン リスク レベル
* デバイスのプラットフォーム

それでも、多くの組織で心配されている特定のリスクが発生することがよくあります。  次の表は、一般的な懸念事項と、それらにする MDM と MAM の対応の比較をまとめたものです。

| 懸念事項   |   MDM  |   MAM  |
|------------|--------|--------|
|許可されていないデータ アクセス | グループ メンバーシップを要求 | グループ メンバーシップを要求 |
|許可されていないデータ アクセス | デバイスの登録を要求 | 保護されたアプリを要求 |
|許可されていないデータ アクセス | 特定の場所を要求 | 特定の場所を要求 |
| | | |
|侵害されたユーザー アカウント| MFA を要求 | MFA を要求|
|侵害されたユーザー アカウント | リスクの高いユーザーをブロック | リスクの高いユーザーをブロック |
|侵害されたユーザー アカウント | デバイス PIN | アプリ PIN |
| | | |
| 侵害されたデバイスまたはアプリ | 準拠しているデバイスを要求 | アプリ起動時の脱獄チェック |
| 侵害されたデバイスまたはアプリ | デバイス データの暗号化 | [アプリ データの暗号化] |
| | | |
|デバイスの紛失または盗難 | すべてのデバイス データを削除 | すべてのアプリ データを削除|
| | | |
| セキュリティで保護されていない場所への偶発的なデータの共有または保存 | デバイスのデータのバックアップを制限 | 切り取り/コピー/貼り付けを制限|
| セキュリティで保護されていない場所への偶発的なデータの共有または保存 | 名前を指定した保存を制限 | 名前を指定した保存を制限 |
|セキュリティで保護されていない場所への偶発的なデータの共有または保存 | 印刷を無効にする | 該当なし|

## <a name="next-steps"></a>次の手順
デバイス管理、アプリ管理、またはこれらの組み合わせに注目し、組織で BYOD を有効にするかどうかを決定します。 実装を選択するのはユーザーですが、Azure AD の ID およびセキュリティ機能を利用できるのでいずれにしても安心です。  

次のレベルの計画について詳しくは、Intune の[計画ガイド](planning-guide.md)をご覧ください。
