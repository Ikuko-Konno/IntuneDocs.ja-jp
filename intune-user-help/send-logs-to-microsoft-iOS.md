---
title: iOS ログを Microsoft 開発者に送信する | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 733a590e-836f-4941-bfd9-6ae53ba25e06
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 13a6e9219c29b33404c2489bb6b60de513369e74
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502092"
---
# <a name="send-logs-to-the-company-portal-developers-for-ios-devices"></a>ログを iOS デバイス向けポータル サイトの開発者に送信する | Microsoft Docs

ポータル サイト アプリが、予期せず終了することがあります。 これは、マイクロソフトがお客様の操作性を向上させ、このような問題が今後発生しないようにするために、アプリの開発者がお客様からのご意見を待ち望んでいる問題です。 この情報は、デバイスの _diagnostic log_ という名前の特殊なドキュメントに保存されています。

この問題が発生した場合、ポータル サイト チームは根本原因を探し、診断するための情報が必要になります。 ここで実行する必要がある操作は、次のとおりです。

1. 問題の再現を試みてください。 できなくても問題ありませんが、再現できると次の手順が簡単になります。
2. __[設定]__  >  __[プライバシー]__  >  __[分析]__  >  __[分析データ]__ の順に移動します。 これは、クラッシュから一般的な使用パターンまで、発生したアプリ アクティビティの一覧です。個人情報は含まれていません。 この一覧は、最も新しいものから順番に表示されます。 この問題を再現できなかった場合、これが、このページのアプリ アクティビティの一覧に表示される最初の項目になります。 問題を再現できなかった場合、"ポータル サイト" で始まる最初の項目が見つかるまで下へスクロールし、見つかったらタップして開きます。
3. キーを押したまま、レポート内のすべてのテキストが選択されるまで、小さい青いドットを上下にドラッグします。 ポップアップ メニューの __[コピー]__ をタップします。
4. 電子メール アプリを開き、電子メールの本文にその内容を貼り付けます。 電子メールを <a href="mailto:IntuneCPiOSfeedback@microsoft.com?subject=My Company Portal App Closed Unexpectedly&body=Press and hold, then paste your copied Company Portal app logs here.">IntuneCPiOSfeedback@microsoft.com</a> に送信します。

サポートが必要な場合は、 社内サポートに問い合わせてください。 連絡先情報については、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)をご確認ください。
