---
title: Intune ポータル サイトで Android デバイスを登録する | Microsoft Docs
description: Intune ポータル サイトで Android デバイスを登録する方法について説明します
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5baf0e9079cc148101a68e5cd2d3a4ed500f567f
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414840"
---
# <a name="enroll-your-device-with-company-portal"></a>Intune ポータル サイトでデバイスを登録する  
自分個人または会社所有の Android デバイスを登録して、会社のメール、アプリ、データにアクセスします。 Intune ポータル サイトでは、Android 4.4 以降が実行されている Samsung Knox などの Android デバイスがサポートされています。  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung KNOX は、ネイティブ Android に用意されている以外の追加保護のために特定の Samsung 製のデバイスで使用されるセキュリティの一種です。 Samsung KNOX デバイスかどうかを確認するには、 **[設定]**  >  **[About device]\(デバイス情報\)** を選択します。 そこに **[KNOX version]\(KNOX バージョン\)** と表示されない場合は、ネイティブ Android デバイスです。

## <a name="enroll-device"></a>デバイスを登録する  
必ず、[無料の Intune ポータル サイト アプリを Google Play からインストール](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)します。 

登録中に、デバイスの使用方法に適したカテゴリを選ぶように求められる場合があります。 会社のサポートは、その回答を使用して、ユーザーがアクセスできるアプリを確認します。  

1. Intune ポータル サイト アプリを開き、職場または学校アカウントでサインインします。  

2. 組織の使用条件への同意を求められたら、 **[すべて受け入れる]** をタップします。  

   ![[ポータルサイトの例] 画面で、[すべて受け入れる] ボタンを強調表示した画像の例。](./media/accept-terms-1911.png)  


3. 組織の内容を確認してください。 その後、 **[続行]** をタップします。


    ![ポータルサイトの画像の例として、[続行] ボタンを強調表示しているプライバシー画面に注目します。](./media/android-privacy-screen-1911.png)  
4. 次の手順で、予期される内容を確認します。 **[次へ]** をタップします。  

    ![[次へ] ボタンを強調表示しているポータルサイトの画像の例 (次の画面)。](./media/android-whats-next-1911.png)  


5. Android のバージョンによっては、デバイスの特定の部分へのアクセスを許可するように求められる場合があります。 これらのプロンプトは Google によって要求され、Microsoft によって管理されることはありません。  

    次のアクセス許可に対して **[許可]** をタップします。  
    * 通話の**作成と管理にポータルサイトを許可する**: このアクセス許可は、デバイスが国際携帯電話局識別番号 (IMEI) を組織のデバイス管理プロバイダーである Intune と共有できるようにします。 このアクセス許可は安全に許可されています。 Microsoft は電話をかけたり管理したりすることはありません。  
    * **連絡先へのアクセスを許可するポータルサイト**: このアクセス許可では、ポータルサイトアプリで職場アカウントの作成、使用、および管理を行うことができます。  このアクセス許可は安全に許可されています。 Microsoft はお客様の連絡先にアクセスすることはありません。 

    アクセス許可を拒否すると、次回ポータルサイトにサインインするときに、再度メッセージが表示されます。 今後このメッセージが表示されないようにするには、 **[今後このメッセージを表示しない]** を選択します。 アプリのアクセス許可を管理するには、設定 アプリ > **アプリ** > **ポータルサイト** > **アクセス許可** > **Phone** にアクセスします。  

6. デバイス管理アプリをアクティブ化します。 

    デバイスを安全に管理するには、ポータルサイトにデバイス管理者のアクセス許可が必要です。 アプリをアクティブ化すると、デバイスのロック解除が繰り返し失敗した場合など、潜在的なセキュリティの問題を組織が特定し、適切に応答できるようになります。  

    ![[デバイス管理者のアクティブ化] 画面のイメージの例で、[アクティブ化] ボタンを強調表示します。](./media/activate-device-administrator-1911.png)  

> [!NOTE]
> この画面では、メッセージングは制御されません。 私たちは、言い回しがやや重大なものであることを理解しています。 組織に関連する制限とアクセス権を指定ポータルサイトことはできません。 組織でのアプリの使用方法について不明な点がある場合は、IT サポート担当者にお問い合わせください。 組織の連絡先情報を検索するには、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)に移動してください。  


7. デバイスの登録が開始されます。 Samsung Knox デバイスを使用している場合は、最初に ELM エージェントのプライバシーポリシーを確認して同意するように求められます。   

    ![登録時に表示される Samsung Knox privacy policy 画面の例。](./media/and-enroll-7-knox-privacy-policy.png)  

8. **[会社アクセスのセットアップ]** 画面で、デバイスが登録されていることを確認します。 その後、 **[続行]** をタップします。  

    ![[会社アクセスのセットアップ] 画面で、[デバイスの管理が完了しました] と表示されているポータルサイトの画像の例。](./media/update-settings-1911.png)  

9. お客様の組織で、デバイス設定の更新が必要になる場合があります。 **[解決]** をタップして設定を調整します。 設定の更新が完了したら、 **[続行]** をタップします。  

   ![[解決] ボタンと [続行] ボタンを強調表示してポータルサイトの画像の例。デバイスの設定を更新します。](./media/resolve-settings-1911.png)  

10. セットアップが完了したら、 **[完了]** をタップします。    

    ![ポータルサイトの [会社アクセスのセットアップ] 画面の画像の例では、セットアップが完了し、[完了] ボタンが強調表示されています。](./media/android-enrollment-done-1911.png) 

## <a name="next-steps"></a>次の手順  

学校または職場のアプリをインストールする前に、[ > **設定**] **[セキュリティ]** にアクセスして、 **[不明なソース]** をオンにします。 このオプションをオンにしない場合、アプリをインストールしようとすると次のメッセージが表示されます: インストールがブロックされました。 セキュリティ上の理由から、デバイスは不明のソースから取得したアプリのインストールをブロックするように設定されています。 メッセージの **[設定]** をタップして、 **[不明なソース]** に直接アクセスできます。  

> [!Note]
> 組織で通信費管理ソフトウェアを使用している場合は、デバイスの登録を完了する前にいくつかの追加手順を実行します。 詳細については、[こちら](enroll-your-device-with-telecom-expense-management-android.md)を参照してください。

Intune にデバイスを登録している最中にエラーが表示された場合は、[会社のサポートにメールを送る](send-logs-to-your-it-admin-by-email-android.md)ことができます。  

サポートが必要な場合は、 社内サポートに問い合わせてください。 連絡先情報については、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)をご確認ください。  