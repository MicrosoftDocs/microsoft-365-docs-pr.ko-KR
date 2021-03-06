---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 대한 라이선스 및 그룹 멤버십 자동화
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 엔터프라이즈용 Microsoft 365 테스트 환경에서 그룹 기반 라이선싱 및 동적 그룹 구성원을 구성합니다.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487579"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에 대한 라이선스 및 그룹 멤버십 자동화

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 테스트 환경에만 사용할 수 있습니다.*

그룹 기반 라이선스는 그룹 구성원 자격에 따라 사용자 계정에 대한 라이선스를 자동으로 할당하거나 제거합니다. 동적 그룹 구성원은 부서 또는 국가와 같은 사용자 계정 속성에 따라 그룹에 구성원을 **추가하거나** **제거합니다.** 이 문서에서는 엔터프라이즈용 Microsoft 365 테스트 환경에서 그룹 구성원을 추가 및 제거하는 데모를 단계화합니다.

엔터프라이즈용 Microsoft 365 테스트 환경에서 자동 라이선싱 및 동적 그룹 구성원을 설정하는 단계는 다음 두 단계로 진행됩니다.

- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항을 통해 간단한 방식으로만 자동화된 라이선스 및 그룹 멤버 자격을 테스트하려면 경량 기본 구성의 지침을 [따르세요.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
시뮬레이트된 엔터프라이즈에서 자동화된 라이선스 및 그룹 멤버 자격을 테스트하려는 경우 통과 인증의 지침을 [따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> 자동화된 라이선스 및 그룹 멤버 자격을 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 인터넷에 연결된 시뮬레이트된 인트라넷과 AD DS(Active Directory 도메인 서비스) 포리스트에 대한 디렉터리 동기화가 포함됩니다. 여기서는 자동화된 라이선스 및 그룹 멤버십을 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 옵션으로 제공됩니다.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2단계: 동적 그룹 구성원 자격 및 자동 라이선싱 구성 및 테스트

먼저 Sales라는 새 그룹을 만들고 Department가 **Sales로** 설정된 사용자 계정이 Sales 그룹에 자동으로 가입하도록 동적 그룹 구성원 규칙을 추가합니다. 

1. 인터넷 브라우저의 개인 인스턴스에서 [Microsoft 365 E5](https://admin.microsoft.com) 테스트 랩 구독의 전역 관리자 계정으로 Microsoft 365 관리 센터에 로그인합니다.
2. 브라우저의 별도 탭에서 Azure Portal(.)로 [https://portal.azure.com](https://portal.azure.com) 이동하세요.
3. Azure Portal에서 검색  상자에 그룹을 입력한 다음 그룹을 **선택합니다.**
4. 모든 그룹 **창에서** 새 **그룹을 선택합니다.**
5. 그룹 **유형에서** **Microsoft 365를 선택합니다.**
6. 그룹 **이름에** **Sales를 입력합니다.**
7. 멤버 **자격 유형에서** **동적 사용자를 선택합니다.**
8. 동적 **사용자 구성원을 선택합니다.**
9. 동적 구성원 **규칙 창에서** 다음을 합니다. 
   - 부서 **속성을** 선택합니다.
   - **같음 연산자를** 선택합니다.
   - 값 **상자에** **Sales를 입력합니다.**
10. **저장** 을 선택합니다.
11. **만들기** 를 선택합니다.

그런 다음 구성원에게 Microsoft 365 E5 라이선스가 자동으로 할당될 수 있도록 Sales 그룹을 구성합니다.

1. Sales **그룹을 선택한** 다음 **라이선스를 선택합니다.**
2. 라이선스 **할당 업데이트** 창에서 **Microsoft 365 E5를** 선택한 다음 저장을 **선택합니다.**
3. 브라우저에서 Azure Portal 탭을 닫습니다.

다음으로, 사용자 4 계정에서 동적 그룹 구성원 자격 및 자동 라이선싱을 테스트합니다.

1. 브라우저의 **Microsoft Office** 탭에서 관리자를 **선택합니다.**
2. Microsoft **365** 관리 센터 탭에서 활성 **사용자를 선택합니다.**
3. 활성 사용자 **페이지에서** 사용자 **4 계정을** 선택합니다.
4. 사용자 **4** 창에서 제품  라이선스 **편집을 선택합니다.**
5. 제품 라이선스 **창에서** **Microsoft 365 E5** 라이선스를 사용하지 않도록 설정한 다음 저장 **닫기 를**  >  **선택합니다.**
6. 사용자 4 계정의 속성에서 제품 라이선스가 할당되지 않은지와 그룹 구성원 자격이 없는지 확인해야 합니다.
7. 연락처 **정보의 경우** 편집을 **선택합니다.**
8. 연락처 정보 **편집 창에서** 연락처 **정보를 선택합니다.**
9. 부서 **상자에** **Sales를** 입력한 다음 저장 **닫기 를**  >  **선택합니다.**
10. 몇 분 정도 기다렸다가 사용자  4 계정 창의 오른쪽 위에 있는 새로 고침 아이콘을 주기적으로 선택합니다.

시간이 지난 후 다음이 표시 됩니다.

- **Group memberships** 속성이 **Sales** 그룹으로 업데이트되었습니다.
- **Microsoft** **365 E5** 라이선스로 업데이트된 제품 라이선스 속성

다음 문서를 참조하여 프로덕션에서 동적 그룹 구성원 자격 및 자동 라이선싱을 배포합니다.

- [Azure Active Directory의 그룹 기반 라이선싱](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory의 동적 그룹](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [ID](m365-enterprise-test-lab-guides.md#identity) 기능도 알아봅니다.

## <a name="see-also"></a>참고 항목

[ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
