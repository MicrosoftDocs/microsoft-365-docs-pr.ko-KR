---
title: EOP의 후방 산란
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 후방산자 및 EOP(Microsoft Exchange Online 보호)에 대해 자세히 알아보게 될 것입니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286972"
---
# <a name="backscatter-in-eop"></a>EOP의 후방 산란

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*후방산은* 보내지 않은 메시지에 대해 수신하는 배달 못지 않은 보고서(NDRS 또는 반송 메시지라고도 합니다.)입니다. 스팸 발송자(스푸핑)는 메시지의 보낸사용자: 주소를위조(스푸핑)하며, 종종 실제 전자 메일 주소를 사용하여 메시지에 신뢰성을 제공합니다. 따라서 스패머가 존재하지 않는 받는 사람에게 메시지를 보낼 수 없는 경우(스팸은 대량의 작업임) 대상 전자 메일 서버는 기본적으로 NDR에서 배달할 수 없는 메시지를 보낸 사람: 주소의 위조된 보낸 사람에게 반환하는 속임수입니다.

Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 EOP는 NDR을 생성하지 않고도 의심스러운 원본에서 메시지를 식별하고 자동으로 삭제하기 위해 모든 노력을 다하고 있습니다. 그러나 서비스를 통해 흐르는 볼륨 전자 메일에 따라 EOP가 의도치 않은 후방 메일을 보낼 가능성이 항상 있습니다.

Backscatterer.org 전송을 담당하는 전자 메일 서버의 차단 목록(DNS 차단 목록 또는 DNSBL)을 유지 관리하고 EOP 서버가 이 목록에 표시될 수 있습니다. 그러나 스태머 목록이 아니기 때문에 (자신의 입장에서) Backscatterer.org 차단 목록에서 제거하려고 하지 않습니다.

> [!TIP]
> Backscatter.org 웹 사이트()는 서비스를 사용하여 거부 모드 대신 수신 전자 메일을 안전한 모드로 검사하는 것이 좋습니다(대규모 전자 메일 서비스는 거의 항상 일부 후방산을 <http://www.backscatterer.org/?target=usage> 전송).
