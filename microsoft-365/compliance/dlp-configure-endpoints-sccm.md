---
title: 구성 관리자를 사용하여 Windows 10 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Configuration Manager를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드됩니다.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769476"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>구성 관리자를 사용하여 Windows 10 장치 온보딩

**적용 대상:**

- [Microsoft 365 끝점 DLP(데이터 손실 방지)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>System Center Configuration Manager를 사용하여 디바이스 온보드

1. 서비스 온보더링 마법사에서 ** 다운로드한 Configuration Manager 구성 패키지 .zip 파일(DeviceComplianceOnboardingPackage.zip)을 니다. Microsoft 준수 센터에서 패키지를 [다운로드할 수 있습니다.](https://compliance.microsoft.com/)

2. 탐색 창에서 설정 디바이스  >  **온보더링을**  >  **선택합니다.**

3. 배포 방법 **필드에서** **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602를 선택합니다.**
 
4. 패키지 **다운로드를** 선택하고 .zip 파일을 저장합니다.

5. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다. *DeviceComplianceOnboardingScript.cmd라는 파일이 필요합니다.*

6. R2 Configuration Manager 문서의 패키지 및 프로그램 단계에 따라 System Center 2012 [배포합니다.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

7. 패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.

> [!NOTE]
> Microsoft 365 끝점 데이터 손실 방지는 [OOBE(첫](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 제공 경험) 단계 동안 온보더링을 지원하지 않습니다. 사용자가 Windows 설치 또는 업그레이드를 실행한 후 OOBE를 완료하는지 확인

>[!TIP]
> 장치를 온보더링한 후 검색 테스트를 실행하여 장치가 서비스에 올바르게 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)장치에서 검색 테스트 실행을 참조하세요.
>
> Configuration Manager 응용 프로그램에 검색 규칙을 만들어 장치가 지속적으로 온보더된지 확인할 수 있습니다. 응용 프로그램은 패키지 및 프로그램과 다른 유형의 개체입니다.
> 장치가 아직 온보드되지 않은 경우(OOBE 완료 보류 또는 기타 이유로 인해) 규칙에서 상태 변경이 감지될 때까지 Configuration Manager가 장치 온보드를 다시 시도합니다.
> 
> 이 동작은 "OnboardingState" 레지스트리 값(예: REG_DWORD) = 1이면 검색 규칙을 만들어 수행할 수 있습니다.
> 이 레지스트리 값은 "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" 아래에 있습니다.
자세한 내용은 R2 Configuration [Manager에서 검색 System Center 2012 참조하십시오.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>샘플 수집 설정 구성

각 디바이스에 대해 Microsoft Defender 보안 센터를 통해 요청이 있을 때 장치에서 샘플을 수집할 수 있는지 여부를 설명하는 구성 값을 설정하여 심층 분석을 위해 파일을 제출할 수 있습니다.

>[!NOTE]
>이러한 구성 설정은 일반적으로 Configuration Manager를 통해 수행됩니다. 

Configuration Manager에서 구성 항목에 대한 준수 규칙을 설정하여 디바이스에서 샘플 공유 설정을 변경할 수 있습니다.

이 규칙은  불만이 있는지 확인하도록 대상 디바이스의 레지스트리 키 값을 설정하는 수정 준수 규칙 구성 항목입니다.

구성은 다음 레지스트리 키 항목을 통해 설정됩니다.

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
여기서,<br>
키 형식은 D-WORD입니다. <br>
가능한 값은 다음과 같습니다.
- 0 - 이 장치에서 샘플 공유를 허용하지 않습니다.
- 1 - 이 장치에서 모든 파일 형식을 공유할 수 있습니다.

레지스트리 키가 없는 경우의 기본값은 1입니다.

System Center Configuration Manager 규정 준수에 대한 자세한 내용은 R2 Configuration Manager의 규정 [준수 System Center 2012 참조하세요.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>기타 권장 구성 설정
장치에 서비스를 온보드한 후 다음과 같은 권장 구성 설정을 사용하여 포함된 위협 방지 기능을 활용하는 것이 중요합니다.

### <a name="device-collection-configuration"></a>디바이스 컬렉션 구성
Endpoint Configuration Manager 버전 2002 이상을 사용하는 경우 서버 또는 다운 수준 클라이언트를 포함하기 위해 배포를 확장할 수 있습니다.


### <a name="next-generation-protection-configuration"></a>차세대 보호 구성

권장되는 구성 설정은 다음과 같습니다.

**스캔**

- USB 드라이브와 같은 이동식 저장 장치 검색: 예

**실시간 보호**

- 동작 모니터링 사용: 예
- 다운로드할 때와 설치 전에 사용자 원치 않는 응용 프로그램으로부터 보호 사용: 예

**클라우드 보호 서비스**

- 클라우드 보호 서비스 멤버십 유형: 고급 멤버십

**공격 표면 감소** 사용 가능한 모든 규칙을 감사하도록 구성합니다.

>[!NOTE]
> 이러한 활동을 차단하면 합법적인 비즈니스 프로세스가 중단될 수 있습니다. 가장 좋은 방법은 모든 것을 감사로 설정하고, 켜도 안전한 설정을 식별한 다음, 가식 검색이 없는 끝점에서 해당 설정을 사용하도록 설정하는 것입니다.

**네트워크 보호**

감사 또는 차단 모드에서 네트워크 보호를 사용하도록 설정하기 전에 지원 페이지에서 얻을 수 있는 맬웨어 방지 플랫폼 업데이트를 설치해야 [합니다.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**제어된 폴더 액세스**

감사 모드에서 기능을 30일 이상 사용하도록 설정 이 기간이 지난 후 검색을 검토하고 보호된 Director에 쓸 수 있는 응용 프로그램 목록을 생성합니다.

자세한 내용은 제어된 폴더 [액세스 평가를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)


## <a name="offboard-devices-using-configuration-manager"></a>Configuration Manager를 사용하여 디바이스 오프보드

보안상의 이유로 장치의 오프보드에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책은 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Microsoft Endpoint Configuration Manager 현재 분기를 사용하여 디바이스 오프보드

Microsoft Endpoint Configuration Manager 현재 분기를 사용하는 경우 오프보더 구성 파일 [만들기를 참조합니다.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>R2 Configuration Manager를 사용하여 System Center 2012 오프보드

1. Microsoft 준수 센터에서 [오프보더 패키지를 다운로드합니다.](https://compliance.microsoft.com/)

2. 탐색 창에서 설정 장치  >   **온보더링 오프보더를** >  **선택합니다.**

3. 운영 체제로 Windows 10을 선택합니다.

4. 배포 방법 **필드에서** **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602를 선택합니다.**
    
5. 패키지 **다운로드를** 선택하고 .zip 파일을 저장합니다.

6. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다. 이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd입니다.*

7. R2 Configuration Manager 문서의 패키지 및 프로그램 단계에 따라 System Center 2012 [배포합니다.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

8. 패키지를 배포할 미리 정의한 장치 컬렉션을 선택하십시오.

> [!IMPORTANT]
> 오프보더를 통해 디바이스가 포털로 센서 데이터 전송을 중지하지만, 디바이스의 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.


## <a name="monitor-device-configuration"></a>장치 구성 모니터링

Microsoft Endpoint Configuration Manager 현재 분기를 사용하는 경우 Configuration Manager 콘솔에서 기본 제공 Microsoft Defender ATP 대시보드를 사용하세요. 자세한 내용은 [Microsoft Defender Advanced Threat Protection - 모니터링을 참조하세요.](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

R2 Configuration Manager를 System Center 2012 모니터링은 다음 두 부분으로 구성됩니다.

1. 구성 패키지가 올바르게 배포되어 네트워크의 디바이스에서 실행 중(또는 성공적으로 실행)을 확인합니다.

2. 장치가 Microsoft 365 끝점 데이터 손실 방지 서비스를 준수하는지 확인합니다(이렇게 하면 장치가 온보더링 프로세스를 완료하고 서비스에 데이터를 계속 보고할 수 있습니다).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>구성 패키지가 올바르게 배포되어 있는지 확인

1. Configuration Manager 콘솔에서 탐색 **창** 아래쪽의 모니터링을 클릭합니다.

2. **개요를** 선택한 다음 **배포를 선택합니다.**

3. 패키지 이름이 있는 배포에서 선택합니다.

4. 완료 통계 및  콘텐츠 상태의 상태 **표시기를 검토합니다.**

    배포에 실패한 **경우(오류,** 요구 사항이 충족되지 않은 장치 **또는** 실패한 상태인 **장치)** 장치 문제를 해결해야 할 수 있습니다. 자세한 내용은 Microsoft [Defender Advanced Threat Protection 온보딩 문제 해결을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

    ![오류 없는 성공적인 배포를 보여주는 Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>장치가 Microsoft 365 엔드포인트 데이터 손실 방지 서비스를 준수하는지 확인

R2 Configuration Manager의 구성 항목에 대한 준수 규칙을 System Center 2012 배포를 모니터링할 수 있습니다.

> [!NOTE]
> 이 절차 및 레지스트리 항목은 Endpoint DLP 및 Advanced Threat Protection에 적용됩니다.

이 규칙은  대상 디바이스에서 레지스트리 키 값을 모니터링하는 수정되지 않는 준수 규칙 구성 항목입니다.

다음 레지스트리 키 항목을 모니터링합니다.
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
자세한 내용은 R2 Configuration Manager의 준수 [설정 System Center 2012 참조하세요.](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용하여 Windows 10 장치 온보드](dlp-configure-endpoints-gp.md)
- [모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩](dlp-configure-endpoints-mdm.md)
- [로컬 스크립트를 사용하여 Windows 10 장치 온보딩](dlp-configure-endpoints-script.md)
- [비영구 가상 데스크톱 인프라(VDI) 장치 온보딩](dlp-configure-endpoints-vdi.md)
- [새로 온보딩된 Microsoft Defender ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
