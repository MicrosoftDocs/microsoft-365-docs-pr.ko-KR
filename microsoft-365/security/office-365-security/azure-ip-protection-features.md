---
title: 기존 테넌트에 롤아웃된 Azure Information Protection의 보호 기능
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Azure Information Protection의 보호 기능에 롤아웃되는 변경 내용에 대해 설명합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe85a46e3f20cda62cd8a52bd5df92257f8fee57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286672"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>기존 테넌트에 롤아웃된 Azure Information Protection의 보호 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

정보 보호의 초기 단계를 지원하기 위해 2018년 7월부터 모든 Azure Information Protection 적격 테넌트에는 기본적으로 Azure Information Protection의 보호 기능이 켜져 있습니다. Azure Information Protection의 보호 기능은 이전 Office 365에서 권한 관리 또는 Azure RMS로 알려져 있습니다. 조직에 Office E3 서비스 플랜 또는 상위 서비스 플랜이 있는 경우 이러한 기능을 롤아웃할 때 Azure Information Protection을 통해 정보를 보호하기 시작할 수 있습니다.

## <a name="changes-beginning-july-1-2018"></a>2018년 7월 1일 이후 변경 내용

2018년 7월 1일부터 Microsoft는 다음 구독 계획 중 하나를 사용하여 모든 조직에 대해 Azure Information Protection의 보호 기능을 사용하도록 설정할 것입니다.

- Office 365 메시지 암호화는 Office 365 E3 및 E5, Microsoft E3 및 E5, Office 365 A1, A3 및 A5 및 Office 365 G3 및 G5의 일부로 제공됩니다. Azure Information Protection의 새로운 보호 기능을 받기 위해 추가 라이선스가 필요하지 않습니다.

- 또한 Azure Information Protection 계획 1을 다음 계획에 추가하여 새로운 Office 365 메시지 암호화 기능을 받을 수 있습니다. Exchange Online 계획 1, Exchange Online 계획 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard 또는 Office 365 Enterprise E1.

- Office 365 메시지 암호화를 통해 혜택을 받을 수 있는 각 사용자는 이 기능을 사용할 수 있도록 라이선스가 부여되어야 합니다.

- 전체 목록은 Office 365 [메시지 암호화에](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 대한 Exchange Online 서비스 설명을 참조하세요.

테넌트 관리자는 Office 365 관리자 포털에서 보호 상태를 확인할 수 있습니다.

![Screenshot that shows that rights management in Office 365 is activated.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>이러한 변경을 하는 이유는 무엇일까요?

Office 365 메시지 암호화는 Azure Information Protection의 보호 기능을 활용합니다. Microsoft 365의 정보 보호에 대한 최근 개선된 기능과 Microsoft 365의 정보 보호에 대한 광범위한 투자의 핵심은 지금까지 암호화 기술을 설정하기 어려웠기 때문에 조직이 보다 쉽게 보호 기능을 켜고 사용할 수 있도록 합니다. 기본적으로 Azure Information Protection의 보호 기능을 켜면 중요한 데이터를 신속하게 보호할 수 있습니다.

## <a name="does-this-impact-me"></a>이 영향이 내게 영향을 미치나요?

조직에서 적합한 Office 365 라이선스를 구입한 경우 테넌트는 이 변경의 영향을 받을 수 있습니다.

> [!IMPORTANT]
> 프레미스 환경에서 AD RMS(Active Directory Rights Management Services)를 사용하는 경우 다음 30일 이내에 이 변경을 롤아웃하기 전에 이 변경을 즉시 옵트아웃하거나 Azure Information Protection으로 마이그레이션해야 합니다. 옵트아웃하는 방법에 대한 자세한 내용은 "AD RMS를 사용하세요. 옵트아웃하는 방법"을 참조하세요. 후반부에 이 문서의 마이그레이션하려면 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>AD RMS(Azure Information Protection)Active Directory Rights Management Services 사용할 수 있나요?

아니요. 이는 지원되는 배포 시나리오가 아닙니다. 추가 옵트아웃 단계를 수행하지 않으면 일부 컴퓨터에서 Azure 권한 관리 서비스를 자동으로 시작하고 AD RMS 클러스터에 연결할 수도 있습니다. 이 시나리오는 지원되지 않는 것이고 신뢰할 수 없는 결과가 있으므로 이러한 새 기능을 롤아웃하기 전에 다음 30일 이내에 이 변경을 옵트아웃(opt out)하는 것이 중요합니다. 옵트아웃하는 방법에 대한 자세한 내용은 "AD RMS를 사용하세요. 옵트아웃하는 방법"을 참조하세요. 후반부에 이 문서의 마이그레이션을 원하는 경우 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>AD RMS를 사용하는지 어떻게 알 수 있나요?

AD RMS(Active Directory Rights Management Services)도 있는 경우 Azure 권한 관리를 위한 환경 준비에서 다음 지침을 사용하여 AD [RMS를](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) 배포한지 확인할 수 있습니다.

1. 선택 사항이지만 대부분의 AD RMS 배포는 도메인 컴퓨터가 AD RMS 클러스터를 검색할 수 있도록 SCP(서비스 연결 지점)를 Active Directory에 게시합니다.

   ADSI 편집을 사용하여 SCP가 Active Directory에 게시되어 있는지 확인합니다. CN=Configuration [서버 이름], CN=Services, CN=RightsManagementServices, CN=SCP

2. SCP를 사용하지 않는 경우 WINDOWS 레지스트리를 사용하여 AD RMS 클러스터에 연결하는 Windows 컴퓨터를 클라이언트 쪽 서비스 검색 또는 라이선스 리디렉션에 맞게 구성해야 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` 합니다.

이러한 레지스트리 구성에 대한 자세한 내용은 [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) 레지스트리를 사용하여 클라이언트 쪽 서비스 검색 사용 및 라이선스 서버 트래픽 리디렉션을 [참조하세요.](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>AD RMS를 사용, 옵트아웃하는 방법

예정된 변경을 옵트아웃(opt out)으로 설정하기 위해 다음 단계를 완료합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 Exchange Online에 연결합니다. 지침을 확인하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

2. 다음 구문을 Set-IRMConfiguration cmdlet을 실행합니다.

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>이 변경이 만들어진 후 예상할 수 있는 상황

이 기능을 사용하도록 설정한 후 옵트아웃하지 않은 경우 [Microsoft Ignite 2017에서](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) 발표된 새로운 버전의 Office 365 메시지 암호화를 사용하여 Azure Information Protection의 암호화 및 보호 기능을 활용할 수 있습니다.

![Screenshot that shows an OME protected message in Outlook on the web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

새로운 기능 향상에 대한 자세한 내용은 [Office 365 메시지 암호화를 참조하세요.](../../compliance/ome.md)
