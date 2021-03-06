---
title: 준비 평가 도구
description: 두 도구, 실행 검사 및 결과의 의미에 대해 설명
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 0311450386f3b7c9f950276340901daacc06b2a8
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453942"
---
# <a name="readiness-assessment-tools"></a>준비 평가 도구

Microsoft Managed Desktop에 등록할 때 최대한 원활한 환경을 위해 설정 및 기타 매개 변수와 특정 장치 및 네트워크 요구 사항을 충족해야 합니다. Microsoft Managed Desktop Admin 포털을 통해 액세스하는 한 도구는 관리 관련 설정을 확인합니다. 다운로드 가능한 다른 도구는 개별 장치 요구 사항 및 네트워크 설정을 확인합니다. 이러한 도구를 사용하여 이러한 설정을 확인하고 올바른 설정이 아닌 설정을 수정하기 위한 자세한 단계를 받을 수 있습니다.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>장치 및 네트워크에 대한 다운로드 가능한 준비 평가 검사

다운로드 가능한 준비 평가 검사기 사용에 대한 자세한 내용은 다운로드 가능한 준비 평가 검사 를 [참조합니다.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>관리 설정을 위한 온라인 준비 평가 도구

온라인 [도구는](https://aka.ms/mmdart) Microsoft 끝점 관리자(특히 Microsoft Intune), Azure AD(Azure Active Directory) 및 Microsoft 365의 설정을 확인하여 Microsoft Managed Desktop에서 작동할지 확인합니다. Microsoft Managed Desktop은 Azure AD 조직(테넌트)에서 검사를 마지막으로 실행한 후 12개월 동안 이러한 검사와 관련된 데이터를 보존합니다. 12개월 후에 비식별된 양식으로 보존됩니다. 수집하는 데이터를 삭제할 수 있습니다.

전역 읽기 권한자 또는 Intune 관리자 역할이 있는 모든 사용자가 이 도구를[](readiness-assessment-fix.md#conditional-access-policies) 실행할 수 있지만 [](readiness-assessment-fix.md#multifactor-authentication) 조건부 액세스 정책 및 다단계 인증의 두 가지 확인에는 추가 권한이 필요합니다.
 
평가 도구는 다음 항목을 검사합니다.

## <a name="microsoft-intune-settings"></a>Microsoft Intune 설정

|수표  |설명  |
|---------|---------|
|Autopilot 배포 프로필     | Autopilot 배포 프로필 할당이 모든 장치에 적용되지 않는지 확인(프로필을 Microsoft Managed Desktop 장치에 할당하면 안 됩니다.)        |
|인증서 커넥터     | 인증서 커넥터의 상태를 확인하여 커넥터가 활성 상태인지 확인   |
|조건부 액세스     | 조건부 액세스 정책이 모든 사용자에게 할당되지 않았는지  확인(조건부 액세스 정책을 Microsoft Managed Desktop 서비스 계정에 할당하지 말아야 합니다.)    |
|장치 준수 정책     | Intune 규정 준수 정책이 모든 사용자에게 할당되지  않는지 검사합니다(정책을 Microsoft Managed Desktop 장치에 할당하면 안 됩니다.)    |
|장치 구성 프로필     | 구성 프로필이 모든 사용자 또는 모든 장치에 할당되지 않는지  확인(구성 프로필을 Microsoft Managed Desktop 장치에 할당하지 말아야 합니다.)     |
|장치 유형 제한     | 조직의 Windows 10 장치가 Intune에 등록할 수 있도록 허용된지 확인        |
|등록 상태 페이지     | 등록 상태 페이지를 사용할 수 없는지 확인      |
|Intune 등록     | Azure AD 조직의 Windows 10 장치가 Intune에 자동으로 등록되어 있는지 확인         |
|비즈니스용 Microsoft Store     | 비즈니스용 Microsoft Store를 활성화하고 Intune과 동기화하는지 확인        |
|다단계 인증 | Microsoft Managed Desktop 서비스 계정에 다단계 인증이 적용되지 않는지 확인
|PowerShell 스크립트     | Microsoft Windows PowerShell 디바이스를 대상으로 하는  방식으로 Windows PowerShell 스크립트가 할당되지 않은지 확인    |
|Region     | Microsoft Managed Desktop에서 해당 지역이 지원되는지 확인        |
|보안 기준     | 보안 기준 프로필이 모든 사용자 또는 모든 장치를 대상으로 하지 않는지  검사합니다(보안 기준 정책은 Microsoft Managed Desktop 장치를 대상으로 지정하지 말아야 합니다.)       |
|Windows 앱     | Microsoft Managed Desktop 장치에 할당할 앱 검토      |
|비즈니스용 Windows Hello     | 비즈니스용 Windows Hello를 사용할 수 있는지 확인        |
|Windows 10 업데이트 링     | Intune의 "Windows 10 업데이트 링" 정책이 모든 사용자 또는 모든 장치를  대상으로 하지 않는지 확인(해당 정책은 Microsoft Managed Desktop 장치를 대상으로 지정하지 말아야 합니다.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory 설정

|수표  |설명  |
|---------|---------|
|엔터프라이즈 상태 로밍에 대한 "애드 Hoc" 구독     | "false"로 설정하면 Enterprise State Roaming이 제대로 작동하지 않을 수 있는 설정을 검사하는 방법을 알 수 있습니다.  |
|Enterprise State Roaming     | 엔터프라이즈 상태 로밍을 사용하도록 설정되어 있는지 확인하는 방법에 대한 조언       |
|라이선스     | 필요한 라이선스를 획득한지 [확인](prerequisites.md#more-about-licenses)         |
|다단계 인증     | 다단계 인증이 모든 사용자에게 적용되지 않는지 확인(다단계 인증을 Microsoft Managed Desktop 서비스 계정에 실수로 적용하면 안 됩니다.)|
|보안 계정 이름   | Microsoft Managed Desktop에서 자체적으로 사용하기 위해 예약한 사용자 이름과 충돌하지 않습니다.        |
|보안 관리자 역할     | 보안 읽기 사용자, 보안 운영자 또는 전역 독자 역할이 있는 사용자에게 끝점용 Microsoft Defender에서 해당 역할이 할당되어 있는지 확인         |
|보안 기본값 | Azure AD 조직이 Azure Active Directory에서 보안 기본값을 사용하도록 설정되어 있는지 확인합니다. |
|셀프 서비스 암호 재설정     | 셀프 서비스 암호 재설정이 사용하도록 설정되어 있는지 확인        |
|표준 사용자 역할     | 사용자가 표준 사용자로서 로컬 관리자 권한이 없는지 확인         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>엔터프라이즈용 Microsoft 365 앱 설정

|수표  |설명  |
|---------|---------|
|비즈니스용 OneDrive     | 비즈니스용 OneDrive에서 지원되지 않는 설정을 사용하고 있는지 확인합니다.        |


각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.


|결과  |의미  |
|---------|---------|
|준비     | 등록을 완료하기 전에 필요한 작업은 없습니다.        |
|권고    | 등록과 사용자에 대해 최상의 환경을 제공하려면 도구의 단계를 따르세요. *등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.        |
|준비되지 않음 | *이러한 문제를* 해결하지 않는 경우 등록이 실패합니다. 도구의 단계에 따라 문제를 해결합니다.        |
|오류 | 사용중인 Azure AD(Active Director) 역할에 이 검사를 실행할 수 있는 권한이 없습니다. |

## <a name="after-enrollment"></a>등록 후

Microsoft Managed Desktop에 등록을 완료한 후 돌아가서 특정 Intune 및 Azure AD 설정을 조정해야 합니다. 자세한 내용은 등록 후 [설정 조정을 참조하세요.](../get-started/conditional-access.md)
