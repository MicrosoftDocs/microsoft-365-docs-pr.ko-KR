---
title: EOP 대기, 지연 및 반송 메시지 FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 가장 일반적인 질문에 대한 답변을 찾아 묻습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289702"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 대기, 지연 및 반송 메시지 FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

이 항목에서는 EOP(Exchange Online Protection) 필터링 프로세스 중에 대기, 지연 또는 반송된 메시지에 대한 질문과 대답을 제공합니다.

## <a name="why-is-mail-queuing"></a>메일이 큐에서 대기하는 이유는 무엇인가요?

서비스에서 배달을 위해 받는 사람에 연결할 수 없는 경우 메시지가 큐에 대기하거나 지연됩니다. 받는 사람 네트워크에서 500 계열 오류가 반환되는 경우에는 메시지가 지연되지 않습니다.

## <a name="how-does-a-message-become-deferred"></a>메시지는 어떤 방식으로 지연되나요?

받는 사람 서버에 연결할 수 없고 받는 사람의 서버에서 연결 시간 초과, 연결 거부 또는 400 계열 오류와 같은 "일시적인 오류"를 반환하는 경우 메시지가 보류됩니다. 500 계열 오류와 같은 영구 오류가 발생한 경우에는 메시지가 보낸 사람에게 반환됩니다.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>메시지가 지연 상태로 유지되는 기간 및 다시 시도 간격은 어떻게 되나요?

지연 메시지는 1일 동안 큐에 남아 있습니다. 메시지 다시 시도는 받는 사람의 메일 시스템에서 다시 수신된 오류를 기반으로 합니다. 처음 몇 개의 지연은 15분 이하로, 후속 다시시작(후반반 12분 이상)을 통해 여러 재시도 간격을 최대 60분까지 늘립니다. 간격 기간 확장은 큐 크기 및 내부 메시지 우선 순위와 같은 여러 변수를 고려하여 동적입니다. 기본적으로 시작한 후 다음 몇 시간 동안 최대 60분까지 확장하는 것이 15분 이하입니다.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>전자 메일 서버가 복원된 경우 큐에 있는 메시지는 어떻게 배포되나요?

전자 메일 서버가 복원된 후 큐에 있는 모든 메시지는 받은 순서 및 서버를 사용할 수 없어 큐에 추가된 순서대로 자동으로 처리됩니다.
