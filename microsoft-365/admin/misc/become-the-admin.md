---
title: 내부 관리자 인계 수행
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365에서 관리되지 않는 테넌트의 소유를 확인하기 위해 전자 메일 및 도메인 소유권을 확인하는 방법을 배우기
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658066"
---
# <a name="perform-an-internal-admin-takeover"></a>내부 관리자 인계 수행

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 

관리자가 셀프 서비스 사용자 등록으로 만든 관리되지 않는 테넌트의 인계를 원하는 경우 내부 관리자 인계를 통해 이 작업을 할 수 있습니다.

> [!NOTE]
> Azure AD를 사용하는 모든 클라우드 서비스에 대한 셀프 서비스 등록은 사용자를 관리되지 않는 또는 "섀도" Azure AD 디렉터리에 추가하고 관리되지 않는 테넌트를 생성합니다. 관리되지 않는 테넌트는 전역 관리자가 없는 디렉터리입니다. 테넌트가 관리되는지 또는 관리되지 않는지 확인 내용은 테넌트 유형 [확인을 참조합니다.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>1단계: 전자 메일 주소 확인

> [!NOTE]
> 테넌트에서 셀프 서비스가 사용하도록 설정된 경우 사용자는 직접 Power BI와 같은 무료 서비스를 구독할 수 있습니다. 이 단계에서는 셀프 서비스 사용자 구독이 관리자로 인계할 관리되지 않는 테넌트가 만들어졌다고 가정합니다. 첫 번째 단계에서는 관리되지 않는 테넌트에서 Power BI를 사용하여 관리자 인계 경로를 보여 주는 사용자 컨텍스트를 생성합니다.

1. Power BI에 등록하려면 Power [BI](https://powerbi.com) 사이트로 이동하여 무료 시작 무료 평가판 시작(Power BI Pro와 공유  >   상자)을 선택합니다. 

2. 조직의 도메인 이름(예: )을 사용하는 사용자 계정으로 `powerbiadmin@contoso.com` 등록합니다. 계정이 이미 사용 중인 경우 현재 암호를 사용하여 로그인합니다.

3. 전자 메일에서 확인 코드를 **확인하고** 코드를 입력하여 전자 메일 주소의 유효성을 검사합니다.
    
## <a name="step-2-create-a-new-account"></a>2단계: 새 계정 만들기

1. 인증 코드를 입력하면 새 계정을 만들 수 있는 페이지로 이동됩니다. 
    
2. 사용할 계정으로 사용자 이름 및 암호 필드를 입력한 다음 시작을 **선택합니다.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>3단계: 도메인 소유권 확인 및 관리자 되기

1. 관리자 **되기 마법사가** 열립니다. 마법사가 시작되지 않는 경우 관리  타일을 찾아 선택합니다. 

2. Select **Yes, I want to be the admin.**

3. 도메인 등록 기관에 TXT 레코드를 추가하여 인계할 도메인을 소유하고 있는지 확인해야 합니다. 마법사는 추가할 TXT 레코드를 제공할 뿐만 아니라 등록 기관의 웹 사이트에 대한 링크와 단계별 지침에 대한 링크를 제공합니다.
    
4. 등록자 사이트에 TXT 레코드를 추가한 후 마법사로 돌아가서 레코드를 **추가했습니다.**
    
> [!NOTE]
> 섀도 테넌트의 인계는 기존 정보나 서비스에 영향을 미치지 않습니다. 그러나 도메인의 사용자가 라이선스가 필요한 서비스에 등록한 경우 관리자 역할 인계의 일부로 해당 사용자의 라이선스를 구입해야 합니다. 관리자 설치 프로세스가 완료되면 라이선스를 구입하거나 제거할 수 있습니다.
  
## <a name="related-articles"></a>관련 문서

YouTube: Power BI 및 [Microsoft 365에 대한 IT 관리자 인계를 수행하기 위한 3단계](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD의 관리자 인계](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[조직에서 셀프 서비스 등록 사용](self-service-sign-up.md)
  
[Power BI 서비스 관리자 역할 이해](https://docs.microsoft.com/power-bi/service-admin-role)

