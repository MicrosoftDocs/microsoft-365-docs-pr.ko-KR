---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 사전 작업
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우 사전 작업입니다.'
ms.openlocfilehash: 5110c6bd86d5df35a7ceccb4abfedf059cb826d0
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826179"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 사전 작업

다음 링크를 사용하여 조직과 관련된 사전 작업 단계로 연결합니다.

- 도이클란드 Microsoft 클라우드에서 Office 365를 사용하는 모든 고객의 경우 다음 [단계를 수행합니다.](#applies-to-everyone)
- Exchange Online 또는 Exchange 하이브리드를 사용하는 경우 이 [단계를 합니다.](#exchange-online)
- SharePoint Online을 사용하는 경우 이 [단계를 합니다.](#sharepoint-online)
- 타사 MDM(모바일 장치 관리) 솔루션을 사용하는 경우 이 [단계를 합니다.](#mobile)
- Office 365와 통합된 타사 서비스 또는 LOB(LOB) 앱을 사용하는 경우 이 [단계를 실행합니다.](#line-of-business-apps)
- Office 365 구독에 포함된 서비스 이상으로 Azure 서비스를 사용하는 경우 이 [단계를 진행합니다.](#microsoft-azure)
- Dynamics 365도 사용하는 경우 이 [단계를 진행합니다.](#dynamics365)
- Power BI도 사용하는 경우 이 [단계를 합니다.](#power-bi)
- DNS 변경의 경우 이 [단계를 합니다.](#dns)
- 페더티된 ID를 사용하는 경우 다음 [단계를 수행합니다.](#federated-identity)

## <a name="applies-to-everyone"></a>모든 사람에 적용

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 후 클라이언트를 다시 시작하고 클라이언트에서 로그인 및 로그인하는 방법을 사용자에게 알릴 준비를 합니다. | Office 클라이언트 라이선스는 마이그레이션 시 도이치클란드 Microsoft 클라우드에서 Office 365 서비스로 전환됩니다. 클라이언트는 Office 클라이언트에서 로그인한 후 유효한 새 라이선스를 선택 합니다. | 사용자의 Office 제품은 Office 365 서비스에서 라이선스를 새로 고쳐야 합니다. 라이선스를 새로 고치지 않은 경우 Office 제품에서 라이선스 유효성 검사 오류가 발생할 수 있습니다. |
| [Office 365](https://aka.ms/o365urls)서비스 URL 및 IP 주소에 대한 네트워크 연결을 확인합니다. | Office 365 서비스에 액세스하는 데 사용되는 고객이 호스팅하는 모든 클라이언트 및 서비스는 Office 365 전역 서비스 끝점에 액세스할 수 있어야 합니다. <br>사용자 또는 공동 작업 파트너가 Office 365 서비스 URL 및 IP 주소에 나열된 URL 및 IP 주소에 액세스하지 못하게 하는 방화벽 규칙이 있는 경우 [Office 365](https://aka.ms/o365urls) 전역 서비스 끝점에 대한 액세스를 허용하는 방화벽 규칙을 변경해야 합니다.| 4단계 전에 이 단계를 수행하지 않은 경우 서비스 또는 클라이언트 소프트웨어 오류가 발생할 수 있습니다.  |
| 평가판 구독을 취소합니다. | 평가판 구독은 마이그레이션되지 않습니다. 유료 구독의 전송이 차단됩니다. | 취소 후 사용자가 액세스하는 경우 평가판 서비스가 만료되고 작동하지 않습니다. |
| 도이클란드 Microsoft 클라우드와 Office 365 서비스 간의 라이선스 기능 차이를 분석합니다. | Office 365 서비스에는 현재 Microsoft 클라우드 도이치랜드에서 사용할 수 없는 추가 기능 및 서비스가 포함되어 있습니다. 구독을 전송하는 동안 사용자가 새 기능을 사용할 수 있습니다. | <ul><li> 도이클란드 Microsoft 클라우드 및 Office 365 서비스 라이선스에서 제공하는 다양한 기능을 분석합니다. [Office 365 플랫폼 서비스 설명으로 시작하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> 사용자 또는 사용자 변경 관리에 대한 영향을 제한하기 위해 Office 365 서비스의 새 기능을 처음에 사용하지 않도록 설정해야 하는지 여부를 결정하고 필요한 경우 사용자 라이선스 할당을 변경합니다. </li><li>Office 365 서비스에서 제공하는 새 서비스 및 기능에 대해 사용자 및 지원 센터 직원을 준비합니다. |
| 마이그레이션 중 [](https://docs.microsoft.com/microsoft-365/compliance/retention) 콘텐츠를 무단으로 삭제하는 것을 방지하는 조직 전체 보존 정책을 만들 수 있습니다.  |<ul><li>마이그레이션 중에 최종 사용자가 콘텐츠를 부수적으로 삭제하지 않도록 조직 전체 보존 정책을 사용하도록 설정할 수 있습니다. </li><li>보존은 필요하지는 않습니다. 마이그레이션 중에 언제든지 배치되는 보류는 예상대로 작동해야 하기 때문에 보존 정책을 보유하는 것은 백업 안전 메커니즘입니다. 동시에 일부 고객, 특히 보존이 우려되는 고객은 보존 정책을 사용할 수 없습니다.</li></ul>| 보존 정책 및 보존 레이블에 대해 자세히 설명에 [설명된 보존 정책을 적용합니다.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 서비스 또는 클라이언트 소프트웨어의 오류는 9단계 중 4단계 전에 수행되지 않은 경우 발생할 수 있습니다. </li></ul>|
| 올바른 라이선스 과부하 | 특정 상황에서는 고객이 구입한 것보다 더 많은 서비스를 사용할 수 있습니다. 이 조건을 라이선스 과부하라고 합니다. Microsoft는 독일 Microsoft 클라우드에서 독일 데이터 센터 지역으로 라이선스 과도하게 계약된 고객을 마이그레이션할 수 없습니다. 서비스 및 데이터에 지속적으로 액세스하려면 할당된 모든 사용자에게 라이선스가 필요합니다. | 모든 고객 | 고객은 추가 라이선스를 구입하거나 사용자의 라이선스를 배포하여 라이선스 과도하게 조건을 평가하고 해결해야 합니다. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>AD FS(Active Directory Federation Services)

**적용 사항:** AD FS를 사용하여 Microsoft Office 365에 연결하는 사용자를 인증하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| [재해 복구 시나리오를 위한 AD FS(Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) 팜 백업 | 고객은 도메인의 발급자 URI를 터치하지 않고도 & 글로벌 트러스트에 대한 신뢰 파티 트러스트가 복원될 수 있도록 AD FS 팜을 적절하게 백업해야 합니다. 필요한 경우 팜의 백업 및 각 복원에 AD FS 신속 복원을 사용하는 것이 좋습니다. | 필수 작업. 고객의 AD FS 팜에 오류가 발생하면 마이그레이션 중에 서비스가 영향을 미치게 됩니다. 자세한 내용은 [ADFS 마이그레이션 단계를 참조하세요.](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange Online

**적용 날짜:** 일정 및 가용성 주소 공간 공유를 사용하도록 설정한 Exchange Online 고객에게 적용됩니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 서비스로의 예정된 전환을 외부 파트너에게 알릴 수 있습니다. | 가용성 주소 공간 구성을 사용하면 Office 365와 사용 가능한/사용 가능한 정보를 공유할 수 있습니다. | 이 작업을 수행하지 못하면 이후 고객 마이그레이션 단계에서 서비스 또는 클라이언트 오류가 발생될 수 있습니다. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online 하이브리드 구성

**적용 사항:** 활성 Exchange 하이브리드 구성을 사용 하는 Exchange Online 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 테넌트가 마이그레이션 단계 5에 들어가기 전에 언제든지 최신 버전의 HCW(하이브리드 구성 마법사)로 업데이트합니다. Office 365 테넌트 마이그레이션이 시작된 메시지 센터 알림을 받은 직후에 이 활동을 시작할 수 있습니다.<br><br> Microsoft 클라우드 도이클란드 하이브리드 Exchange Online 고객은 이전 버전의 HCW를 제거한 다음 에서 최신 버전(17.0.5378.0 이상)을 설치 및 실행해야 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 합니다. |<ul><li>HCW의 최신 버전에는 도이클란드 Microsoft 클라우드에서 Office 365 서비스로 전환하는 고객을 지원하기 위해 필요한 업데이트가 포함되어 있습니다.</li><li> 업데이트에는 송신 커넥터 및 수신 커넥터에 대한 사내 인증서 설정이 변경됩니다.</li><li> Exchange 관리자는 5단계 중 9단계(Exchange 마이그레이션)가 시작되기 전에 언제든지 HCW를 다시 설치해야 합니다.<br>5단계 전에 HCW를 실행할 때 내 Office 365 조직 아래의 목록 상자에서 _Office 365 Exchange Online_ 아래의 HCW의 2nd 페이지에서 _"Office 365 Germany"를_ 선택합니다.</li><li>**참고:** Office 365 테넌트 마이그레이션이 완료되면 HCW의 2nd 페이지에서 "Office 365 Worldwide" 설정을 사용하여 HCW를 제거하고 다시 설치하여 Exchange Online 전역 서비스로 하이브리드 설정을 완료합니다.</li></ul>|5단계(Exchange 마이그레이션) 전에 HCW를 실행하지 못하면 서비스 또는 클라이언트 오류가 발생합니다. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**적용 사항:** SharePoint 2013을 사용하는 고객


| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| SharePoint Online 마이그레이션 중에 SharePoint 2013 워크플로를 제한합니다. | 전환 전에 SharePoint 2013 워크플로를 줄이고 진행 중 워크플로를 완료합니다. | 비활성으로 인해 사용자에게 혼동을 주며 지원 센터 통화가 있을 수 있습니다. |
||||

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

**적용 사항:** 비즈니스용 Skype Online 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 독일의 비즈니스용 Skype에 액세스하는 사용자를 위해 Teams 데스크톱 클라이언트를 배포합니다. | 마이그레이션은 공동 작업, 통화 및 채팅을 위해 비즈니스용 Skype 사용자를 Microsoft Teams로 이동합니다. Microsoft Teams 데스크톱 클라이언트를 배포하거나 지원되는 브라우저를 사용할 수 있도록 합니다. | 비활성화하면 Microsoft Teams 공동 작업 서비스를 사용할 수 없게 됩니다. |
| 마이그레이션 관련 DNS 변경 내용을 검토하고 준비합니다. | 비즈니스용 Skype Online에 대한 고객 소유 DNS 영역 변경 |<ul><li>DNS 레코드를 새로 고치기 위해 고객 소유 도메인 DNS 레코드의 TTL(Time-to-Live)을 5분으로 업데이트하는 것이 좋습니다. 그러나 이 DNS와 연결된 Microsoft 관리 컷오버 변경은 제공된 24시간 변경 기간 내에 언제든지 발생할 수 있습니다. </li><li>향후에는 서비스가 중단될 수 있습니다. 사용자는 비즈니스용 Skype에 로그인할 수 없습니다. Office 365 서비스의 마이그레이션된 Teams 환경으로 리디렉션됩니다. </li></ul>|
| Microsoft Teams로의 전환을 위한 최종 사용자 및 관리 교육 및 준비를 준비합니다. | 사용자 커뮤니케이션 및 준비를 계획하여 Skype에서 Teams로 전환하는 데 성공하세요. | <ul><li>클라이언트는 새 서비스와 해당 서비스가 Office 365 서비스로 전환된 후 사용하는 방법을 알고 있어야 합니다. </li><li>고객 베니티 도메인과 초기 도메인에 대해 DNS를 변경한 후 사용자는 비즈니스용 Skype에 로그인하고 이제 Teams로 마이그레이션된 것으로 표시됩니다. 또한 백그라운드에서 Teams용 데스크톱 클라이언트를 다운로드합니다. </li></ul>|
||||

## <a name="mobile"></a>모바일

타사 MDM(모바일 장치 관리) 솔루션을 사용하는 경우:

| Step(s) | 설명 | 적용 대상 | 영향 |
|:-------|:-----|:-------|:-------|
| iOS 및 Android용 Microsoft Outlook에서 계정을 제거하고 다시 추가하는 사용자에 대한 최종 사용자 및 관리 교육을 준비합니다. | Microsoft 클라우드 도이치랜드의 사서함으로 구성된 iOS 및 Android용 Microsoft Outlook 계정을 제거하고 Outlook에 다시 추가해야 새 Office 365 서비스 구성을 제대로 동기화할 수 있습니다. | iOS 및 Android용 Microsoft Outlook 고객 | 이전에 도이치클란드 Microsoft 클라우드에 대해 구성된 Outlook 사서함은 새 Office 365 서비스 구성을 선택하지 않을 수 있으며, 이로 인해 다른 사용자 환경의 오류 및 성능이 저하될 수 있습니다. IT 관리자는 마이그레이션 후 로그인 또는 메일 동기화에 문제가 발생하는 경우 사용자에게 계정을 제거하고 iOS 및 Android용 Microsoft Outlook에 다시 추가하도록 지시하는 문서를 제공하는 것이 권장됩니다. |
| 마이그레이션 후 다시 구성해야 하는지 여부를 판단합니다. | MDM(모바일 장치 관리) 솔루션은 끝점을 `outlook.de` 대상으로 할 수 있습니다. 이 Office 365 서비스로 전환할 때 클라이언트 프로필은 Office 365 서비스 URL 으로 업데이트해야 `outlook.office365.com` 합니다. | Exchange Online 및 MDM 고객 | 끝점에 액세스할 수 있는 동안 클라이언트가 계속 작동하지만 도이치클라드 Microsoft 클라우드 끝점을 더 이상 사용할 수 없는 경우 `outlook.de` 실패합니다. |
|||||

## <a name="line-of-business-apps"></a>업무용 앱

Office 365와 통합된 타사 서비스 또는 LOB(LOB) 앱을 사용하는 경우: 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 후 다시 구성해야 하는지 여부를 판단합니다. | Office 365와 통합되는 타사 서비스 및 응용 프로그램은 도이치랜드 Microsoft 클라우드 IP 주소 및 URL을 예상하여 코딩될 수 있습니다. | 필수 작업입니다. 비활성으로 인해 서비스 또는 클라이언트 소프트웨어가 실패할 수 있습니다. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**적용 사항:** Microsoft Dynamics를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Dynamics 365 샌드박스 구독의 경우 Dynamics SQL 인스턴스의 프로덕션 환경을 Microsoft 클라우드 도이클랜드의 Dynamics 365 구독에서 다운로드해야 합니다. 샌드박스 마이그레이션 전에 최신 프로덕션 백업을 샌드박스로 복원해야 합니다. | Dynamics 365를 마이그레이션하려면 고객이 샌드박스 환경을 최신 프로덕션 데이터베이스로 새로 고쳐야 합니다. | FastTrack 팀은 고객이 건조 실행을 수행하여 8.x에서 9.1.x로 버전 업그레이드의 유효성을 검사하는 데 도움을 주게 됩니다. |
||||

## <a name="power-bi"></a>Power BI

**적용 사항:** Power BI 고객 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Power BI Microsoft 클라우드 도이클랜드에서 Office 365 서비스로 마이그레이션되지 않는 Power BI 구독에서 개체 제거 | Power BI 서비스를 마이그레이션하려면 데이터 집합 및 대시보드와 같은 특정 아티팩트를 삭제하기 위한 고객 작업이 필요합니다. | <ul><li>관리자는 구독에서 다음 항목을 제거해야 할 수 있습니다. </li><li>Real-Time 데이터 집합(예: 스트리밍 또는 푸시 데이터 집합) </li><li>Power BI 사내 데이터 게이트웨이 구성 및 데이터 원본 </li></ul>|
||||

## <a name="dns"></a>DNS

**적용 프로그램:** Office 데스크톱 클라이언트를 사용하는 고객(Microsoft 365 앱, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Azure AD(Azure Active Directory) 컷오버 전에 언제든지 고객 소유 DNS에서 MSOID, CName을 제거합니다. 변경이 빠르게 적용될 수 있도록 5분의 TTL을 설정할 수 있습니다.

## <a name="federated-identity"></a>페더레이션 ID

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 기존 신뢰 파티 트러스트에 SSO(Single Sign-On)에 대한 식별자를 추가하고 AD FS 메타데이터 자동 업데이트를 사용하지 않도록 설정합니다. | 마이그레이션을 시작하기 전에 AD FS 신뢰 파티 트러스트에 ID를 추가해야 합니다. 실수로 해당 ID가 제거되는 것을 방지하려면 메타데이터 업데이트에 대해 자동 업데이트를 사용하지 않도록 설정하십시오. <br><br> AD FS 서버에서 다음 명령을 단일 명령줄로 실행합니다. <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| 페더러드 인증 조직 | 필수 작업. 9단계 중 4단계(SharePoint) 이전의 비활성 상태는 마이그레이션 중에 서비스에 영향을 미치게 됩니다.  |
| 전역 Azure AD 끝점에 대한 신뢰 파티 트러스트 생성 | 고객은 전역 끝점에 대한 RPT(신뢰자 트러스트)를 수동으로 [만들어야](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 합니다. 이 작업에서는 GUI를 통해 새 RPT를 추가한 다음 [Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 클레임 규칙(AD FS 도움말에서)을 사용하여 클레임 규칙을 생성하고 RPT로 가져와서 수행됩니다. | 페더러드 인증 조직 | 필수 작업. 비활성 상태는 마이그레이션 중에 서비스에 영향을 미치게 됩니다. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

도이치랜드 Microsoft 클라우드 인스턴스에서 Office 365 및 Microsoft Azure에 대해 동일한 Azure Active Directory ID 파티션을 사용하는 경우 Microsoft Azure 서비스의 고객 기반 마이그레이션을 준비하고 있는지 확인합니다.
Office 365 테넌트가 마이그레이션 단계 3에 도달하기 전에 Microsoft Azure 서비스의 마이그레이션을 시작하지 말고 마이그레이션 8단계가 완료되기 전에 완료해야 합니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 사용하려는 Azure 서비스를 결정하고 파트너와 협력하여 독일에서 Office 365 서비스 테넌트로의 향후 마이그레이션을 준비합니다. Azure 마이그레이션 [플레이북에 설명된 단계를 따릅니다.](https://docs.microsoft.com/azure/germany/germany-migration-main) |<ul><li>Azure 리소스 마이그레이션은 고객의 책임이 있으며, 정해진 단계에 따라 수동으로 노력해야 합니다. 조직에서 사용하려는 서비스를 이해하는 것은 Azure 서비스의 성공적인 마이그레이션을 위한 핵심입니다. </li><li> 동일한 ID 파티션(조직)에 Azure 구독이 있는 Office 365 Germany 고객은 구독 및 서비스 마이그레이션을 시작할 수 있는 경우 Microsoft에서 정한 순서를 따라야 합니다.</li></ul>|<ul><li>고객은 여러 Azure 구독을 사용할 수 있으며 각 구독에는 인프라, 서비스 및 플랫폼 구성 요소가 포함됩니다. </li><li> 관리자는 이 마이그레이션 이벤트의 일부로 신속한 마이그레이션 및 유효성 검사가 가능하도록 구독 및 관련자를 파악해야 합니다. </li><li>이러한 구독 및 정해진 시간 내에 Azure 구성 요소의 마이그레이션을 성공적으로 완료하지 못하면 Office 및 Azure AD가 Office 365 서비스로의 전환 완료에 영향을 미치며 데이터 손실이 발생하게 될 수 있습니다. </li><li> 메시지 센터 알림은 고객이 주도하는 마이그레이션을 시작할 수 있는 지점을 신호합니다. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
