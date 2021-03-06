---
title: Microsoft에 스팸, 스팸이 아닌 메시지 및 피싱 메시지 보고
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 관리자는 분석을 위해 Microsoft에 양호하고 잘못된 메시지와 파일을 보고하는 다양한 방법에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21c733945256386ff9543b372badaa6f2302171b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288094"
---
# <a name="report-messages-and-files-to-microsoft"></a>Microsoft에 메시지와 파일 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 사용자와 관리자 모두 Microsoft에 전자 메일 메시지와 파일을 보고하는 여러 가지 방법이 있습니다.

****

|메서드|설명|
|---|---|
|[관리자 제출을 사용하여 의심스러운 스팸, 피싱, URL 및 파일을 Microsoft에 제출](admin-submission.md)|Exchange Online 사서함이 있는 조직의 관리자에게 권장되는 보고 방법(독립 실행형 EOP에서는 사용할 수 없습니다).|
|[보고서 메시지 추가 기능을 사용하도록 설정](enable-the-report-message-add-in.md)|Outlook 및 웹용 Outlook(이전의 웹용 Outlook)에서 Outlook Web App. <p> 구독에 따라 사용자가 추가 기능으로 보고한 메시지는 [Admin Submissions 포털,](admin-submission.md)자동화된 조사 [](view-email-security-reports.md#user-reported-messages-report)및 [응답(AIR)](air-view-investigation-results.md)결과, 사용자가 보고한 메시지 보고서 및 [위협](threat-explorer-views.md#email--submissions)탐색기에서 사용할 수 있습니다. <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)
|[보고서 피싱 추가 기능을 사용하도록 설정](enable-the-report-phish-add-in.md)|Outlook 및 웹용 Outlook(이전의 웹용 Outlook)에서 Outlook Web App. <p> 구독에 따라 사용자가 추가 기능으로 보고한 메시지는 [Admin Submissions 포털,](admin-submission.md)자동화된 조사 [](view-email-security-reports.md#user-reported-messages-report)및 [응답(AIR)](air-view-investigation-results.md)결과, 사용자가 보고한 메시지 보고서 및 [위협](threat-explorer-views.md#email--submissions)탐색기에서 사용할 수 있습니다. <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)|
|[Microsoft Outlook용 정크 메일 보고 추가 기능 설치 및 사용](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook에서만 작동합니다.|
|[웹에서 Outlook에서 정크 메일 및 피싱 메일 보고](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online 사서함이 있는 조직(독립 실행형 EOP에서는 사용할 수 없는)을 위해 웹용 Outlook의 기본 제공 기능을 사용하세요. <p> 사용자가 보고하는 메시지는 관리 제출 [포털에서 사용할 수 있습니다.](admin-submission.md) <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)|
|[iOS 및 Android용 Outlook에서 정크 메일 및 피싱 메일 보고](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Exchange Online 사서함이 있는 조직의 경우 iOS 및 Android용 Outlook의 기본 제공 기능을 사용하세요(독립 실행형 EOP에서는 사용할 수 없습니다). <p> 사용자가 보고하는 메시지는 관리 제출 [포털에서 사용할 수 있습니다.](admin-submission.md) <p> 보고된 메시지를 지정한 사서함으로 복사하거나 리디렉션하도록 구성할 수 있습니다. 자세한 내용은 사용자 제출 [정책을 참조하세요.](user-submission.md)|
|[분석을 위해 Microsoft에 수동으로 메시지 제출](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|스팸 및 피싱이 아닌 스팸을 위해 특정 Microsoft 전자 메일 주소로 첨부된 메시지를 수동으로 전송합니다.|
|[메일 흐름 규칙을 사용하여 사용자가 Microsoft에 보고한 내용 확인](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|사용자가 분석을 위해 Microsoft에 메시지를 보고할 때 이를 알 수 있는 메일 흐름 규칙(전송 규칙)을 만드는 방법을 학습합니다.|
|[분석을 위해 맬웨어 및 맬웨어가 아닌 맬웨어를 Microsoft에 제출](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft 보안 인텔리전스 사이트를 사용하여 첨부 파일 및 기타 파일을 제출합니다.|

스팸 또는 피싱 메시지가 배달되지 않고도 끊어졌다면 사용자는 보안 및 준수 센터의 Quarantine Portal에서 Microsoft에 메시지를 & 수 있습니다. 자세한 내용은 [Microsoft 365에서](find-and-release-quarantined-messages-as-a-user.md)사용자로 고지된 메시지 찾기 및 릴리스를 참조합니다.

> [!NOTE]
> Microsoft로 전송되는 데이터는 북미 데이터 센터의 Office 365 규정 준수 경계에 있습니다. 이 데이터는 엔지니어링 팀의 분석가가 필터의 효율성을 높이기 위해 검토합니다.
