---
title: Microsoft Intune での Windows 10 用の配信の最適化設定 - Azure | Microsoft Docs
description: Intune で管理する Windows 10 デバイスで配信の最適化を使用する方法を構成します。 Intune では、デバイス構成プロファイルを作成してインターネットから更新プログラムをインストールします。 また、既存の更新プログラム リングを配信の最適化プロファイルに置き換える方法についても確認します。
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 44078f61e4f1939b1f0b15b3dde5ac54938ffbc3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059976"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Microsoft Intune での配信の最適化設定

Intune では、ご利用の Windows 10 デバイスに合わせて配信の最適化の設定を使用することで、そのデバイスでアプリケーションおよび更新プログラムをダウンロードする際に消費される帯域幅を削減することができます。 配信の最適化は、ご利用のデバイスの構成プロファイルの一部として構成されます。  

この記事では、デバイスの構成プロファイルの一部として配信の最適化の設定を構成する方法について説明します。 プロファイルを作成したら、次に、そのプロファイルをご利用の Windows 10 デバイスに割り当てるか、展開します。 

Intune でサポートされる配信の最適化の設定の一覧については、「[Intune の配信の最適化の設定](../delivery-optimization-settings.md)」を参照してください。  

Windows 10 での配信の最適化について学習するには、Windows ドキュメントの[配信の最適化更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)に関するページを参照してください。  

> [!NOTE]
> **[ソフトウェア更新プログラム] – [Windows 10 更新プログラムのリング]** は、 **[配信の最適化]** 設定によって置き換えられます。 **[配信の最適化]** 設定を使用するように既存の更新リングを変更できます。 「[既存の更新リングを配信の最適化に移動する](#move-existing-update-rings-to-delivery-optimization)」(この記事)。

## <a name="create-the-profile"></a>プロファイルの作成

1. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。

2. **[デバイス]** 、 **[構成プロファイル]** 、 **[プロファイルの作成]** の順に選択します。

3. 次のプロパティを入力します。

    - **[名前]** :新しいプロファイルのわかりやすい名前を入力します。
    - **説明**:プロファイルの説明を入力します。 この設定は省略可能ですが、推奨されます。
    - **[プラットフォーム]** : **[Windows 10 以降]** を選択します。
    - **[プロファイルの種類]** : **[配信の最適化]** を選択します。

4. **[設定]** 、 **[構成]** の順に選択し、更新プログラムやアプリをダウンロードする方法を定義します。 使用可能な設定については、「[Intune の配信の最適化の設定](../delivery-optimization-settings.md)」を参照してください。

5. 完了したら、 **[OK]**  >  **[作成]** の順に選択して変更を保存します。

プロファイルが作成され、一覧に表示されます。 次に、[プロファイルを割り当て](device-profile-assign.md)てから、[その状態を監視](device-profile-monitor.md)します。

## <a name="move-existing-update-rings-to-delivery-optimization"></a>既存の更新リングを配信の最適化に移動する

**[ソフトウェア更新プログラム] – [Windows 10 更新プログラムのリング]** は、 **[配信の最適化]** 設定によって置き換えられます。 既存の更新プログラム リングは、 **[配信の最適化]** 設定を使うように簡単に変更できます。 配信の最適化のプロファイルを作成するときに同じ設定を維持するには、同じ*配信の最適化ダウンロード モード*を使用し、さらに既に使用しているものと同じ設定内容を設定します。 ただし、配信の最適化のプロファイルで管理できるあらゆる追加設定を活用できるように、配信の最適化の設定を再構成することもできます。

1. 配信の最適化の構成プロファイルを作成します。

    1. Microsoft Endpoint Manager 管理センターで、 **[デバイス]**  >  **[構成プロファイル]**  >  **[プロファイルの作成]** の順に選択します。
    2. 次のプロパティを入力します。

        - **[名前]** :新しいプロファイルのわかりやすい名前を入力します。
        - **説明**:プロファイルの説明を入力します。 この設定は省略可能ですが、推奨されます。
        - **[プラットフォーム]** : **[Windows 10 以降]** を選択します。
        - **[プロファイルの種類]** : **[配信の最適化]** を選択します。
        - **設定**:**配信の最適化ダウンロード モード**については、ご利用のデバイスに適用する設定を変更する必要がない限り、既存のソフトウェア更新プログラム リングで使用されているものと同じモードを選択します。 次のようなオプションがあります。
            - **未構成**
            - **HTTP のみ、ピアリングなし**
            - **HTTP blended with peering behind the same NAT (HTTP と同じ NAT でのピアリングの組み合わせ)**
            - **HTTP blended with peering across a private group (HTTP とプライベート グループでのピアリングの組み合わせ)**
            - **HTTP とインターネット ピアリングの組み合わせ**
            - **ピアリングなしの簡易ダウンロード モード**
            - **バイパス モード**
    3. 管理したい追加設定を構成します。

2. 既存のソフトウェア更新プログラム リングと同じデバイスおよびユーザーに、この新しいプロファイルを割り当てます。 [プロファイルの割り当て](device-profile-assign.md)に関するページに手順が記載されています。

3. 既存のソフトウェアのリングの構成を解除します。
    1. Microsoft Endpoint Manager 管理センターで、 **[ソフトウェア更新]** > [Windows 10 更新リング] の順に進みます。
    2. 一覧から更新プログラム リングを選択します。
    3. 設定で、 **[配信の最適化ダウンロード モード]** を **[未構成]** に設定します。
    4. **[Ok]**  >  変更を **[保存]** します。

## <a name="next-steps"></a>次の手順

[プロファイルを割り当て](device-profile-assign.md)、[その状態を監視](device-profile-monitor.md)します。  
Intune 用の[配信の最適化の設定](../delivery-optimization-settings.md)を表示します。
