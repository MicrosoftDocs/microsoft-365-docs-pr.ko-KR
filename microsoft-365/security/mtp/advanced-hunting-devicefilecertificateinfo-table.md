---
title: 고급 헌팅의 DeviceFileCertificateInfo 표
description: 고급 헌팅chema의 DeviceFileCertificateInfo 표에서 파일 서명 정보에 대해 자세히
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931317"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 `DeviceFileCertificateInfo` 헌팅의 [표에는](advanced-hunting-overview.md) 파일 서명 인증서에 대한 정보가 포함되어 있습니다. 이 표에는 끝점의 파일에 대해 정기적으로 수행되는 인증서 확인 활동에서 얻은 데이터가 사용됩니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `IsSigned` | 부울 | 파일에 서명이 있는지 여부를 나타냅니다. |
| `SignatureType` | 문자열 | 서명 정보가 파일 자체에 포함된 콘텐츠로 읽혀지거나 외부 카탈로그 파일에서 읽어들이는지 여부를 나타냅니다. |
| `Signer` | 문자열 | 파일의 서명자에 대한 정보 |
| `SignerHash` | 문자열 | 서명자를 식별하는 고유 해시 값 |
| `Issuer` | 문자열 | 발급 CA(인증 기관)에 대한 정보 |
| `IssuerHash` | 문자열 | 발급 CA(인증 기관)를 식별하는 고유한 해시 값 |
| `CertificateSerialNumber` | 문자열 | 발급 CA(인증 기관)에 고유한 인증서의 식별자 |
| `CrlDistributionPointUrls` | 문자열 |  인증서 및 CRL(인증서 해지 목록)이 포함된 네트워크 공유의 URL을 나열하는 JSON 배열 |
| `CertificateCreationTime` | datetime | 인증서를 만든 날짜 및 시간 |
| `CertificateExpirationTime` | datetime | 인증서가 만료로 설정된 날짜 및 시간 |
| `CertificateCountersignatureTime` | datetime | 인증서가 연대 서명된 날짜 및 시간 |
| `IsTrusted` | 부울 | 알 수 없는 루트 인증서 정보, 잘못된 서명, 해지된 인증서 및 기타 의심되는 특성을 검사하는 WinVerifyTrust 함수의 결과에 따라 파일을 신뢰할 수 있는지 여부를 나타냅니다. |
| `IsRootSignerMicrosoft` | 부울 | 루트 인증서의 서명자인지 여부를 나타냅니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다. | 

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
