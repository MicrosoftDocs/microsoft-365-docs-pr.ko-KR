---
title: 비즈니스용 Microsoft 365에 대한 위협 방지 강화
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Office 365용 Microsoft Defender를 설정하고 피싱, 맬웨어 및 기타 위협으로부터 중요한 데이터를 보호합니다.
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842259"
---
# <a name="increase-threat-protection"></a>위협 방지 강화

이 문서는 피싱, 맬웨어 및 기타 위협으로부터 보호하기 위해 Microsoft 365 구독의 보호를 강화하는 데 도움이 됩니다. 이러한 권장 사항은 법률 사무소 및 의료 기관과 같이 보안 요구가 증가하는 조직에 적절합니다.

시작하기 전에 Office 365 보안 점수를 검사합니다. Office 365 보안 점수는 정기적인 활동 및 보안 설정에 따라 조직의 보안을 분석하고 점수를 할당합니다. 먼저 현재 점수를 기록해 넣습니다. 점수를 높이기 위해 이 문서에서 권장하는 작업을 완료합니다. 목표는 최대 점수를 달성하는 것이 아니라 사용자의 생산성에 부정적인 영향을 주지 않는 환경을 보호할 수 있는 기회를 인식하는 것입니다.

자세한 내용은 [Microsoft 보안 점수를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>메일의 맬웨어에 대한 보호 수준 높이기

Office 365 또는 Microsoft 365 환경에는 맬웨어로부터의 보호가 포함되어 있습니다. 일반적으로 맬웨어에 사용되는 파일 형식의 첨부 파일을 차단하여 이 보호를 강화할 수 있습니다. 전자 메일에서 맬웨어 보호를 강화하는 방법:

1. Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.

2. 보안 준수 센터의 왼쪽 탐색 창에 있는 위협 관리에서 맬웨어 방지 &amp; 정책을   \> **선택하십시오.**

3. 이 회사 전체 정책을 편집하려면 기본 정책을 두 번 클릭합니다.

4. **설정** 을 선택합니다.

5. 일반적인 **첨부 파일 형식 필터에서** 를 **선택합니다.** 차단된 파일 형식은 이 컨트롤 바로 아래에 있는 창에 나열됩니다. 다음 파일 형식을 추가해야 합니다.

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   필요한 경우 나중에 파일 형식을 추가하거나 삭제할 수 있습니다.

6. 저장을 **선택합니다.**

자세한 내용은 EOP의 맬웨어 [방지 보호 기능을 참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="protect-against-ransomware"></a>랜섬웨어로부터 보호

랜섬웨어는 파일을 암호화하거나 컴퓨터 화면을 잠가 데이터에 대한 액세스를 제한합니다. 그런 다음 데이터에 대한 액세스 대가로 일반적으로 암호화 형식의 "금전적"을 요청하여 희생자로부터 돈을 유출하려고 시도합니다.

랜섬웨어로부터 보호하기 위해 하나 이상의 메일 흐름 규칙을 만들어 랜섬웨어에 일반적으로 사용되는 파일 확장명을 차단합니다. (메일 단계에서 맬웨어에 대한 보호 수준을 높이기 위해 이러한 [규칙을 추가했습니다.)](#raise-the-level-of-protection-against-malware-in-mail) 전자 메일로 이러한 첨부 파일을 받는 사용자에게 경고할 수도 있습니다.

이전 단계에서 차단한 파일 외에도 매크로가 포함된 Office 첨부 파일을 열기 전에 사용자에게 경고하는 규칙을 만드는 것이 좋습니다. 매크로 내에서 랜섬웨어를 숨길 수 있으므로 사용자가 모르는 사용자로부터 이러한 파일을 열지 못하게 경고합니다.

메일 전송 규칙을 만들 수 있습니다.

1. 관리 센터로 이동하여 관리 센터 <https://admin.microsoft.com>  \> **Exchange를 선택하세요.**

2. 메일 흐름 **범주에서** 규칙을 **선택합니다.**

3. Select **+** , and then select Create a new **rule**.

4. 전체 **옵션 집합을** 확인하려면 대화 상자 아래쪽에서 다른 옵션을 선택합니다.

5. 규칙에 대해 다음 표의 설정을 적용합니다. 설정을 변경하지 않는 한 나머지 설정에 대해 기본값을 사용합니다.

6. **저장** 을 선택합니다.

|설정|Office 파일의 첨부 파일을 열기 전에 사용자에게 경고||
|---|---|---|
|이름|랜섬웨어 방지 규칙: 사용자에게 경고|
|.이 경우 이 규칙을 적용합니다. . .|모든 첨부 파일. . . 파일 확장명은 일치합니다. . .|
|단어 또는 구 지정|다음 파일 형식을 추가합니다.  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|다음을 합니다. . .|받는 사람에게 메시지로 알림|
|메시지 텍스트 제공|악성 코드가 포함된 매크로가 포함되어 있을 수 있기 때문에 모르는 사용자로부터 이러한 형식의 파일을 열지 않습니다.|

자세한 내용은 다음을 참조하세요.

- [랜섬웨어: 위험을 줄이는 방법](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [OneDrive 복원](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>전자 메일에 대한 자동 전달 중지

사용자의 사서함에 액세스할 수 있는 해커는 사서함이 자동으로 전자 메일을 전달하도록 설정하여 메일을 도용할 수 있습니다. 이는 사용자의 인식 없이도 발생될 수 있습니다. 이러한 문제를 방지할 수 있도록 메일 흐름 규칙을 구성합니다.

메일 전송 규칙을 만들 경우 이 짧은 비디오를 시청하거나 [다음](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) 단계를 따르세요.

1. Microsoft 365 관리 센터에서 **관리 센터** \> **Exchange를 선택합니다.**

2. 메일 흐름 **범주에서** 규칙을 **선택합니다.**

3. Select **+** , and then select Create a new **rule**.

4. 모든 옵션을 확인하려면 대화 상자 아래쪽에서 **다른** 옵션을 선택합니다.

5. 다음 표에 있는 설정을 적용합니다. 설정을 변경하지 않는 한 나머지 설정에 대해 기본값을 사용합니다.

6. **저장** 을 선택합니다.

|설정|Office 파일의 첨부 파일을 열기 전에 사용자에게 경고|
|---|---|
|이름|외부 도메인으로 전자 메일 자동 전달 방지|
|다음의 경우 이 규칙을 적용합니다.|보낸 사람. . . 는 외부/내부입니다. . . 조직 내부|
|조건 추가|메시지 속성. . . 메시지 유형을 포함합니다. . . 자동 전달|
|다음 작업을 합니다.|메시지를 차단합니다. . . 메시지를 거부하고 설명을 포함합니다.|
|메시지 텍스트 제공|이 조직 외부의 전자 메일 자동 전달은 보안상의 이유로 방지됩니다.|


## <a name="protect-your-email-from-phishing-attacks"></a>피싱 공격으로부터 전자 메일 보호

Office 365 또는 Microsoft 365 환경에 대해 하나 이상의 사용자 지정 도메인을 구성한 경우 대상 피싱 방지 보호를 구성할 수 있습니다. Microsoft Defender for Office 365의 일부인 피싱 방지 보호는 악의적인 가장 기반 피싱 공격 및 기타 피싱 공격으로부터 조직을 보호하는 데 도움이 될 수 있습니다. 사용자 지정 도메인을 구성하지 않은 경우 이 작업을 할 필요가 없습니다.

가장 중요한 사용자와 사용자 지정 도메인을 보호하는 정책을 만들어 이 보호를 시작하는 것이 좋습니다.

Microsoft Defender for Office 365에서 피싱 방지 정책을 만들 경우 이 짧은 교육 비디오를 시청하거나  [다음](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)단계를 완료합니다.

1. [https://protection.office.com](https://protection.office.com)으로 이동합니다.

2. 보안 준수 센터의 왼쪽 탐색 창에 &amp; **있는 위협 관리에서** 정책을 **선택 합니다.**

3. 정책 **페이지에서** 피싱 **방지를 선택합니다.**

4. 피싱 **방지 페이지에서** + **만들기를 선택합니다.** 마법사가 피싱 방지 정책을 정의하는 단계를 실행합니다.

5. 다음 표에서 권장되는 정책의 이름, 설명 및 설정을 지정합니다. 자세한 내용은 Microsoft [Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)옵션의 피싱 방지 정책에 대해 자세히 참조하세요.

6. 설정을 검토한 후 해당 정책  만들기 또는 **저장을** 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인 및 가장 중요한 캠페인 직원|
|설명|가장 중요한 직원과 도메인이 가장되지 않도록 합니다.|
|보호할 사용자를 추가|Select **+ Add a condition, the recipient is**. 사용자 이름을 입력하거나 후보, 캠페인 관리자 및 기타 중요한 직원 구성원의 전자 메일 주소를 입력합니다. 가장으로부터 보호하려는 내부 및 외부 주소를 최대 20개까지 추가할 수 있습니다.|
|보호할 도메인을 추가|Select **+ Add a condition, the recipient domain is**. 정의한 경우 Microsoft 365 구독과 연결된 사용자 지정 도메인을 입력합니다. 두 개 이상의 도메인을 입력할 수 있습니다.|
|작업 선택|가장된 사용자가 전자 메일을 보낸 경우: 메시지를 다른 전자 메일 주소로 리디렉션하도록 선택한 다음 보안 관리자의 전자 메일 주소를 입력합니다. 예를 들어 *Alice <span> <span> @contoso.com.* 가장된 도메인에서 전자 메일을 보내는 경우: **격리 메시지** 를 선택합니다.|
|사서함 인텔리전스|새 피싱 방지 정책을 만들 때 기본적으로 사서함 인텔리전스가 선택됩니다. 최상의 결과를 위해 해당 설정을 **켜짐** 에 둡니다.|
|신뢰할 수 있는 발신자와 도메인 추가|여기에서 자체 도메인 또는 다른 신뢰할 수 있는 도메인을 추가할 수 있습니다.|
|적용 대상|**받는 사람의 도메인이 다음과 같음** 을 선택합니다. **이러한 항목 모두** 아래에서 **선택** 을 선택합니다. **+ 추가** 를 선택합니다. 도메인 이름 옆의 확인란(예: *contoso)을 선택합니다. <span> <span> com을* 선택한 다음 추가를 **선택합니다.** **완료** 를 선택합니다.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>안전한 첨부 파일을 통해 악의적인 첨부 파일 및 파일로부터 보호

문서, 프레젠테이션, 스프레드시트 등의 첨부 파일을 정기적으로 보내고 받고 공유합니다. 전자 메일 메시지를 보는 것만 하여 첨부 파일이 안전한지 또는 악의적인지 쉽게 알 수 있는 것은 아닙니다. Office 365용 Microsoft Defender에는 안전한 첨부 파일 보호가 포함되어 있지만 이 보호는 기본적으로 켜져 있지 않습니다. 이 보호를 사용할 새 규칙을 만드는 것이 좋습니다. 이 보호는 SharePoint, OneDrive 및 Microsoft Teams의 파일로 확장됩니다.

안전 첨부 파일 정책을 만들 경우 이 짧은 비디오를 시청하거나 [다음](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)단계를 완료합니다.

1. Go to [https://protection.office.com](https://protection.office.com) , and sign in with your admin account.

2. 보안 준수 센터의 왼쪽 탐색 창에 &amp; **있는 위협 관리에서** 정책을 **선택 합니다.**

3. 정책 페이지에서 안전 첨부 **파일을 선택합니다.**

4. 안전한 첨부 파일 페이지에서 **SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP** 켜기 확인란을 선택하여 이 보호를 광범위하게 적용합니다.

5. 새 **+** 정책을 만들지 선택합니다.

6. 다음 표에 있는 설정을 적용합니다.

7. 설정을 검토한 후 해당  정책 만들기 또는 **저장을** 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|감지된 맬웨어로 현재 및 향후 전자 메일을 차단합니다.|
|설명|감지된 맬웨어로 현재 및 향후 전자 메일 및 첨부 파일을 차단합니다.|
|첨부 파일 알 수 없는 맬웨어 응답 저장|차단 선택 - 감지된 맬웨어로 현재 및 미래의 전자 메일 및 **첨부 파일을 차단합니다.**|
|검색 시 첨부 파일 리디렉션|리디렉션을 사용하도록 설정(이 상자 선택) 관리자 계정 또는 사서함 설정을 입력하여 확인란을 선택합니다.          첨부 파일에 대한 맬웨어 검색이 시간보다 멀거나 오류가 발생하는 경우 위의 선택을 적용합니다(이 상자를 선택).|
|적용 대상|받는 사람 도메인이 . . . 도메인을 선택합니다.|

자세한 내용은 [Office 365용 Microsoft Defender에서](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)피싱 방지 정책 설정을 참조하세요.

## <a name="protect-against-phishing-attacks-with-safe-links"></a>안전한 링크를 통해 피싱 공격으로부터 보호

해커가 전자 메일 또는 기타 파일의 링크에서 악성 웹 사이트를 숨기는 경우도 있습니다. Office 365용 Microsoft Defender의 일부인 안전한 링크는 전자 메일 메시지 및 Office 문서에서 웹 주소(URL)의 클릭 시간 확인을 제공하여 조직을 보호하는 데 도움이 될 수 있습니다. 보호는 안전한 링크 정책을 통해 정의됩니다.

다음을 하는 것이 좋습니다.

- 보호를 강화하도록 기본 정책을 수정합니다.

- 도메인의 모든 받는 사람에게 대상으로 하는 새 정책을 추가합니다.

안전한 링크를 설정하기 위해 이 [짧은 교육](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)비디오를 시청하거나 다음 단계를 완료하세요.

1. Go to [https://protection.office.com](https://protection.office.com) , and sign in with your admin account.

2. 보안 준수 센터의 왼쪽 탐색 창에 &amp; **있는 위협 관리에서** 정책을 **선택 합니다.**

3. 정책 페이지에서 안전한 링크를 **선택합니다.**

기본 정책을 수정하려면

1. 안전한 링크 페이지의 전체 조직에 적용되는 정책에서 **기본** **정책을** 선택합니다.

2. 전자 **메일을 제외한 콘텐츠에** 적용되는 설정에서 엔터프라이즈용 **Microsoft 365 앱, iOS 및 Android용 Office를 선택합니다.**

3. **저장** 을 선택합니다.

도메인의 모든 받는 사람을 대상으로 하는 새 정책을 만들 수 있습니다.

1. 안전한 링크 페이지의 전체 조직에 적용되는 정책 아래에서 새 정책을 만들 **+** 수 있도록 선택합니다.

2. 다음 표에 나열된 설정을 적용합니다.

3. **저장** 을 선택합니다.

|설정 또는 옵션|권장 설정|
|---|---|
|이름|도메인의 모든 받는 사람에 대한 안전한 링크 정책|
|메시지에서 알 수 없는 악의적인 URL에 대한 작업 선택|선택 - 사용자가 링크를 클릭할 때 알려진 악성 링크 목록에 대해 URL을 다시 덮고 **검사합니다.**|
|안전한 첨부 파일을 사용하여 다운로드 가능한 콘텐츠 검색|이 상자를 선택합니다.|
|적용 대상|받는 사람 도메인이 . . . 도메인을 선택합니다.|

자세한 내용은 안전한 링크를 [참조하세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)

## <a name="go-to-intune-admin-center"></a>Intune 관리 센터로 이동합니다.

1. [Azure Portal에 로그인합니다.](https://portal.azure.com/)

2. **모든 서비스** 를 선택하고 **검색 상자** 에 *Intune* 을 입력합니다.

3. 결과가 나타나면 **Microsoft Intune** 옆의 시작을 선택하여 즐겨찾기 및 나중에 쉽게 찾을 수 있도록 합니다.

관리 센터 외에도 Intune을 사용하여 조직의 장치를 등록하고 관리할 수 있습니다. 자세한 내용은 [Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) 장치에 대한 등록 방법 및 [Intune에서](https://docs.microsoft.com/intune/enrollment-options)관리하는 장치에 대한 등록 옵션을 참조하세요.
