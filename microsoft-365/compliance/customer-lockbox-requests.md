---
title: 고객 Lockbox 요청
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 문제가 있는 경우 Microsoft 지원 엔지니어가 데이터에 액세스할 수 있는 방법을 제어할 수 있는 고객 Lockbox 요청에 대해 자세히 알아보습니다.
ms.openlocfilehash: b475c9af80d0e28961360825788d9e19a426dc69
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48768866"
---
# <a name="customer-lockbox-in-office-365"></a>Office 365의 고객 Lockbox

이 문서에서는 고객 Lockbox에 대한 배포 및 구성 지침을 제공합니다. 고객 Lockbox는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive의 데이터에 액세스하기 위한 요청을 지원합니다. 다른 서비스에 대한 지원을 권장하기 위해 [Office 365 UserVoice에서 요청을 제출하십시오.](https://office365.uservoice.com/)

2020년 4월 1일을 포함하여 Microsoft 365 규정 준수 서비스를 이용하기 위해 사용자에게 라이선스를 제공하는 옵션을 확인한 후 보안 및 규정 준수에 대한 [Microsoft 365](https://aka.ms/ComplianceSD)라이선스 & 참조하세요.

고객 Lockbox는 Microsoft가 명시적 승인 없이는 서비스 작업을 수행하기 위해 콘텐츠에 액세스할 수 없습니다. Customer Lockbox는 콘텐츠에 액세스하기 위한 요청에 대한 승인 워크플로를 제공합니다.

경우에 따라 Microsoft 엔지니어는 지원 프로세스에서 보고된 고객 문제를 해결하고 문제를 해결합니다. 일반적으로 문제는 Microsoft가 해당 서비스에 대해 준비한 광범위한 원격 분석 및 디버깅 도구를 통해 해결됩니다. 그러나 일부 경우에는 Microsoft 엔지니어가 고객 콘텐츠에 액세스하여 근본 원인을 파악하고 문제를 해결해야 합니다. 고객 Lockbox를 사용하려면 엔지니어가 승인 워크플로의 최종 단계로 고객의 액세스를 요청해야 합니다. 이렇게 하면 조직에서 이러한 요청을 승인하거나 거부하고 고객에게 직접 액세스 제어를 제공할 수 있습니다.

### <a name="customer-lockbox-overview-video"></a>고객 Lockbox 개요 비디오

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>고객 Lockbox 워크플로

다음 단계에서는 Microsoft 엔지니어가 고객 Lockbox 요청을 시작할 때의 일반적인 워크플로에 대해 간략하게 설명합니다.

1. 조직의 누군가가 Microsoft 365 사서함에 문제가 있습니다.

2. 사용자가 문제를 해결했지만 해결할 수 없는 경우 Microsoft 지원 서비스에서 지원 요청을 받습니다.

3. Microsoft 지원 엔지니어가 서비스 요청을 검토하고 Exchange Online에서 문제를 복구하기 위해 조직의 테넌트에 액세스해야 하는지 여부를 판단합니다.

4. Microsoft 기술 지원 엔지니어는 고객 Lockbox 요청 도구에 로그인하고 조직의 테넌트 이름, 서비스 요청 번호 및 엔지니어가 데이터에 액세스해야 하는 예상 시간을 포함하는 데이터 액세스 요청을 합니다.

5. Microsoft 지원 관리자가 요청을 승인하면 Customer Lockbox는 Microsoft의 보류 중인 액세스 요청에 대한 전자 메일 알림을 조직에서 지정된 승인자에 전송합니다.

    ![고객 Lockbox 전자 메일 알림의 예](../media/CustomerLockbox1.png)

   Microsoft 365 관리 센터에서 [고객 Lockbox](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 액세스 승인자 관리자 역할이 할당된 모든 사용자는 고객 Lockbox 요청을 승인할 수 있습니다.

6. 승인자가 Microsoft 365 관리 센터에 로그인하고 요청을 승인합니다. 이 단계에서는 감사 로그를 검색하여 사용 가능한 감사 레코드 만들기를 트리거합니다. 자세한 내용은 고객 Lockbox 요청 [감사를 참조하세요.](#auditing-customer-lockbox-requests)

   고객이 요청을 거부하거나 12시간 이내에 요청을 승인하지 않는 경우 요청이 만료되고 Microsoft 엔지니어에게 액세스 권한이 부여되지 않습니다.

   > [!IMPORTANT]
   > Microsoft는 Office 365에 로그인해야 하는 고객 Lockbox 전자 메일 알림에 링크를 포함하지 않습니다.

7. 조직의 승인자가 요청을 승인하면 Microsoft 엔지니어가 승인 메시지를 받고 Exchange Online의 테넌트에 로그인하고 고객의 문제를 해결합니다. Microsoft 엔지니어는 액세스가 자동으로 해지되는 문제를 해결하기 위해 요청된 기간이 있습니다.

> [!NOTE]
> Microsoft 엔지니어가 수행한 모든 작업이 감사 로그에 기록됩니다. 이러한 감사 레코드를 검색하고 검토할 수 있습니다.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>고객 Lockbox 요청 켜기 또는 끄기

Microsoft 365 관리 센터에서 고객 Lockbox 컨트롤을 켜면 됩니다. 고객 Lockbox를 켜면 Microsoft는 테넌트의 콘텐츠에 액세스하기 전에 조직의 승인을 얻어야 합니다.

1. 전역 관리자 또는 **Customer Lockbox** 액세스 승인자 역할이 할당된 직장 또는 학교 계정을 사용하여 이동하여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인합니다.

2. Choose **Settings > Org Settings.**

3. 보안 **& 개인** 정보 보호 고객 Lockbox 편집을 선택한 다음 토글을 켜기 또는 끄기로 이동하여 기능을  >    >  켜거나 끄습니다.  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>고객 Lockbox 요청 승인 또는 거부

1. 전역 관리자 또는 **Customer Lockbox** 액세스 승인자 역할이 할당된 직장 또는 학교 계정을 사용하여 이동하여 [https://admin.microsoft.com](https://admin.microsoft.com) 로그인합니다.

2. 고객 **Lockbox > 지원 옵션을 선택하십시오.**

    ![지원 클릭, 고객 Lockbox 요청 클릭](../media/CustomerLockbox5.png)

    고객 Lockbox 요청 목록이 표시됩니다.

    ![고객 Lockbox 요청 목록](../media/CustomerLockbox6.png)

3. 고객 Lockbox 요청을 선택한 다음 승인 **또는** **거부를 선택합니다.**

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox7.png)

    고객 Lockbox 요청 승인에 대한 확인 메시지가 표시됩니다.

    ![고객 Lockbox 요청 승인 또는 거부](../media/CustomerLockbox8.png)

> [!NOTE]
> Set-AccessToCustomerDataRequest cmdlet을 사용하여 Microsoft 지원 엔지니어의 사용자 데이터에 대한 액세스를 제어하는 Microsoft 365 고객 lockbox를 승인, 거부 또는 취소합니다. 자세한 내용은 [Set-AccessToCustomerDataRequest를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest)


## <a name="auditing-customer-lockbox-requests"></a>고객 Lockbox 요청 감사

고객 Lockbox 요청에 해당하는 감사 레코드가 감사 로그에 기록됩니다. 보안 및 준수 센터의 [](search-the-audit-log-in-security-and-compliance.md) 감사 로그 검색 도구를 사용하여 이러한 & 수 있습니다. Microsoft 엔지니어가 수행한 작업(액세스 요청이 승인된 경우)과 고객 Lockbox 요청 수락 또는 거부와 관련된 작업도 감사 로그에 기록됩니다. 이러한 감사 레코드를 검색하고 검토할 수 있습니다.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>고객 Lockbox 요청과 관련된 활동에 대한 감사 로그 검색

감사 로그를 사용하여 고객 Lockbox에 대한 요청을 추적하려면 먼저 감사 로깅을 설정하기 위해 몇 가지 단계를 수행해야 합니다. 자세한 내용은 보안 및 준수 센터에서 감사 [로그를 & 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 설치를 완료한 후 다음 단계를 사용하여 고객 Lockbox와 관련된 감사 레코드를 반환하는 감사 로그 검색 쿼리를 만들 수 있습니다.

1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.
  
2. 회사 또는 학교 계정을 사용하여 로그인합니다.

3. 보안 및 준수 센터의 왼쪽 창에서 & **검색**& 감사  >  **로그 검색을 선택 합니다.**

    감사 **로그 검색 페이지가** 표시됩니다.

    ![감사 로그 검색 페이지](../media/auditlogsearch1.png)
  
4. 다음과 같은 검색 조건을 구성합니다. 

    1. **작업** - 검색에서 모든 활동에 대한 감사 레코드를 반환할 수 있도록 이 필드를 비워 두십시오. 이 작업은 고객 Lockbox 요청 및 Microsoft 엔지니어가 수행한 해당 활동과 관련된 모든 감사 레코드를 반환하는 데 필요합니다.

    1. **시작 날짜** 및 **종료 날짜** - 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다.

    1. **사용자** - 이 필드를 비워 두십시오.

    1. **파일, 폴더 또는 사이트** - 이 필드는 비워 두십시오.

5. **검색** 을 클릭하여 검색 조건을 사용한 검색을 실행합니다. 

    검색 결과가 로드되고 몇 분 후에 감사 로그 검색 페이지의 결과 **아래에** **표시됩니다.**

6. 검색 **결과 페이지에서** 결과 필터링을 클릭하고 다음 중 하나를 선택합니다.

   - 조직에서 고객 Lockbox 요청을 승인하거나 거부하는 승인자와 관련된 감사 레코드를 표시하는 경우: 활동 열 아래에 있는 상자에 **Set-AccessToCustomerDataRequest를** 입력합니다. 

   - 승인된 고객 Lockbox 요청에 대한 응답으로 작업을 수행하는 Microsoft 엔지니어와 관련된 감사  레코드를 표시하기 위해 사용자 열 아래에 있는 상자에 **Microsoft 운영자를 입력합니다.** 작업 **열에는** 엔지니어가 수행한 작업이 표시됩니다.

      ![감사 레코드를 표시하기 위해 "Microsoft 연산자"를 필터링합니다.](../media/CustomerLockbox10.png)

7. 결과 목록에서 감사 레코드를 클릭하여 표시합니다.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>고객 Lockbox 액세스 요청에 대한 감사 레코드

조직의 사용자가 고객 Lockbox 요청을 승인하거나 거부하면 감사 레코드가 감사 로그에 기록됩니다. 이 레코드에는 다음 정보가 들어 있습니다.

| 감사 레코드 속성| 설명|
|:---------- |:----------|
| 날짜       | 고객 Lockbox 요청이 승인 또는 거부된 날짜 및 시간입니다.
| IP 주소 | 승인자가 요청을 승인하거나 거부하는 데 사용한 컴퓨터의 IP 주소입니다. |
| 사용자       | 서비스 계정은 \[ BOXServiceAccount@ \] .prod.outlook.com.            |
| 활동   | Set-AccessToCustomerDataRequest; 고객 Lockbox 요청을 승인하거나 거부할 때 기록되는 감사 활동입니다.                                |
| 항목       | 고객 Lockbox 요청의 Guid                             |

다음 스크린샷에는 승인된 Customer Lockbox 요청에 해당하는 감사 로그 레코드의 예가 나와 있습니다. Customer Lockbox 요청이 거부된 경우 **ApprovalDecision** 매개 변수의 값은 **Deny가 됩니다.**

![승인된 고객 Lockbox 요청에 대한 감사 레코드](../media/CustomerLockbox9.png)

> [!TIP]
> 감사 레코드에 자세한 정보를 표시하려면 추가 정보를 **클릭합니다.**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Microsoft 엔지니어가 수행한 작업의 감사 레코드

고객 Lockbox 요청이 승인된 후(그리고 고객 콘텐츠에 액세스하게 될 수 있는) Microsoft 엔지니어가 수행한 작업이 감사 로그에 기록됩니다. 이러한 레코드에는 다음 정보가 포함되어 있습니다.

| 감사 레코드 속성| 설명|
|:---------- |:----------|
| 날짜       | 작업이 수행된 날짜 시간입니다. 이 작업이 수행된 시간은 고객 Lockbox 요청이 승인된 후 4시간 이내에 수행됩니다.              |
| IP 주소 | Microsoft 엔지니어가 사용한 컴퓨터의 IP 주소입니다. |
| 사용자       | Microsoft 연산자 이 값은 이 레코드가 Customer Lockbox 요청과 관련이 있는 경우를 나타냅니다.                                  |
| 활동   | Microsoft 엔지니어가 수행한 활동의 이름입니다.|
| 항목       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>자주 묻는 질문

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>Customer Lockbox는 어떤 Microsoft 365 서비스에 적용하나요?

고객 Lockbox는 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에서 지원됩니다.

#### <a name="is-customer-lockbox-available-to-all-customers"></a>모든 고객이 고객 Lockbox를 사용할 수 있나요?

고객 Lockbox는 Microsoft 365 또는 Office 365 E5 구독에 포함되어 있으며 정보 보호 및 규정 준수 또는 고급 준수 추가 기능 구독을 사용하여 다른 계획에 추가할 수 있습니다. 자세한 내용은 [요금제](https://products.office.com/business/office-365-enterprise-e5-business-software) 및 가격을 참조하세요.

#### <a name="what-is-customer-content"></a>고객 콘텐츠란?

고객 콘텐츠는 Microsoft 365 서비스 및 응용 프로그램의 사용자가 만든 데이터입니다. 고객 콘텐츠의 예는 다음과 같습니다.

- 전자 메일 본문 또는 전자 메일 첨부 파일

- SharePoint 사이트 콘텐츠

- SharePoint 파일의 본문에 있는 정보

- 비즈니스용 Skype 프레젠테이션 파일 본문

- IM(인스턴트 메시지) 또는 음성 대화

- 고객 생성 Blob 또는 구조화된 저장소 데이터(예: SQL 컨테이너)

- 고객 소유의 보안 정보(예: 인증서, 암호화 키 및 암호)

- 고객 콘텐츠가 남아 있는 경우 유추 및 모든 후속 유추

Office 365의 고객 콘텐츠에 대한 자세한 내용은 [Office 365 트러스트 센터를 참조하세요.](https://products.office.com/business/office-365-trust-center-privacy/)

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>내 콘텐츠에 대한 액세스 요청이 있는 경우 누구에게 알림을 제공하나요?

전역 관리자와 Customer Lockbox 액세스 승인자 관리자 역할이 할당된 모든 사용자에게 알림을 제공합니다. 고객 Lockbox 요청을 승인할 수 있는 사용자도 마찬가지입니다.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>조직에서 이러한 요청을 승인하거나 거부할 수 있는 사람

전역 관리자와 Customer Lockbox 액세스 승인자 관리자 역할이 할당된 모든 사용자는 고객 Lockbox 요청을 승인할 수 있습니다. 고객은 조직에서 이러한 역할 할당을 제어합니다.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>Customer Lockbox에 옵트인(opt in)하는 방법

전역 관리자는 Microsoft 365 또는 Microsoft 365 관리 센터에서 고객 Lockbox를 사용하도록 설정하고 구성할 수 있습니다.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>고객 Lockbox 요청을 승인하는 경우 엔지니어가 할 수 있는 일과 Microsoft 엔지니어가 어떤 작업을 했는가를 어떻게 알 수 있나요?

고객 Lockbox 요청을 승인한 후 Microsoft 엔지니어는 사전 승인된 cmdlet을 사용하여 고객 콘텐츠에 액세스하는 데 필요한 권한을 부여했습니다. 고객 Lockbox 요청에 대한 응답으로 Microsoft 엔지니어가 수행한 작업은 보안 및 준수 센터의 감사 로그에 기록되어 & 액세스할 수 있습니다.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Microsoft가 승인 프로세스를 따르는지 어떻게 알 수 있나요?

Microsoft 365 관리 센터에서 고객 Lockbox 요청 기록을 사용하여 조직의 관리자 및 승인자에게 전송되는 전자 메일 승인 알림을 상호 참조할 수 있습니다.

고객 Lockbox는 최신 [SOC 1 SSAE 16 감사 보고서에 포함되어 있습니다.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports) 자세한 내용은 Microsoft Service Trust Portal에서 최신 보고서를 [찾을 수 있습니다.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft에서 내 테넌트의 승인자 목록을 수정할 수 있나요? 그렇지 않은 경우 어떻게 방지하나요?

조직의 전역 관리자만 고객 Lockbox 요청을 승인할 수 있는 대상을 지정할 수 있습니다. 즉, Azure Active Directory의 전역 관리자 그룹의 구성원만 요청을 승인할 수 있는 대상을 지정할 수 있습니다. Azure Active Directory의 전역 관리자 그룹 구성원은 조직에서만 관리합니다.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>승인하기 위해 콘텐츠 액세스 요청에 대한 자세한 정보가 필요한 경우 어떻게 하나요?

각 고객 Lockbox 요청에는 Microsoft 365 서비스 요청 번호가 포함되어 있습니다. Microsoft 지원 서비스에 문의하여 이 서비스 번호를 참조하여 요청에 대한 자세한 정보를 얻을 수 있습니다.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>고객 Lockbox 요청이 승인되면 사용 권한이 얼마나 오래 유효한가요?

현재 Microsoft 엔지니어에게 부여된 액세스 권한의 최대 기간은 4시간입니다. Microsoft 엔지니어가 더 짧은 기간을 요청할 수 있습니다.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>모든 고객 Lockbox 요청에 대한 기록은 어떻게 얻을 수 있나요?

모든 고객 Lockbox 요청은 Microsoft 365 관리 센터에서 볼 수 있습니다.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>콘텐츠 액세스 요청과 관련 감사 로그의 상관 관계는 어떻게 하나요?

준수 센터 활동 피드에는 고객 Lockbox의 로그 활동이 포함되어 있습니다. 고객은 받은 전자 메일 요청에 대해 활동 피드에서 고객 Lockbox 로그 활동을 상호 참조할 수 있습니다.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>고객이 고객 Lockbox 요청에 응답하지 않는 경우 어떻게 하나요?

고객 Lockbox 요청의 기본 기간은 12시간입니다. 12시간 이내에 요청에 응답하지 않는 경우 요청이 만료됩니다.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>고객이 고객 Lockbox 요청을 거부할 때 Microsoft는 어떤 작업을 하나요?

고객이 고객 Lockbox 요청을 거부하면 고객 콘텐츠에 대한 액세스 권한이 없습니다. 조직의 사용자가 계속해서 Microsoft에서 고객 콘텐츠에 액세스하여 문제를 해결해야 하는 서비스 문제가 계속 발생하면 서비스 문제가 지속될 수 있으며 Microsoft는 사용자에게 이를 알릴 수 있습니다.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>고객 Lockbox가 사법 기관 또는 기타 타사의 데이터 요청으로부터 보호하나요?

아니요. Microsoft는 고객 데이터에 대한 타사 요청을 심각하게 처리합니다. 클라우드 서비스 공급자인 Microsoft는 항상 고객 데이터의 개인 정보 보호를 지지합니다. 소속된 경우 Microsoft는 항상 타사를 고객에게 리디렉션하여 정보를 얻습니다. (Brad Smith의 블로그 읽기: 정부 스누프로부터 고객 [데이터 보호).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Microsoft가 수신하는 [](https://www.microsoft.com/corporate-responsibility/lerr) 사법 기관 요청에 대한 자세한 정보를 주기적으로 게시합니다.

자세한 내용은 타사 데이터 요청과 [관련한 Microsoft](https://www.microsoft.com/trustcenter/default.aspx) 보안 센터 및 온라인 [](https://www.microsoft.com/Licensing/product-licensing/products.aspx) 서비스 약관의 "고객 데이터 공개" 섹션을 참조하세요.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Microsoft는 직원의 구성원이 Office 365 응용 프로그램의 고객 콘텐츠에 대한 정식 액세스 권한을 하지 않도록 어떻게 보장하나요?

Microsoft는 액세스 제어 시스템을 통해 광범위한 예방 조치와 이러한 액세스 제어 시스템을 우회하려는 시도를 식별하고 해결하기 위한 감지 조치를 구현합니다. Microsoft 365는 최소 권한 및 Just-In-Time 액세스 원칙을 통해 운영됩니다. 따라서 Microsoft 직원은 지속적인 기준에 따라 고객 콘텐츠에 액세스할 수 있는 권한이 없습니다. 권한이 부여된 경우 제한된 기간 동안만 사용할 수 있습니다. 

Microsoft 365는 *Lockbox라는* 액세스 제어 시스템을 사용하여 서비스 내에서 운영 및 관리 기능을 수행할 수 있는 권한을 부여하는 사용 권한 요청을 처리합니다. 운영자는 Lockbox를 사용하여 고객 콘텐츠에 대한 액세스를 요청해야 합니다. 그러면 액세스 권한이 부여되기 전에 두 번째 사람이 요청(예: 승인)을 수행해야 합니다. 두 번째 사람은 요청자가 될 수 없습니다. 고객 콘텐츠에 대한 액세스를 승인하려면 해당 요청을 지정해야 합니다. 요청이 승인된 경우만 운영자가 고객 콘텐츠에 대한 임시 액세스를 획득합니다. 권한 상승 기간이 만료되면 Lockbox는 액세스를 해지합니다.

Microsoft 일반 [보안](https://www.microsoft.com/licensing/product-licensing/products) 사례에 대한 자세한 내용은 온라인 서비스 약관을 참조하세요.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>Microsoft 엔지니어가 내 콘텐츠에 액세스해야 하는 상황

Microsoft 엔지니어가 고객 콘텐츠에 액세스해야 하는 가장 일반적인 시나리오는 고객이 문제 해결을 위해 액세스가 필요한 지원 요청을 하는 경우입니다. Microsoft 365의 기본 원칙은 Microsoft에서 고객 콘텐츠에 액세스하지 않고도 서비스가 운영되는 것입니다. Microsoft에서 수행한 거의 모든 서비스 작업은 완전히 자동화되고 사람 개입은 고객 콘텐츠에서 완전히 제어되고 추상화됩니다. Microsoft 365의 목표는 고객이 Microsoft 액세스에 대한 특정 요청을 승인할 때까지 서비스를 지원하기 위한 고객 콘텐츠에 액세스하는 것입니다.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Microsoft 클라우드를 사용하여 데이터를 안전하게 보호할 수 있는 것으로 생각한 경우 고객 Lockbox가 필요한 이유는 무엇일까요?

고객 Lockbox는 고객에게 서비스 작업에 대한 명시적 액세스 권한을 부여하는 기능을 제공하여 추가 제어 계층을 제공합니다. 또한 고객 Lockbox는 명시적 데이터 액세스 권한 부여를 위한 절차가 수락된 것으로 고객에게 HIPAA 및 FEDRAMP와 같은 특정 규정 준수 의무를 충족하는 데 도움이 됩니다.
