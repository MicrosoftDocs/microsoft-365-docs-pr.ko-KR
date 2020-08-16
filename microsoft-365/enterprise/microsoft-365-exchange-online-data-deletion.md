---
title: Microsoft 365 Exchange Online 데이터 삭제
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 사서함에 대 한 소프트 및 하드 데이터 삭제가 Exchange Online에서 처리 되는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4b4d30da70001967ca73377f10a4cd417577b72
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696317"
---
# <a name="exchange-online-data-deletion-in-microsoft-365"></a>Microsoft 365에서 Exchange Online 데이터 삭제

Exchange Online 내에는 두 가지 유형의 삭제 (소프트 삭제 및 하드 삭제)가 있습니다. 이는 사서함에 있는 모든 사서함과 항목에 적용 됩니다.

## <a name="soft-deleted-and-hard-deleted-mailboxes"></a>일시 삭제 되 고 영구 삭제 된 사서함
일시 삭제 된 사용자 사서함은 Microsoft 365 관리 센터 또는 사서함 제거 cmdlet을 사용 하 여 삭제 되었으며 30 일 이내에 여전히 Azure Active Directory 휴지통에 남아 있는 사서함입니다. 다음 방법 중 하나를 사용 하 여 사서함을 일시 삭제할 수 있습니다.
- 사용자 사서함의 연결 된 Azure Active Directory 사용자 계정이 일시 삭제 됩니다 (사용자 개체가 범위를 벗어나 있거나 휴지통 컨테이너에 없음).
- 사용자 사서함의 연결 된 Azure Active Directory 사용자 계정이 영구적으로 삭제 되었지만 Exchange Online 사서함이 소송 보존 또는 eDiscovery 보존 상태에 있습니다.
- 사용자 사서함의 연결 된 Azure Active Directory 사용자 계정이 지난 30 일 이내에 제거 되었습니다. Exchange Online의 최대 보존 길이는 영구적으로 제거 되 고 복구할 수 없게 되는 일시 삭제 된 상태로 유지 됩니다.

영구적으로 삭제 된 사용자 사서함은 다음 방법 중 하나를 사용 하 여 삭제 된 사서함입니다.
- 사용자 사서함이 30 일 넘게 일시 삭제 되었으며, 연결 된 Azure Active Directory 사용자가 영구적으로 삭제 되었습니다. 전자 메일, 연락처, 파일 등의 모든 사서함 콘텐츠가 영구적으로 삭제 됩니다.
- 사용자 사서함에 연결 된 사용자 계정이 Azure Active Directory에서 영구적으로 삭제 되었습니다. 이제 사용자 사서함은 Exchange Online에서 일시 삭제 되며 30 일 동안 일시 삭제 된 상태로 유지 됩니다. 30 일 동안 새 Azure Active Directory 사용자가 같은 **ExchangeGuid** 또는 **ArchiveGuid**을 사용 하는 원래 받는 사람 계정과 동기화 되 고 새 계정에 Exchange Online에 대 한 사용이 허가 된 경우 원래 사용자 사서함이 영구적으로 삭제 됩니다. 전자 메일, 연락처, 파일 등의 모든 사서함 콘텐츠가 영구적으로 삭제 됩니다.
- 일시 삭제 된 사서함은 **PermanentlyDelete 제거**를 사용 하 여 삭제 됩니다.

위의 삭제 시나리오에서는 사용자 사서함이 소송 보존 또는 eDiscovery 보류와 같은 보존 상태에 있지 않은 것으로 가정 합니다. 사서함에 보류 중인 형식이 있으면 사서함을 삭제할 수 없습니다. 모든 메일 사용자 받는 사람 유형에 대해 모든 [보류](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e?ui=en-US&rs=en-US&ad=US) 설정은 무시 되며, 하드 삭제 또는 소프트 삭제에는 영향을 주지 않습니다.

## <a name="soft-deleted-and-hard-deleted-items"></a>일시 삭제 되 고 영구 삭제 된 항목
사용자가 사서함 항목 (예: 전자 메일 메시지, 연락처, 일정 약속 또는 작업)을 삭제 하면 항목은 복구 가능한 항목 폴더 및 "delete" 라는 하위 폴더로 이동 됩니다. 이를 일시 삭제 라고 합니다. 삭제 되는 항목을 삭제 폴더에 보관 하는 기간 사서함에 대해 설정 된 항목 보존 기간에 따라 달라 집니다. Exchange Online 사서함은 기본적으로 14 일 동안 삭제 된 항목을 유지 하지만 Exchange Online 관리자는이 설정을 변경 하 여 최대 30 일까지 기간을 늘릴 수 있습니다. Exchange Online 사서함에 대해 삭제 된 항목 보존 기간을 늘리는 자세한 단계는 [Exchange online 사서함에 영구적으로 삭제 되는 항목을 변경 하](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention)는 기간 변경을 참조 하십시오. 사용자는 삭제 된 항목의 보존 시간이 만료 되기 전에 지운 편지함을 복구 하거나 제거할 수 있습니다. 이렇게 하려면 Microsoft Outlook 또는 웹용 Outlook에서 삭제 된 항목 복구 기능을 사용 합니다.

사용자가 Outlook 또는 웹용 Outlook에서 지운 편지함 복구 기능을 사용 하 여 삭제 된 항목을 제거 하는 경우이를 하드 삭제 라고 합니다. Exchange Online에서는 새 사서함을 만들 때 기본적으로 단일 항목 복구를 사용 하도록 설정 되므로 삭제 된 항목 보존 기간이 만료 되기 전에는 관리자가 여전히 영구 삭제 된 항목을 [복구할](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/recover-deleted-messages) 수 있습니다. 또한 사용자 또는 프로세스에 의해 메시지가 변경 되는 경우에는 단일 항목 복구를 사용 하는 경우에도 원본 항목의 복사본이 보존 됩니다.

## <a name="page-zeroing"></a>페이지 비우기
*제로화* 는 삭제 된 데이터에 대 한 0 또는 이진 패턴을 기록 하 여 삭제 한 데이터를 복구 하기가 더 어려워질 수 있는 보안 메커니즘입니다. Exchange Online에서 사서함 데이터베이스는 *페이지* 를 저장소 단위로 사용 하며, *페이지 비우기*라는 덮어쓰기 프로세스를 구현 합니다. 페이지 비우기는 기본적으로 사용 하도록 설정 되어 있으며, 고객 또는 Microsoft에서 사용 하지 않도록 설정할 수 없습니다. 페이지 비우기 작업은 트랜잭션 로그 파일에 기록 되므로 지정 된 데이터베이스의 모든 복사본은 비슷한 방식으로 페이지를 0으로 변환 될 수 있습니다. 활성 데이터베이스 복사본에서 페이지를 비우면 데이터베이스의 수동 복사본에서 페이지가 0이 됩니다.

페이지 비우기는 하드 삭제 된 레코드 위에 이진 패턴을 씁니다. 페이지 비우기 패턴은 ESE (Extensible Storage Engine) 작업 (Exchange Online의 서버에서 사용 하는 내부 데이터베이스 엔진의 이름)과 관련 되어 있으며, 런타임 작업 및 백그라운드 데이터베이스 유지 관리 작업에 따라 다릅니다. (백그라운드 데이터베이스 유지 관리는 각 데이터베이스를 지속적으로 검사 하 고 검색 하는 프로세스입니다. 기본 기능은 체크섬 데이터베이스 페이지에 대 한 것 이지만, 저장소 충돌로 인해 지우지 못한 레코드 및 페이지를 지우고 공간 정리를 처리 합니다.

다음 표에는 특정 런타임 작업에 해당하는 채우기 패턴이 나와 있습니다.

| ESE 런타임 작업   | 채우기 패턴 |
|--------------------------|--------------|
| 바꾸기                  | 이력서            |
| 레코드/Long 값 삭제 | D            |
| 비운 페이지 공간         | 도움말            |


다음 표에는 ESE 백그라운드 데이터베이스 유지 관리 중에 발생하는 특정 작업에 해당하는 채우기 패턴이 나와 있습니다.

| ESE 백그라운드 데이터베이스 유지 관리 작업 | 채우기 패턴 |
|-----------------------------------------------|--------------|
| 레코드 삭제                                 | D            |
| Long 값 삭제                             | 자            |
| 부분적으로 사용된 페이지의 비운 페이지 공간       | Z            |
| 사용되지 않은 페이지의 비운 페이지 공간               | &            |


### <a name="page-zeroing-process"></a>페이지 비우기 프로세스
페이지 비우기 프로세스는 삭제 시나리오에 따라 달라 집니다. 다음 표에서는 데이터베이스 삭제 시나리오 및 페이지 비우기 기능이 수행되는 시기에 대해 설명합니다.

| 데이터베이스 삭제 시나리오 | 데이터베이스 데이터를 비우기 위한 ESE 프로세스 및 시간대 |
|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 삭제 된 항목 보존 기간에 따라 항목이 만료 됩니다. | 비동기 스레드는 삭제된 데이터를 바이너리 패턴으로 덮어씁니다. 이 작업은 레코드 삭제 후 몇 밀리초 이내에 발생합니다. 비동기 비우기 작업이 계속 진행 되는 동안 저장소 프로세스가 중단 되는 경우 (또는 버전 저장소 성장으로 인해 버전 저장소 정리가 취소 됨), 백그라운드 데이터베이스 유지 관리가 데이터베이스의 해당 섹션을 처리할 때 비우기가 완료 됩니다. |
| 시나리오 보기: 웹 폴더 보기에서 Outlook/Outlook의 항목 만료 (예를 들어, 대화 보기) | 백그라운드 데이터베이스 유지 관리가 데이터베이스의 해당 섹션을 처리할 때 데이터 비우기가 발생합니다. |
| 사서함 이동/사서함 삭제 시나리오: 원본 사서함 삭제 (삭제 된 사서함 만료) | 백그라운드 데이터베이스 유지 관리가 데이터베이스의 해당 섹션을 처리할 때 데이터 비우기가 발생합니다. |

### <a name="mailbox-data-types-without-page-zeroing"></a>페이지 비우기 없는 사서함 데이터 형식
다음 사서함 데이터 형식은 페이지 비우기에 대 한 프로 비전을 갖고 있지 않습니다.
- **사서함 데이터베이스 트랜잭션 로그** -트랜잭션 로그가 일반 작업의 일부로 삭제 되 면 파일 시스템에서 삭제 된 로그 파일을 저장 한 블록을 0으로 변환 하는 프로세스가 수행 되지 않습니다. 파일 시스템이 새로 만든 로그에 대 한 사용 가능한 공간을 빠르게 다시 사용할 수 있지만이 경우에는 그렇지 않을 수도 있습니다.
- **콘텐츠 인덱스 카탈로그 파일** -Exchange Online은 검색 인덱싱 기능에 검색 파운데이션 (FAST 라고도 함)을 사용 합니다. 검색 인덱스 카탈로그는 사서함 데이터베이스 파일과 동일한 볼륨에 저장 된 수십 개의 파일로 구성 되어 있습니다. 메시지가 사서함 데이터베이스에서 영구 삭제될 때 검색 카탈로그의 연결된 콘텐츠는 즉시 삭제되지 않습니다. 콘텐츠 삭제는 Search Foundation에서 여러 작은 카탈로그 파일을 단일 큰 파일에 섀도 (또는 마스터 병합) 할 때 발생 합니다. 마스터 병합이 완료된 후 작은 카탈로그 파일은 삭제됩니다. 삭제된 카탈로그 파일이 저장된 블록을 비우는 프로세스는 없습니다.

## <a name="continuous-replication"></a>연속 복제
연속 복제 (로그 전달 및 재생이 라고도 함)는 Exchange Online의 기술로, 모든 사서함 데이터베이스의 복사본을 만들고 유지 관리 하 여 고가용성, 사이트 복구 및 재해 복구를 제공 합니다. 연속 복제는 Exchange Server 데이터베이스 크래시 복구 지원을 활용 하 여 하나 이상의 사서함 데이터베이스 복사본에 대 한 비동기 업데이트를 수행 하는 기술을 제공 합니다. 각 사서함 서버는 활성 데이터베이스 (예: 사용자 전자 메일 활동)에서 수행한 데이터베이스 업데이트를 1mb의 순차적인 로그 파일 집합으로 기록 합니다. 이 파일 집합을 로그 스트림 이라고 합니다. 연속 복제에서는 로그 스트림을 사용 하 여 하나 이상의 데이터베이스 복사본을 비동기적으로 업데이트할 수도 있습니다. 이 작업은 활성 데이터베이스의 수동 복사본을 포함 하는 위치로 로그를 전송 하 고 수동 데이터베이스 복사본으로 재생 하는 방식으로 수행 됩니다. 활성 데이터베이스의 모든 로그가 데이터베이스의 수동 복사본에 대해 재생 되는 경우에는 두 데이터베이스가 동일 하며,이 프로세스를 통해 활성 데이터베이스에 대 한 실제 변경 내용이 해당 데이터베이스의 모든 수동 복사본에 복제 됩니다.

사서함 데이터베이스에서 사서함 항목이 나 전체 사서함을 삭제 하는 경우, 소프트-삭제 또는 영구 삭제 여부는 현재 데이터베이스에 대 한 실제 변경 내용을 나타냅니다. 또한 페이지 비우기는 활성 데이터베이스를 물리적으로 변경 하는 것을 수반 합니다. 이러한 변경 내용은 연속 복제 라는 프로세스를 통해 로그 파일에 기록 되며, 데이터베이스의 수동 복사본에 대해 로그 파일을 재생 하면 해당 수동 데이터베이스에 대 한 동일한 실제 변경 내용이 적용 됩니다.