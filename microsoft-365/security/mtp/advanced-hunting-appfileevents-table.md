---
title: 고급 구하기 스키마의 AppFileEvents 테이블
description: 고급 구하기 스키마의 AppFileEvents 테이블에 있는 클라우드 앱 및 서비스와 연결 된 파일 관련 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899342"
---
# <a name="appfileevents"></a>AppFileEvents

**적용 대상:**
- Microsoft 위협 방지

`AppFileEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Microsoft cloud App Security에서 모니터링 하는 클라우드 앱 및 서비스의 파일 관련 작업에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. |
| `Application` | 문자열 | 기록 된 작업을 수행한 응용 프로그램 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록 된 작업이 적용 된 파일을 포함 하는 폴더 |
| `PreviousFileName` | 문자열 | 동작의 결과로 이름이 바뀐 파일의 원래 이름입니다. |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN (사용자 계정 이름) |
| `AccountObjectId` | 문자열 | Azure AD의 계정에 대 한 고유 식별자입니다. |
| `AccountDisplayName` | 문자열 | 주소록에 표시 되는 계정 사용자의 이름입니다. 일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `IPAddress` | 문자열 | 끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소 |
| `Location` | 문자열 | 이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치 |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)