---
title: EDiscovery 사례의 보존 보고서 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: eDiscovery 사례와 연결된 모든 보류에 대한 정보가 포함된 보고서를 생성하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 35e432104e7c1358887eb89ae96b9bb0d1d12a0f
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546980"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>EDiscovery 사례의 보존 보고서 만들기

이 문서의 스크립트를 통해 eDiscovery 관리자 및 eDiscovery 관리자는 Office 365 또는 Microsoft 365의 준수 센터에서 eDiscovery 사례와 연결된 모든 보류에 대한 정보가 포함된 보고서를 생성할 수 있습니다. 보고서에는 보류가 연결된 사례의 이름, 보류된 콘텐츠 위치, 보류가 쿼리 기반인지 여부 등의 정보가 포함되어 있습니다. 보류가 없는 사례가 있는 경우 스크립트는 보류되지 않은 사례 목록을 사용하여 추가 보고서를 생성합니다.

보고서에 [포함된 정보에](#more-information) 대한 자세한 설명은 추가 정보 섹션을 참조하세요.

## <a name="admin-requirements-and-script-information"></a>관리자 요구 사항 및 스크립트 정보

- 조직의 모든 eDiscovery 사례에 대한 보고서를 생성하기 위해 조직의 eDiscovery 관리자(Administrator)를 설정해야 합니다. eDiscovery 관리자인 경우 보고서에는 액세스할 수 있는 사례에 대한 정보만 포함됩니다. eDiscovery 사용 권한에 대한 자세한 내용은 [eDiscovery 권한 할당을 참조하세요.](assign-ediscovery-permissions.md)

- 이 문서의 스크립트에는 최소한의 오류 처리가 있습니다. 주요 목적은 조직의 eDiscovery 사례와 연결된 보류에 대한 보고서를 빠르게 만드는 것입니다.

- 이 항목에서 제공된 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서는 지원되지 않습니다. 샘플 스크립트는 어떠한 보증도 없이 "있는 그대로" 제공됩니다. Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용 불가능으로 인해 발생하는 모든 손해(수익에 대한 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알고 있었더라고 마찬가지입니다.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>1단계: 보안 및 & PowerShell에 연결

첫 번째 단계는 조직의 보안 & 준수 센터 PowerShell에 연결하는 것입니다. 단계별 지침은 [보안 및 준수 센터 PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)를 참조하세요.

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>2단계: 스크립트를 실행하여 eDiscovery 사례와 연결된 보류 보고

Security & Compliance Center PowerShell에 연결한 후 다음 단계는 조직의 eDiscovery 사례에 대한 정보를 수집하는 스크립트를 만들고 실행하는 것입니다.

1. 파일 이름 접미사 .ps1을 사용하여 Windows PowerShell 스크립트 파일에 다음 텍스트를 저장합니다. 예를 들어 CaseHoldsReport.ps1.

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. 1단계에서 Windows PowerShell 세션에서 스크립트를 저장한 폴더로 이동합니다.

3. 스크립트를 실행합니다. 예를 들어:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   스크립트에서 보고서를 저장할 대상 폴더를 묻는 메시지가 표시됩니다.

4. 보고서를 저장할 폴더의 전체 경로 이름을 입력한 다음 Enter 를 **누를 수 있습니다.**

   > [!TIP]
   > 스크립트가 있는 폴더에 보고서를 저장하기 위해 대상 폴더에 대한 메시지가 표시될 때 마침표(".")를 입력합니다. 스크립트가 있는 폴더의 하위 폴더에 보고서를 저장하기 위해 하위 폴더의 이름을 입력하기만 하면 됩니다.

   스크립트는 조직의 모든 eDiscovery 사례에 대한 정보를 수집하기 시작합니다. 스크립트가 실행되는 동안 보고서 파일에 액세스하지 않습니다. 스크립트가 완료되면 확인 메시지가 Windows PowerShell 표시됩니다. 이 메시지가 표시되면 4단계에서 지정한 폴더의 보고서에 액세스할 수 있습니다. 보고서의 파일 이름은 `CaseHoldsReport<DateTimeStamp>.csv` 입니다.

   또한 이 스크립트는 보류가 없는 사례 목록이 있는 보고서를 만듭니다. 이 보고서의 파일 이름은 `CaseswithNoHolds<DateTimeStamp>.csv` 입니다.

   다음은 스크립트 실행의 CaseHoldsReport.ps1 예입니다.

   ![실행 중인 스크립트를 실행한 CaseHoldsReport.ps1 출력](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>추가 정보

이 문서의 스크립트를 실행할 때 만들어진 케이스 보류 보고서에는 각 보류에 대한 다음 정보가 포함되어 있습니다. 앞서 설명한처럼 조직의 모든 보류에 대한 정보를 반환하기 위해 eDiscovery 관리자(Administrator)입니다. 케이스 보류에 대한 자세한 내용은 [eDiscovery 사례를 참조하세요.](ediscovery-cases.md)

- 보류의 이름과 보류가 연결된 eDiscovery 사례의 이름입니다.

- eDiscovery 사례가 활성 상태인지 닫혀 있는지 여부입니다.

- 보류를 사용할지 여부를 설정합니다.

- 보류가 연결된 eDiscovery 사례의 구성원입니다. 사례 구성원은 할당된 eDiscovery 사용 권한에 따라 사례를 보거나 관리할 수 있습니다.

- 사례가 만들어진 시간 및 날짜입니다.

- 사례가 마감된 경우 해당 사례를 닫은 사람 및 닫은 시간 및 날짜입니다.

- 보류된 Exchange 사서함 및 SharePoint 사이트 위치

- 보류가 쿼리 기반인 경우 쿼리 구문입니다.

- 보류를 만든 시간 및 날짜와 보류를 만든 사람입니다.

- 보류가 마지막으로 변경된 시간 및 날짜와 변경한 사람입니다.
