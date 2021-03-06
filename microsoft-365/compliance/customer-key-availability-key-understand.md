---
title: 고객 키에 대한 가용성 키 알아보기
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 손실된 고객 키를 복구하는 데 사용되는 가용성 키에 대해 자세히 알아보습니다.
ms.openlocfilehash: 8e9903294d5fc25e51ef25c0ae6237c943dec6ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632027"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>고객 키에 대한 가용성 키 알아보기

가용성 키는 데이터 암호화 정책을 만들 때 자동으로 생성되고 프로비전되는 루트 키입니다. Microsoft 365는 가용성 키를 저장하고 보호합니다. 가용성 키는 고객 키를 사용하여 서비스 암호화를 위해 제공하는 두 루트 키와 기능적으로 같아야 합니다. 가용성 키는 키 계층 구조에서 한 계층 아래에서 키를 줄 바꿈합니다. Azure Key Vault에서 제공하고 관리하는 키와 달리 가용성 키에 직접 액세스할 수 없습니다. Microsoft 365 자동화 서비스는 프로그래밍적으로 가용성 키를 관리합니다. 이러한 서비스는 가용성 키에 대한 직접 액세스와는 관련이 없는 자동화된 작업을 시작됩니다.

가용성 키의 주요 목적은 관리하는 루트 키의 의도하지 않은 손실로부터 복구 기능을 제공하는 것입니다. 손실은 오해나 악의적인 작업의 결과일 수 있습니다. 루트 키에 대한 제어가 잃을 경우 Microsoft 지원에 문의하면 Microsoft에서 가용성 키를 사용하여 복구 프로세스를 지원할 것입니다. 가용성 키를 사용하여 프로비전하는 새 루트 키가 있는 새 데이터 암호화 정책으로 마이그레이션합니다.

가용성 키의 저장 및 제어는 세 가지 이유로 인해 Azure Key Vault 키와 고의적으로 다릅니다.

- 가용성 키는 두 Azure Key Vault 키에 대한 제어가 모두 손실된 경우 복구, "중단 유리" 기능을 제공합니다.
- 논리 컨트롤과 보안 저장소 위치를 분리하면 심층 방어가 제공되어 단일 공격이나 오류 지점에서 모든 키와 데이터가 손실되지 않습니다.
- 가용성 키는 Microsoft 365 서비스가 일시적인 오류로 인해 Azure Key Vault에서 호스트된 키에 도달할 수 없는 경우 고가용성 기능을 제공합니다. 이 규칙은 Exchange Online 및 비즈니스용 Skype 서비스 암호화에만 적용됩니다. Microsoft에 복구 프로세스를 시작하게 명시적으로 지시하지 않는 한 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일은 가용성 키를 사용하지 않습니다.

키 관리를 위한 다양한 보호 및 프로세스를 사용하여 데이터를 보호해야 하는 책임을 공유하면 궁극적으로 모든 키(및 사용자 데이터)가 영구적으로 손실되거나 폐기되는 위험을 줄일 수 있습니다. Microsoft는 사용자가 서비스를 떠날 때 가용성 키의 사용 안함 또는 폐기에 대한 유일한 권한을 사용자에게 제공합니다. 기본적으로 Microsoft의 어느 누구도 가용성 키에 액세스할 수 없습니다. 이 키는 Microsoft 365 서비스 코드에서만 액세스할 수 있습니다.

키를 보호하는 방법에 대한 자세한 내용은 [Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) 보안 센터를 참조하세요.
  
## <a name="availability-key-uses"></a>가용성 키 사용

가용성 키는 외부 남성 또는 악의적인 내부 사용자가 키 자격 증명 모음의 제어를 도용하거나 잘못된 관리로 루트 키가 손실되는 시나리오에 대한 복구 기능을 제공합니다. 이 복구 기능은 고객 키와 호환되는 모든 Microsoft 365 서비스에 적용됩니다. 개별 서비스는 가용성 키를 다르게 사용 합니다. Microsoft 365는 아래 설명된 방식으로만 가용성 키를 사용 합니다.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online 및 비즈니스용 Skype 사용

복구 기능 외에도 Exchange Online 및 비즈니스용 Skype는 가용성 키를 사용하여 루트 키에 액세스하는 서비스와 관련된 일시적 또는 일시적인 운영 문제 동안 데이터 가용성을 보장합니다. 일시적인 오류로 인해 서비스가 Azure Key Vault의 고객 키 중 하나에 도달할 수 없는 경우 서비스에서 자동으로 가용성 키를 사용하게 됩니다. 서비스가 가용성 키로 직접 연결되지 않습니다.

Exchange Online 및 비즈니스용 Skype의 자동화된 시스템은 일시적인 오류 시 가용성 키를 사용하여 바이러스 백신, 전자 검색, 데이터 손실 방지, 사서함 이동 및 데이터 인덱싱과 같은 자동화된 백 엔드 서비스를 지원할 수 있습니다.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에서 사용하는 경우

SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 가용성 키는 복구 기능 외부에서 사용되지 않습니다. 고객은 Microsoft에 복구 시나리오 중에 가용성 키 사용을 시작하게 명시적으로 지시해야 합니다. 자동화된 서비스 작업은 Azure Key vault의 고객 키를 전적으로 사용하게 됩니다. 이러한 서비스에 대해 키 계층 구조가 작동하는 방식에 대한 자세한 내용은 SharePoint Online, 비즈니스용 [OneDrive](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)및 Teams 파일에서 가용성 키를 사용하는 방법을 참조하세요.

## <a name="availability-key-security"></a>가용성 키 보안

Microsoft는 가용성 키를 인스턴스화하고 이를 보호하기 위한 광범위한 조치를 취하여 데이터 보호의 책임을 공유합니다. Microsoft는 고객에게 가용성 키에 대한 직접적인 제어를 노출하지 않습니다. 예를 들어 Azure Key Vault에서 소유한 키만 롤(회전)할 수 있습니다. 자세한 내용은 고객 키 또는 가용성 키 롤 또는 [회전을 참조하세요.](customer-key-availability-key-roll.md)

### <a name="availability-key-secret-stores"></a>가용성 키 비밀 저장소

Microsoft는 고객이 사용하는 Azure Key Vault와 같은 액세스 제어 내부 암호 저장소의 가용성 키를 보호합니다. Microsoft 관리자가 포함된 비밀에 직접 액세스하지 못하게 액세스 제어를 구현합니다. 키 회전 및 지우기 등의 비밀 저장소 작업은 가용성 키에 대한 직접 액세스와 관련이 없는 자동화된 명령을 통해 수행됩니다. 비밀 저장소 관리 작업은 특정 엔지니어로 제한되어 있으며 내부 도구인 Lockbox를 통해 권한 에스컬레이터를 요구합니다. 권한 에스컬레이터를 사용하려면 권한을 부여하기 전에 관리자의 승인 및 사당이 필요합니다. Lockbox는 액세스가 시간 만료 또는 엔지니어 로그아웃 시 자동 액세스 해지로 제한된 시간을 보장합니다.

**Exchange Online 및 비즈니스용 Skype** 가용성 키는 Exchange Online Active Directory 비밀 저장소에 저장됩니다. 가용성 키는 Active Directory 도메인 컨트롤러 내의 테넌트 특정 컨테이너 내에 안전하게 저장됩니다. 이 보안 저장소 위치는 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일 비밀 저장소와 분리되어 있습니다.

**SharePoint Online, 비즈니스용 OneDrive 및 Teams** 파일 가용성 키는 서비스 팀에서 관리하는 내부 비밀 저장소에 저장됩니다. 보안이 유지되는 비밀 저장소 서비스에는 응용 프로그램 끝점이 있는 프런트 엔드 서버와 SQL 데이터베이스가 백 엔드로 있습니다. 가용성 키는 SQL 데이터베이스에 저장되며 AES-256 및 HMAC 조합을 사용하여 미사용 가용성 키를 암호화하는 비밀 저장소 암호화 키로 래핑(암호화)됩니다. 비밀 저장소 암호화 키는 동일한 SQL Database의 논리적으로 격리된 구성 요소에 저장되며 Microsoft CA(인증 기관)에서 관리하는 인증서에 포함된 RSA-2048 키로 추가로 암호화됩니다. 이러한 인증서는 데이터베이스에 대해 작업을 수행하는 비밀 저장소 프런트 엔드 서버에 저장됩니다.

### <a name="defense-in-depth"></a>심층 방어

Microsoft는 심층 방어 전략을 사용하여 악의적인 공격자들이 Microsoft 클라우드에 저장된 고객 데이터의 기밀성, 무결성 또는 가용성에 영향을 미치는 것을 방지합니다. 특정 예방 및 감지용 컨트롤은 과부하 보안 전략의 일부로 비밀 저장소 및 가용성 키를 보호하기 위해 구현됩니다.

Microsoft 365는 가용성 키의 오용을 방지하기 위해 제작됩니다. 응용 프로그램 계층은 가용성 키를 비롯한 키를 사용하여 데이터를 암호화하고 암호 해독하는 데 사용할 수 있는 유일한 방법입니다. Microsoft 365 서비스 코드만 암호화 및 암호 해독 활동을 위해 키 계층 구조를 해석하고 트래버스할 수 있습니다. 고객 키의 저장소 위치, 가용성 키, 기타 계층적 키 및 고객 데이터 간에 논리적 고리가 있습니다. 이렇게 하는 경우 하나 이상의 위치가 손상된 경우 데이터 노출 위험을 완화할 수 있습니다. 계층 구조의 각 계층에는 저장된 데이터 및 비밀을 보호하기 위해 24x7 침입 감지 기능이 기본 제공되어 있습니다.

액세스 제어는 가용성 키 비밀 저장소를 포함하여 내부 시스템에 대한 무단 액세스를 방지하기 위해 구현됩니다. Microsoft 엔지니어는 가용성 키 비밀 저장소에 직접 액세스할 수 없습니다. 액세스 제어에 대한 자세한 내용은 [Microsoft 365의](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview)관리 액세스 제어를 검토합니다.

기술 제어를 통해 Microsoft 직원이 높은 권한의 서비스 계정에 로그인할 수 없습니다. 이 계정은 공격자가 Microsoft 서비스를 가장하는 데 사용될 수 있습니다. 예를 들어 이러한 컨트롤은 대화형 로그온을 방지합니다.

보안 로깅 및 모니터링 제어는 Microsoft 서비스와 데이터에 대한 위험을 완화하는 또 다른 심층 방어 보호 장치입니다. Microsoft 서비스 팀은 경고 및 감사 로그를 생성하는 활성 모니터링 솔루션을 배포했습니다. 모든 서비스 팀은 로그가 집계 및 처리되는 중앙 저장소에 로그를 업로드합니다. 내부 도구는 레코드를 자동으로 검사하여 서비스가 최적화되고 탄력적인 보안 상태로 작동하고 있는지 확인할 수 있습니다. 비정상적인 활동은 추가 검토를 위해 플래그가 지정됩니다.

Microsoft 보안 정책 위반 가능성을 나타내는 모든 로그 이벤트는 즉시 Microsoft 보안 팀의 주의를 끌 수 있습니다. Microsoft 365 보안은 가용성 키 비밀 저장소에 대한 액세스 시도를 감지하도록 경고를 구성했습니다. Microsoft 직원이 액세스 제어에 의해 금지 및 보호되는 서비스 계정에 대화형 로그온을 시도하면 알림도 생성됩니다. 또한 Microsoft 365 보안은 Microsoft 365 서비스가 일반 기준 작업과 다른 경우를 감지하고 경고합니다. Microsoft 365 서비스를 오용하려는 남성은 경고를 트리거하여 가해자는 Microsoft 클라우드 환경에서 벗어날 수 있습니다.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>가용성 키를 사용하여 키 손실로부터 복구

고객 키에 대한 제어권이 손실된 경우 가용성 키는 데이터를 복구하고 다시 암호화하는 기능을 제공합니다.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype 복구 절차

고객 키에 대한 제어권이 손실된 경우 가용성 키는 데이터를 복구하고 영향을 주는 Microsoft 365 리소스를 다시 온라인으로 가져오는 기능을 제공합니다. 복구하는 동안 가용성 키는 데이터를 계속 보호합니다. 높은 수준에서 키 손실을 완전히 복구하려면 새 DEP를 만들고 영향을 미치는 리소스를 새 정책으로 이동해야 합니다.

새 고객 키를 사용하여 데이터를 암호화하기 위해 Azure Key Vault에서 새 키를 만들고 새 고객 키를 사용하여 새 DEP를 만든 다음 키가 분실되거나 손상된 이전 DEP로 현재 암호화된 사서함에 새 DEP를 할당합니다.

이 다시 암호화 프로세스는 최대 72시간이 걸릴 수 있습니다. DEP를 변경할 때의 표준 기간입니다.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 복구 절차

SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 가용성 키는 복구 기능 외부에서 사용되지 않습니다. 복구 시나리오 중에 Microsoft에 가용성 키 사용을 시작해야 합니다. 복구 프로세스를 시작하려면 Microsoft에 문의하여 가용성 키를 활성화합니다. 활성화되면 가용성 키가 데이터 암호를 해독하는 데 자동으로 사용되므로 새 고객 키에 연결된 새로 만든 DEP를 사용하여 데이터를 암호화할 수 있습니다.  

이 작업은 조직의 사이트 수에 비례합니다. Microsoft에 가용성 키를 사용하기 위해 전화를 걸면 약 4시간 이내에 완전히 온라인이 됩니다.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online 및 비즈니스용 Skype에서 가용성 키를 사용하는 방법

고객 키를 사용하여 DEP를 만들면 Microsoft 365는 해당 DEP와 연결된 DEP 키(데이터 암호화 정책 키)를 생성합니다. 이 서비스는 DEP 키를 세 번 암호화합니다. 각 고객 키와 가용성 키를 사용하여 한 번씩 DEP 키의 암호화된 버전만 저장되며 DEP 키는 고객 키 또는 가용성 키로만 암호 해독할 수 있습니다. 그런 다음 DEP 키를 사용하여 개별 사서함을 암호화하는 사서함 키를 암호화합니다.
  
Microsoft 365는 이 프로세스를 따라 고객이 서비스를 사용할 때 암호를 해독하고 데이터를 제공합니다.
  
1. 고객 키를 사용하여 DEP 키의 암호를 해독합니다.

2. 암호 해독된 DEP 키를 사용하여 사서함 키의 암호를 해독합니다.

3. 암호 해독된 사서함 키를 사용하여 사서함 자체의 암호를 해독하여 사서함 내의 데이터에 액세스할 수 있습니다.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에서 가용성 키를 사용하는 방법

고객 키 및 가용성 키에 대한 SharePoint Online 및 비즈니스용 OneDrive 아키텍처 및 구현은 Exchange Online 및 비즈니스용 Skype와 다릅니다.
  
조직이 고객 관리 키로 이동하면 Microsoft 365는 조직별 TIK(중간 키)를 만듭니다. Microsoft 365는 각 고객 키를 사용하여 TIK를 두 번 암호화하고 암호화된 두 버전의 TIK를 저장합니다. 암호화된 버전의 TIK만 저장되고 TIK는 고객 키로만 암호 해독할 수 있습니다. 그런 다음 TIK를 사용하여 사이트 키를 암호화합니다. 이 키는 Blob 키(파일 청크 키라고도 불리는)를 암호화하는 데 사용됩니다. 파일 크기에 따라 서비스는 파일을 각각 고유한 키로 여러 파일 청크로 분할할 수 있습니다. Blob(파일 청크) 자체는 Blob 키로 암호화되고 Microsoft Azure Blob Storage 서비스에 저장됩니다.
  
Microsoft 365는 이 프로세스를 따라 고객이 서비스를 사용할 때 암호를 해독하고 고객 파일을 제공합니다.

1. 고객 키를 사용하여 TIK의 암호를 해독합니다.

2. 암호 해독된 TIK를 사용하여 사이트 키의 암호를 해독합니다.

3. 암호 해독된 사이트 키를 사용하여 Blob 키의 암호를 해독합니다.

4. 암호 해독된 Blob 키를 사용하여 Blob의 암호를 해독합니다.

Microsoft 365는 약간의 오프셋으로 Azure Key Vault에 두 개의 암호 해독 요청을 발행하여 TIK의 암호를 해독합니다. 완료할 첫 번째 요청은 결과를 제공하여 다른 요청을 취소합니다.
  
고객 키에 대한 액세스 권한이 손실된 경우 Microsoft 365는 가용성 키로 TIK를 암호화하고 각 고객 키로 암호화된 TIK와 함께 저장합니다. 가용성 키로 암호화된 TIK는 고객이 악의적으로 또는 실수로 키에 액세스할 수 없는 경우 Microsoft에 복구 경로를 요청하는 경우에 사용됩니다.
  
가용성 및 확장을 위해 암호 해독된 TIK는 시간 제한 메모리 캐시에 캐시됩니다. TIK 캐시가 만료로 설정되기 2시간 전에 Microsoft 365는 각 TIK의 암호를 해독하려고 시도합니다. TIK의 암호를 해독하는 경우 캐시의 수명이 연장됩니다. TIK 암호 해독이 상당한 시간 동안 실패하면 Microsoft 365는 캐시 만료 전에 엔지니어링에 알리는 경고를 생성합니다. 고객이 Microsoft에 전화를 거는 경우만 Microsoft 365가 복구 작업을 시작하며, 이는 Microsoft의 비밀 저장소에 저장된 가용성 키로 TIK의 암호를 해독하고, 암호 해독된 TIK 및 고객이 제공한 새로운 Azure Key Vault 키 집합을 사용하여 테넌트를 다시 온보더링하는 작업입니다.
  
현재, 고객 키는 Azure Blob 저장소에 저장된 SharePoint Online 파일 데이터의 암호화 및 암호 해독 체인에 포함되지만 SQL 데이터베이스에 저장된 SharePoint Online 목록 항목 또는 메타데이터는 포함하지 않습니다. Microsoft 365는 위에서 설명한 사례가 아닌 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일(고객이 시작한 경우)에 대한 가용성 키를 사용하지 않습니다. 고객 데이터에 대한 인적 액세스는 Customer Lockbox에 의해 보호됩니다.

## <a name="availability-key-triggers"></a>가용성 키 트리거

Microsoft 365는 특정 상황에서만 가용성 키를 트리거합니다. 이러한 상황은 서비스마다 다릅니다.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대한 트리거
  
1. Microsoft 365는 Azure Key Vault에서 두 고객 키의 위치를 결정하기 위해 사서함이 할당된 DEP를 읽습니다.

2. Microsoft 365는 DEP에서 두 고객 키 중 하나를 임의로 선택하고 Azure Key Vault에 요청을 보내 고객 키를 사용하여 DEP 키를 래치하지 않습니다.

3. 고객 키를 사용하여 DEP 키를 래치하지 못하면 Microsoft 365가 Azure Key Vault에 두 번째 요청을 보내 이번에는 대체(두 번째) 고객 키를 사용하게 지시합니다.

4. 고객 키를 사용하여 DEP 키를 래치하는 두 번째 요청이 실패하면 Microsoft 365는 두 요청의 결과를 모두 검사합니다.

    - 검사에서 요청이 시스템 오류를 반환하지 못했다고 판단되는 경우:

       - Microsoft 365는 가용성 키를 트리거하여 DEP 키의 암호를 해독합니다.

       - 그런 다음 Microsoft 365는 DEP 키를 사용하여 사서함 키의 암호를 해독하고 사용자 요청을 완료합니다. 

       - 이 경우 Azure Key Vault는 일시적인 오류로 인해 응답할 수 없거나 이에 응답할 수 없습니다.

    - 검사에서 요청이 ACCESS DENIED를 반환하지 못했다고 판단되는 경우:

       - 즉, 서비스 종료의 일부로 데이터 삭제 프로세스 중과 같은 고객 키를 사용할 수 없게 설정하기 위해 고의적, 부수적 또는 악의적인 작업이 수행된 것입니다.

       - 이 경우 가용성 키는 시스템 작업에만 사용이 며 사용자 작업에는 사용되지 않습니다. 사용자 요청이 실패하고 사용자가 오류 메시지를 수신합니다.

>[!IMPORTANT]
>Microsoft 365 서비스 코드에는 항상 고객 데이터를 이유로 부가 가치 클라우드 서비스를 제공하기 위한 유효한 로그인 토큰이 있습니다. 따라서 가용성 키가 삭제될 때까지 Exchange Online 및 비즈니스용 Skype(예: 검색 인덱스 만들기 또는 사서함 이동)에서 시작되거나 내부적으로 시작된 작업에 대한 폴백으로 사용할 수 있습니다. 이는 Azure Key Vault에 대한 일시적인 오류 및 ACCESS DENIED 요청 둘 다에 적용됩니다.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 트리거

SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 가용성 키는 복구 기능 외부에서 사용되지 않습니다. 고객은 Microsoft에 복구 시나리오 중에 가용성 키 사용을 시작하게 명시적으로 지시해야 합니다.

## <a name="audit-logs-and-the-availability-key"></a>감사 로그 및 가용성 키

Microsoft 365의 자동화된 시스템은 시스템을 통해 흐르는 모든 데이터를 처리하여 바이러스 백신, 전자 검색, 데이터 손실 방지 및 데이터 인덱싱과 같은 클라우드 서비스를 제공합니다. Microsoft 365는 이 활동에 대해 고객이 볼 수 있는 로그를 생성하지 않습니다. 또한 Microsoft 직원은 이러한 일반적인 시스템 작업의 일부로 데이터에 액세스하지 않습니다.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online 및 비즈니스용 Skype 가용성 키 로깅

Exchange Online 및 비즈니스용 Skype가 가용성 키에 액세스하여 서비스를 제공하면 Microsoft 365는 보안 및 준수 센터에서 액세스할 수 있는 고객이 볼 수 있는 로그를 게시합니다. 서비스에서 가용성 키를 사용할 때마다 가용성 키 작업에 대한 감사 로그 레코드가 생성됩니다. 활동 유형이 "Fallback to Availability Key"인 "Customer Key Service Encryption"이라는 새 레코드 유형을 통해 관리자는 통합 감사 로그 검색 결과를 필터링하여 가용성 키 레코드를 볼 수 있습니다. [](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

로그 레코드에는 날짜, 시간, 활동, 조직 ID 및 데이터 암호화 정책 ID와 같은 특성이 포함됩니다. 이 레코드는 통합 감사 로그의 일부로 사용할 수 있으며 보안 및 준수 센터 감사 로그 & 탭에서 액세스할 수 있습니다.

![가용성 키 이벤트에 대한 감사 로그 검색](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online 및 비즈니스용 Skype 가용성 키 레코드는 [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 정책 ID, 범위 키 버전 ID 및 요청 ID와 같은 추가된 사용자 지정 매개 변수와 함께 Office 365 관리 활동 일반 스마마를 사용합니다.

![가용성 키 사용자 지정 매개 변수](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일 가용성 키 로깅

이러한 서비스에는 가용성 키 로깅을 아직 사용할 수 없습니다. SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 가용성 키는 복구 목적으로 Microsoft에서만 활성화됩니다. 따라서 이러한 서비스에 가용성 키가 사용되는 모든 이벤트를 이미 알고 있습니다.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>고객 키 계층 구조의 가용성 키
  
Microsoft 365는 가용성 키를 사용하여 고객 키 서비스 암호화에 대해 설정한 키 계층에서 낮은 키 계층을 줄 바꿈합니다. 서비스 간에는 서로 다른 키 계층이 있습니다. 또한 주요 알고리즘은 가용성 키와 해당하는 각 서비스의 계층 구조에 있는 다른 키 간에도 다릅니다. 다른 서비스에서 사용하는 가용성 키 알고리즘은 다음과 같습니다.

- Exchange Online 및 비즈니스용 Skype 가용성 키는 AES-256을 사용 합니다.

- SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일 가용성 키는 RSA-2048을 사용 합니다.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype의 키를 암호화하는 데 사용되는 암호화 암호화

![Exchange Online 고객 키에 대한 암호화](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive의 키를 암호화하는 데 사용되는 암호화 암호화

![SharePoint Online 고객 키에 대한 암호화](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)
