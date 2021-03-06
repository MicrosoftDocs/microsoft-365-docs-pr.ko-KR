---
title: 암호화된 전자 메일 보내기
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook을 사용하여 암호화된 전자 메일을 보내는 방법을 배워야 합니다.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044219"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>중요한 전자 메일을 암호화하거나 레이블을 지정합니다.

데이터 및 캠페인 정보는 중요하고 종종 기밀입니다. 암호화 및 민감도 레이블을 사용하여 이 중요한 정보를 보호하여 사용자와 전자 메일 받는 사람이 정보를 필요한 민감도로 취급할 수 있도록 합니다.

## <a name="best-practices"></a>모범 사례

기밀 또는 중요한 정보가 있는 전자 메일을 보내기 전에 다음을 켜는 것이 있습니다.

- **암호화:** 전자 메일의 정보 개인 정보를 보호하기 위해 전자 메일을 암호화할 수 있습니다. 전자 메일 메시지를 암호화하면 읽을 수 있는 일반 텍스트에서 스크램블된 키프 텍스트로 변환됩니다. 메시지를 암호화하는 데 사용되는 공개 키와 일치하는 개인 키가 있는 받는 사람만 메시지를 읽을 수 있습니다. 그러나 해당 개인 키가 없는 받는 사람은 검색할 수 없는 텍스트를 볼 수 있습니다. 관리자는 특정 조건을 충족하는 메시지를 자동으로 암호화하는 규칙을 정의할 수 있습니다. 예를 들어 관리자는 조직 외부로 전송된 모든 메시지 또는 특정 단어나 구를 언급하는 모든 메시지를 암호화하는 규칙을 만들 수 있습니다. 암호화 규칙은 자동으로 적용됩니다.
- **민감도 레이블:** 또한 캠페인은 파일 및 전자 메일에 적용할 수 있는 민감도 레이블을 설정하여 캠페인의 정보 보호 정책을 준수하도록 할 수 있습니다. 레이블을 설정하면 레이블이 전송된 경우에도(예: 메시지에 헤더로 표시) 전자 메일과 함께 지속됩니다.

![레이블 및 암호화에 대한 설명이 있는 전자 메일 다이어그램](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>설정하기

미리 정의된 규칙을 충족하지 않는 메시지를 암호화하거나 관리자가 규칙을 설정하지 않은 경우 메시지를 보내기 전에 다양한 암호화 규칙을 적용할 수 있습니다. Outlook 2013 또는 2016 또는 Mac용 Outlook 2016에서 암호화된 메시지를 보내기 위해 옵션 > 사용 권한을 선택한 다음 필요한 보호 옵션을 선택합니다.  웹에서 Outlook의 보호 단추를 선택하여  암호화된 메시지를 보낼 수도 있습니다. 자세한 내용은 PC용 Outlook에서 암호화된 메시지 보내기, 보기 및 [회신을 참조하세요.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>관리자 설정

[Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)전자 메일 암호화에서 전자 메일 암호화를 설정하는 방법을 모두 학습할 수 있습니다.

### <a name="automatically-encrypt-email-messages"></a>전자 메일 메시지 자동 암호화

관리자는 메일 흐름 규칙을 만들어 캠페인에서 보내고 받은 전자 메일 메시지를 자동으로 보호할 수 있습니다. 발신 전자 메일 메시지를 암호화하고 조직 내부에서 오는 암호화된 메시지에서 암호화를 제거하거나 조직에서 보낸 암호화된 메시지에 대한 답장에서 암호화를 제거하는 규칙을 설정합니다.

새 Office 365 OME(메시지 암호화) 기능을 사용하여 전자 메일 메시지를 암호화하는 메일 흐름 규칙을 만들 수 있습니다. EAC(Exchange 관리 센터)를 사용하여 새 OME 기능을 사용하여 메시지 암호화를 트리거하기 위한 메일 흐름 규칙을 정의합니다. 

1. 웹 브라우저에서 전역 관리자 권한이 부여된 직장 또는 학교 계정을 사용하여 로그인합니다.
2. 관리 타일을 선택 합니다.
3. In the admin center, choose **Admin centers > Exchange.**

자세한 내용은 전자 메일 메시지를 암호화하는 메일 흐름 [규칙 정의를 참조하십시오.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

### <a name="brand-your-encryption-messages"></a>암호화 메시지 브랜드

캠페인 브랜드를 적용하여 전자 메일 메시지의 모양과 텍스트를 사용자 지정할 수도 있습니다. 자세한 내용은 암호화된 메시지에 조직의 브랜드 [추가를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
