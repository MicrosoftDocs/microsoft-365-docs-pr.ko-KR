---
title: 엔터프라이즈용 Microsoft 365 테스트 환경용 Azure AD ID 보호
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD ID 보호를 구성하고 엔터프라이즈용 Microsoft 365 테스트 환경에서 현재 계정을 분석합니다.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487711"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경용 Azure AD ID 보호

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

Azure AD(Azure Active Directory) ID 보호를 사용하여 조직의 ID에 영향을 주는 잠재적인 취약점을 감지하고 자동화된 응답을 구성하고 인시던트 조사를 할 수 있습니다. 이 문서에서는 Azure AD ID 보호를 사용하여 테스트 환경 계정의 분석을 보는 방법을 설명합니다.

엔터프라이즈용 Microsoft 365 테스트 환경에서 Azure AD ID 보호를 설정하는 단계는 다음 두 단계로 진행됩니다.

- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: Azure AD ID 보호 사용](#phase-2-use-azure-ad-identity-protection)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항과 경량 방식으로 Azure AD ID 보호만 테스트하려면 경량 기본 구성의 [지침을 따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 Azure AD ID 보호를 테스트하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Azure AD ID 보호 테스트에는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. Azure AD ID 보호를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>2단계: Azure AD ID 보호 사용

1. 브라우저의 개인 인스턴스를 열고 엔터프라이즈용 Microsoft 365 테스트 환경의 전역 관리자 계정으로 [https://portal.azure.com](https://portal.azure.com) Azure Portal에 로그인합니다.
2. Azure Portal에서 검색 상자에 **ID** 보호를 입력한 다음 **Azure AD ID 보호를 선택합니다.**
3. ID 보호 **-** 개요 블레이드에서 각 보고서를 선택하여 보고하는 대상을 봐야 합니다.
4. **알림에서** **위험에 노출된 경고를 감지한 사용자를 선택합니다.**
5. 위험에 **노출된 경고가** 있는 사용자 창에서 중간을 **선택합니다.**
6. 전자 **메일이** 다음 사용자에게 전송되는  경우 포함을 선택하고 전역 관리자 계정이 선택한 구성원 목록에 있는지 확인해야 합니다.
7. **저장** 을 선택합니다.

보호 **아래에서** 다양한 옵션을 선택하여 구성 방법을 봐야 합니다. 정책을 만들고 활성화하는 경우 정책이 모든 사용자에 대한 액세스를 차단하지 않는지 확인하거나 로그인하지 못하게 될 수 있습니다. 이를 방지하려면 전역 관리자와 같은 특정 사용자 계정을 제외합니다.

추가 테스트 및 실험은 위험 이벤트 [시뮬레이션을 참조하세요.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
