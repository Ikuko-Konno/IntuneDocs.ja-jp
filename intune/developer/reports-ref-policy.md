---
title: ポリシー エンティティのリファレンス
titleSuffix: Microsoft Intune
description: Intune データ ウェアハウス API のエンティティ コレクションのポリシー カテゴリに関するリファレンス トピック。
keywords: Intune データ ウェアハウス
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 64fc1bab596715be80fd3a91c003cac1176fe787
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72490265"
---
# <a name="reference-for-policy-entities"></a>ポリシー エンティティのリファレンス

**ポリシー** カテゴリには、次のような情報を追跡するモバイル デバイスのエンティティが含まれています。

- デバイス構成プロファイル、アプリ構成プロファイル、およびコンプライアンス ポリシーのインベントリ  
- 成功、保留中、失敗、またはエラー状態のデバイス数/日  
- 成功、保留中、失敗、またはエラー状態のユーザー数/日  
- 成功、保留中、失敗、またはエラー状態のデバイスの累積数  

## <a name="policies"></a>policies

**policy** エンティティには、デバイス構成プロファイル、アプリ構成プロファイル、およびコンプライアンス ポリシーがリストされています。 モバイル デバイス管理 (MDM) を含むポリシーを社内のグループに割り当てることができます。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| policyKey |データ ウェアハウス内のポリシーを表す一意のキー。 |123 |
| policyId |データ ウェアハウス内のポリシーを示す一意識別子。 |b66bc706-ffff-7437-0340-032819502773 |
| policyName |ポリシーの名前。 |"Windows 10 Baseline" |
| policyVersion |ポリシーのバージョン。 ポリシーを編集または変更すると、新しいバージョンが作成されます。 |1, 2, 3 |
| isDeleted |ポリシー レコードが更新されているかどうかを示します。  <br>True - ポリシーには、フィールドが更新された新しいレコードがあります。 <br>False - ポリシーの最新のレコードです。 |真/偽 |
| startDateInclusiveUTC |ポリシーがデータ ウェアハウスで作成されたときの UTC 日時。 |11/23/2016 12:00:00 AM |
| deletedDateUTC |IsDeleted が True に変更されたときの UTC 日時。 |11/23/2016 12:00:00 AM |
| rowLastModifiedDateTimeUTC |ポリシーがデータ ウェアハウスで最後に変更されたときの UTC 日時。 |11/23/2016 12:00:00 AM |

## <a name="policytypes"></a>policyTypes

**policyType** エンティティには、デバイス構成プロファイル、アプリ構成プロファイル、およびコンプライアンス ポリシーの種類がリストされています。 モバイル デバイス管理 (MDM) を含むポリシーを社内のグループに割り当てることができます。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| policyTypeId |ソース システムのポリシーを示す一意識別子。 |123 |
| policyTypeKey |データ ウェアハウス内のポリシーを示す一意識別子。 |1 |
| policyTypeName |ポリシーの種類の名前 |Windows 10 のコンプライアンス ポリシー。 |

## <a name="device-configuration"></a>デバイス構成

**deviceConfigurationProfileDeviceActivity** エンティティには、成功、保留中、失敗、エラー状態の**デバイス**数/日がリストされています。 この数は、エンティティに割り当てられているデバイス構成プロファイルを反映しています。 たとえば、割り当てられているすべてのポリシーで**デバイス**が成功状態の場合、その日の成功カウンターが 1 つ増えます。 成功状態のプロファイルとエラー状態のプロファイルという 2 つのプロファイルがデバイスに割り当てられている場合、エンティティは成功カウンターを増やし、デバイスをエラー状態にします。 エンティティには、過去 30 日間の各状態のデバイス数/日が表示されます。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| dateKey |デバイス構成プロファイル チェックインがデータ ウェアハウスに記録されたときの日付キー。 |20160703 |
| pending |保留状態の一意のデバイス数。 |123 |
| 成功 |成功状態の一意のデバイス数。 |12 |
| エラー |エラー状態の一意のデバイス数。 |10 |
| 失敗 |失敗状態の一意のデバイス数。 |2 |

**deviceConfigurationProfileUserActivity** エンティティには、成功、保留中、失敗、エラー状態の**ユーザー**数/日がリストされています。 この数は、エンティティに割り当てられているデバイス構成プロファイルを反映しています。 たとえば、割り当てられているすべてのポリシーで**ユーザー**が成功状態の場合、その日の成功カウンターが 1 つ増えます。 ユーザーに、成功状態のプロファイルとエラー状態のプロファイルの 2 つのプロファイルが割り当てられている場合、エラー状態のユーザーがカウントされます。  **deviceConfigurationProfileUserActivity** エンティティには、過去 30 日間の各状態のユーザー数/日がリストされています。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| dateKey |デバイス構成プロファイル チェックインがデータ ウェアハウスに記録されたときの日付キー。 |20160703 |
| pending |保留状態の一意のユーザー数。 |123 |
| 成功 |成功状態の一意のユーザー数。 |12 |
| エラー |エラー状態の一意のユーザー数。 |10 |
| 失敗 |失敗状態の一意のユーザー数。 |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

**policyTypeActivity** エンティティには、成功、保留中、失敗、またはエラー状態のデバイスの累積数がリストされています。 デバイス構成プロファイル、アプリ構成プロファイル、またはコンプライアンス ポリシーについて、これらの状態が 1 日単位で表示されます。

| プロパティ  | 説明 | 例 |
|---------|------------|--------|
| dateKey |デバイス構成プロファイルのチェックインがデータ ウェアハウスに記録されたときの dateKey。 |20160703 |
| policyKey |policyKey。ポリシーと結合させて policyName を取得できます。 |Windows 10 baseline |
| policyTypeKey |ポリシー キーの種類とポリシーの種類を結合してポリシーの種類名を取得できます。 |Windows10 のコンプライアンス ポリシー |
| pending |保留状態の一意のデバイス数。 |123 |
| 成功 |成功状態の一意のデバイス数。 |12 |
| エラー |エラー状態の一意のデバイス数。 |10 |
| 失敗 |失敗状態の一意のデバイス数。 |2 |

## <a name="compliance-policy"></a>コンプライアンス ポリシー

コンプライアンス ポリシー API リファレンスには、デバイスに割り当てられているコンプライアンス ポリシーに関する状態情報を提供するエンティティが含まれています。

### <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities

次の表は、コンプライアンス ポリシーのデバイスへの割り当ての状態をまとめたものです。 見つかったコンプライアンスの状態ごとにデバイスの数を一覧表示します。


|プロパティ     |説明  |例  |
|---------|---------|---------|
|dateKey  |コンプライアンス ポリシーの概要が作成されたときの日付キー。|20161204 |
|unknown  |何らかの理由でオフラインになっているか、Intune または Azure AD との通信に失敗したデバイスの数。 |5|
|notApplicable      |管理者が適用対象とするデバイス コンプライアンス ポリシーが適用されないデバイスの数。|201 |
|compliant      |管理者が適用対象とする 1 つ以上のデバイス コンプライアンス ポリシーが正常に適用されているデバイスの数。 |4083 |
|inGracePeriod      |準拠していないが、管理者によって定義された猶予期間内にあるデバイスの数。 |57|
|nonCompliant      |管理者が適用対象とする 1 つ以上のデバイス コンプライアンス ポリシーの適用に失敗した、または管理者が適用対象とするポリシーにユーザーが準拠していないデバイスの数。|43 |
|エラー      |Intune または Azure AD との通信に失敗し、エラー メッセージが返されたデバイスの数。 |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities 

次の表は、デバイスへのコンプライアンス ポリシーの割り当ての状態をポリシーごとおよびポリシーの種類ベースごとにまとめたものです。 割り当てられたコンプライアンス ポリシーごとに、各コンプライアンスの状態で見つかったデバイスの数を一覧表示します。



|プロパティ  |説明  |例  |
|---------|---------|---------|
|dateKey  |コンプライアンス ポリシーの概要が作成されたときの日付キー。|20161219|
|policyKey     |概要の作成対象のコンプライアンス ポリシーのキー。 |10178 |
|policyPlatformKey      |概要の作成対象のコンプライアンス ポリシーのプラットフォームの種類のキー。|5|
|unknown     |何らかの理由でオフラインになっているか、Intune または Azure AD との通信に失敗したデバイスの数。|13|
|notApplicable     |管理者が適用対象とするデバイス コンプライアンス ポリシーが適用されないデバイスの数。|3|
|compliant      |管理者が適用対象とする 1 つ以上のデバイス コンプライアンス ポリシーが正常に適用されているデバイスの数。 |45|
|inGracePeriod      |準拠していないが、管理者によって定義された猶予期間内にあるデバイスの数。 |3|
|nonCompliant      |管理者が適用対象とする 1 つ以上のデバイス コンプライアンス ポリシーの適用に失敗した、または管理者が適用対象とするポリシーにユーザーが準拠していないデバイスの数。|7|
|エラー      |Intune または Azure AD との通信に失敗し、エラー メッセージが返されたデバイスの数。 |3|

### <a name="policyplatformtypes"></a>policyPlatformTypes

次の表には、すべての割り当てられたポリシーのプラットフォームの種類が含まれています。 どのデバイスにも割り当てられていないポリシー プラットフォームの種類は、この表には記載されていません。


|プロパティ  |説明  |例  |
|---------|---------|---------|
|policyPlatformTypeKey      |ポリシー プラットフォームの種類の一意のキー。 |20170519 |
|policyPlatformTypeId      |ポリシー プラットフォームの種類の一意の ID。|1|
|policyPlatformTypeName      |ポリシー プラットフォームの種類の名前。|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

次の表に、成功、保留中、失敗、またはエラー状態のデバイス数/日の一覧を示します。 数は、ポリシーの種類のプロファイルごとのデータを反映しています。 たとえば、割り当てられているすべてのポリシーでデバイスが成功状態の場合、その日の成功カウンターが 1 つ増えます。 成功状態のプロファイルとエラー状態のプロファイルという 2 つのプロファイルがデバイスに割り当てられている場合、エンティティは成功カウンターを増やし、デバイスをエラー状態にします。 policyDeviceActivity エンティティには、過去 30 日間の各状態のデバイス数/日がリストされています。

|プロパティ  |説明  |例  |
|---------|---------|---------|
|dateKey|デバイス構成プロファイル チェックインがデータ ウェアハウスに記録されたときの日付キー。|20160703|
|pending|保留状態の一意のデバイス数。|123|
|成功|成功状態の一意のデバイス数。|12|
|policyKey|policyKey。ポリシーと結合させて policyName を取得できます。|Windows 10 baseline|
|エラー|エラー状態の一意のデバイス数。|10|
|失敗|失敗状態の一意のデバイス数。|2|

### <a name="policyuseractivities"></a>policyUserActivities

次の表に、成功、保留中、失敗、またはエラー状態のユーザー数/日の一覧を示します。 数は、ポリシーの種類のプロファイルごとのデータを反映しています。 たとえば、割り当てられているすべてのポリシーでユーザーが成功状態の場合、その日の成功カウンターが 1 つ増えます。 ユーザーに、成功状態のプロファイルとエラー状態のプロファイルの 2 つのプロファイルが割り当てられている場合、エラー状態のユーザーがカウントされます。 PolicyUserActivity エンティティには、過去 30 日間の各状態のユーザー数/日が表示されます。


| プロパティ  |                                         説明                                         |       例       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  dateKey  | デバイス構成プロファイル チェックインがデータ ウェアハウスに記録されたときの日付キー。 |      20160703       |
|  pending  |                         保留状態の一意のデバイス数。                          |         123         |
| 成功 |                         成功状態の一意のデバイス数。                          |         12          |
| policyKey |                 policyKey。ポリシーと結合させて policyName を取得できます。                 | Windows 10 baseline |
|   エラー   |                          エラー状態の一意のデバイス数。                           |         10          |

